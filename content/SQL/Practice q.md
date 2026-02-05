1. How do you identify and remove duplicate records in a table without losing data?  
		use business keys and perform ranking operatio( retain latest record by TS) 
2. Write a SQL query to find the second highest salary per department.  
	1. DENSE rank concept
3. Difference between INNER JOIN vs LEFT JOIN with a real-world use case.  
	1. 
4. How do indexes work internally, and when do they actually hurt performance?  
		Btree 
			+ves:lesser FT scans
			-ve: inserts, deletes costly
5. What is slowly changing dimension (SCD)? Explain Type 1 vs Type 2.  
		change aitai but not daily basis like address ..etc 
		type1- overwrites (no history)
		type 2- full history 
		
6. How would you design an ETL pipeline to ingest data from multiple sources in near real-time?  
		1. **Design:**
	- Sources → Kafka/Event Hub
	- Stream ingestion → Spark Structured Streaming
	- Landing → ADLS (Bronze)
	- Transform → Silver/Gold
	- Serve → Synapse / Power BI
	Key features:
	- Schema enforcement
	- Checkpointing
	- Exactly-once semantics
	- Metadata-driven configs
7. Difference between ETL and ELT. Which one would you choose for cloud data warehouses and why?  
		|**ETL**|**ELT**|
		|---|---|
		|Transform before load|Load first, transform later|
		|Limited scalability|Uses cloud compute|
		|Legacy systems|Modern cloud DW|
	Cloud warehouses (Synapse, Snowflake) are scalable and cheaper for transformations.
8. How do you handle late-arriving data in data pipelines?  
			Methods:

		- Event-time processing + **watermarks**
		    
		- Reprocessing windows
		    
		- Upserts using **MERGE**
		    
		- Maintain correction logic
9. How do you make pipelines fault-tolerant?  
	1. > Pipeline must **resume**, not restart.
	2. - Retry mechanisms
    
	- Checkpointing
	    
	- Idempotent writes
	    
	- Dead-letter queues
	    
	- Alerting + monitoring
11. Explain idempotency and why it is critical in data pipelines.  
	Running the same job multiple times produces **same result**.
			**Why critical:**
		
		- Failures
		    
		- Retries
		    
		- Reprocessing historical data
		    
		
		  
		
		Achieved by:
		
		- Natural keys
		    
		- Deduplication
		    
			- Delta Lake MERGE
9. How does Apache Spark handle shuffle operations, and why are they expensive?  
	1. 
10. Difference between partitioning and bucketing in Spark/Hive.  
		partition- physical seperation
		bucketing - hashing data to buckets
11. How would you optimize a Spark job that runs slowly on large datasets?  
	1. Correct answers (add these):
	
	- Reduce shuffle
	    
	- Broadcast small tables
	    
	- Handle skew
	    
	- Cache reused datasets
	    
	- Tune partitions
	    
	- Use efficient file formats (Parquet)
	1. add indexes
	2. check for skews and repartition
	3. increase workers 
12. Explain the CAP theorem with a practical example.  
		1. consistency, availability partition tolerance
	1. - - Choose **CP** → data is consistent, system may be unavailable
    - Choose **AP** → system available, data may be temporarily inconsistent
13. How do you ensure data consistency and reliability in distributed systems?
	1. - Idempotent operations
	    
	- Exactly-once processing
	    
	- Schema enforcement
	    
	- Transactions (Delta Lake)
	    
	- Monitoring + audits
	    
	- Data quality checks

