Even after installing I faced virtual env issue. I copied the requirements and now started working.
My basics in pandas, pyspark and newly added delta lake all suck I just realised

yf.download(['MSFT', 'AAPL', 'GOOG'], period='1mo')


- Why does MultiIndex break Spark?
- > Spark DataFrames require **flat, atomic column names**.
> Pandas MultiIndex creates **hierarchical column metadata**, which Spark cannot map to its schema model.
> As a result, Spark either misinterprets the schema or fails during write operations.
    
- Why is looping per symbol safer?
- We clean each symbol first then proceed it to next stage.. > It also simplifies debugging and supports partial reprocessing due to isolation
    
- Why should Bronze normalize shape but not correctness?
	Bronze normalizes shape and schema so data is usable downstream, but preserves raw correctness for traceability.
	This allows reprocessing, auditing, and debugging without losing original source information.

Bronze layer - Data Ingestion:
In this layer I checked the column names for spaces or unaccepted characters then replaced them (snake case)
Why we need delta? > Delta Lake is a storage layer that brings ACID transactions, schema enforcement, and time travel to data lakes. It also contains Delta output log diff than parquet

Why dropduplicates(['date']) better than this dropduplicates()
dropDuplicates() without columns is non-deterministic because Spark may keep any arbitrary row. Specifying ["Date"] enforces a business-defined uniqueness rule, making the result predictable and explainable
1. Why is dropDuplicates(["Date"]) acceptable here?
    In our case date is primary key and it eliminates records
2. When would it be dangerous?
    When we need to consider close
3. Why might (Date, Close) be safer than just Date?
	In some cases we need to eliminate duplicates on close
4. Do you understand why dropDuplicates(["Date"]) comes **before** the window?
	to eliminate confusion and establish better clarity.. like if same date has percentage change it won't be sensible