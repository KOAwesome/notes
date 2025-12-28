why did you use spark?
> I used Spark because it provides distributed processing for large time-series datasets and supports advanced analytics like window functions, joins, and aggregations.

> Combined with Delta Lake, it also gives me ACID guarantees, schema enforcement, and idempotent writes, which are essential for reliable data pipelines.

## **How did you ensure idempotency?**

  

**Correct answer:**

  

> I used Delta Lake MERGE in the Silver layer so reruns update existing records instead of duplicating them.

> This allows safe reprocessing and late-arriving data handling.

Setup: Installed openjdk, spark and setup config files in local.

After verifying spark installation then installed python3.11 and created a venv for the same

*configure_spark_with_delta_pip* spark by default doesn't know about delta lake by configuring it in code it enables us enables delta catalog , lake and sql extensions

medallion architecture: we have three layers bronze, silver, gold

**Bronze layer - Data Ingestion**
Bronze layer is stored as Delta Lake, not plain Parquet.
- Delta **uses Parquet files internally**, but:
    - Parquet ≠ Delta
    - Delta = Parquet **+ transaction log (_delta_log)**

> In my project, the Bronze layer contains raw market data from 2023–2024 stored in Delta format.

> The data is structured but not cleaned — it may contain nulls or duplicates.

> Bronze prioritizes data availability and structure over correctness[CAP], which is why we do not perform analysis directly on it.

> Delta Lake is used to provide **ACID** transactions, safe reprocessing, schema enforcement, and time travel, which makes the pipeline production-ready.

Bronze layer represents raw but structured data as received from the source.
Why we need delta? > _Delta Lake is a storage layer that brings ACID transactions, schema enforcement, and time travel to data lakes._
	1. Reinforces acid transactions
	2. idempotent writes(parquet doesn't guarantee this)
		Job failed at 80%
		→ re-run
		→ no duplicate / corrupted data
	3. Schema enforcement (prevents accidental schema changes)
	4. Time Travel
	5. Merge/upsert more safer

> **What transformation do you think belongs in Silver but NOT in Bronze? or Why we dont perform transformations in bronze layer?** 

> (Example: daily returns, deduplication, null handling — pick one and explain why.)
 Deduplication belongs in the Silver layer because Bronze must remain a lossless representation of the source.

Removing duplicates in Bronze would destroy **auditability and prevent accurate reprocessing**.

Silver is where we apply correctness and business logic.



**How would you define a duplicate here?**
Choose **one**
- Same (symbol, trade_date) appears twice
- Same (symbol, trade_date, close) appears twice
- 
> I define duplicates as records where (symbol, trade_date, close) are identical, because for financial analytics the close price uniquely represents the end-of-day state.

> Records with the same date but different close values represent different states and must be preserved until business rules decide which one is correct.

 Should daily return for the **first day of a symbol** be:
- NULL
- 0
- dropped completely
Pick one and say **why**.

Why 
NULL
 is correct (tight explanation)
First trading day has no previous close
Any numeric value (0) would be fake data    
Dropping the row would lose a valid trading day

**Silver layer**
Now here we perform cleaning tasks to meet our business requirements. First we load our bronze data and drop duplicates over symbol, trade_date and close. 

After that we apply a window function to calculate daily return. We do this by lagging(close) by one row so that we can obtain difference net profit or loss.

| close | previous close |
| ----- | -------------- |
| 100   | null           |
| 101.5 | 100            |

Then I have stored the results partitioned by Symbol

delta doesn't silently overwrite existing data. it asks for explicit permission `overwriteSchema` only after setting it true it writes.. When adding volatility it got this safe mechanism


mergeschema `.option("mergeSchema", "true")`
This is better for:
- append jobs
- streaming
- incremental evolution
For a **batch overwrite Silver job**, overwriteSchema is cleaner.

> When calculating Moving averages and volatility they are computed using rolling window functions partitioned by symbol and ordered by trade date.

> Initial rows return NULL due to insufficient history, which preserves analytical correctness.

`silver_df.write.format("delta") \`

`.mode("overwrite") \`

`.option("overwriteSchema", "true") \`

`.partitionBy("symbol") \`

`.save(silver_path)`
previously i was doing batch operations.. it performs on the entire table and is costly if there are updates or simply new insertions to load all data. So we have merge/upsert option for the same

I ran the query twice second time it ran faster. I think thanks to update functionality

when i ran for count and checked it showed 750
`spark.read.format("delta").load("/tmp/market/silver_prices").count()`
Silver layer uses upsert merge to perform idempotent upserts based on business keys
- safe reprocessing
- late data handling
- prevent duplication without full loads

**Gold Layer**
> The Gold layer aggregates Silver-level analytics into symbol-level KPIs that are directly consumable by reporting and dashboards, separating business metrics from transformation logic.

Bronze → Silver → Gold
(raw)     (analytics)   (business KPIs)


Now, I have successfully completed ingestion and processing part. 
> Can downstream users trust this data?
Like what happens if we get close as negative values, maybe there is no symbol.

for that reason we need to perform 
	1. null checks
	2. domain checks( range checks)
	3. duplicates detection
	4. completeness check

for null checks performing a full table count is not optimal like this `null_violations.count() > 0` it is costly operation
so i have used `if df.limit(1).count() > 0:` here we are taking only one row if there is one row it means there is violation

for completeness checks 
  

`if silver_df.count() > bronze_df.count():
	raise Exception("❌ Data Quality Failed: Silver has more rows than Bronze")`
We know at this point that silver we remove duplicates so silver count should always be less but it is too basic

`if null_violations.limit(1) is not None:`
 why ❌ - A DataFrame object is **never** **None**, even if it has **0 rows** 
 instead we could `null_violations.**isEmpty()**`

I created generic reusable rules and placed it under data quality 
then i encountered Traceback (most recent call last):
  File "/Users/sairahul/git/market-data-analytics-pipeline/data_quality/silver_data_quality_check.py", line 4, in <module>
    from data_quality.checks import (
ModuleNotFoundError: No module named 'data_quality'

Its because root was confusing so then I started running it as module 
`python -m data_quality.silver_data_quality_check`

To Upgrade checklist
1. Orchestration: right now i am running it manually i will try to integrate airflow and if possible revise airflow concepts too
2. Parameterization: many of the values in my current code are hard coded I will use cli tags
3. Environment seperation: everything is stored in temp should change it to cloud for automatic scaling
4. Logging and monitoring
5. Data quality enforcement: seperate soft warns and hard fails
6. Schema governance: write now manual overwrite should add versioning concept
7. incremental processing: processing only new data based on date. 
8. cost control: 
9. access controls
10. testing strategy

> I built the core Spark + Delta pipeline first, then identified production gaps such as orchestration, incremental processing, logging, and schema governance. I treated those as conscious trade-offs rather than omissions.