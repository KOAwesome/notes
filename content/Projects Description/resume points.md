one line summary > **Data Engineer with hands-on experience building metadata-driven data quality frameworks and complex Spark-based transformation pipelines for large-scale financial and regulatory datasets on AWS.**
# **🔹 CORE DATA ENGINEER BULLETS (USE THESE)**

  

### **Data Engineering | AWS Glue | PySpark | S3 | Athena | Iceberg**

- Designed and implemented a **metadata-driven Data Quality Framework in PySpark**, supporting profiling, rule-based validation, threshold evaluation, and historical drift detection across large-scale datasets.
    
- Built a **hard/soft validation rule engine**, where hard failures block downstream pipelines while soft failures generate warnings, enabling controlled data quality enforcement for regulatory and BI use cases.
    
- Integrated **S3-hosted configuration–driven rules** to dynamically apply validations only on required columns, reducing Spark execution cost and improving pipeline performance.
    
- Implemented **historical profile comparison logic** to detect month-over-month deviations in data distributions, enabling early detection of upstream data issues.
    

---

# **🔹 COMPLEX SPARK TRANSFORMATION BULLETS (VERY IMPORTANT)**

- Developed a large-scale **limited company data transformation pipeline**, consolidating **22+ source tables into a unified 150+ column Parquet dataset** for credit risk and business intelligence analysis.
    
- Implemented **temporal self-joins with time-range conditions** to correctly align historical financial records and prevent future-data leakage in time-series datasets.
    
- Designed **multi-window Spark aggregations** using multiple partitioning and ordering strategies to compute financial metrics such as YoY changes, rolling indicators, and latest snapshots.
    
- Programmatically applied **dynamic column aggregations across 40+ financial fields** using reusable window specifications, improving maintainability and scalability.
    

---

# **🔹 BUSINESS LOGIC + DOMAIN BULLETS (THIS MAKES YOU SENIOR-LEANING)**

- Implemented complex **financial derivations** including percentage change calculations, currency normalization, zero-division handling, and null-safe arithmetic for risk analytics.
    
- Built logic to handle **live vs inactive company states**, historical director records, site-level enrichment, and insolvency/distress indicators using conditional transformations.
    
- Developed **credit-risk and financial health indicators** by combining multi-source business, payment, and judgment datasets.
    

---

# **🔹 PERFORMANCE & PRODUCTION READINESS BULLETS**

- Optimized Spark workloads using **strategic repartitioning (up to 150 partitions)**, column pruning, and staged transformations to handle large-volume joins efficiently.
    
- Designed pipelines with **failure isolation and structured error outputs**, generating Step Functions–friendly summaries and detailed CSV error reports in S3.
    
- Ensured **schema consistency across evolving datasets** by dynamically adding missing columns and enforcing data type casting before final writes.
    

---

# **🔹 VERSION CONTROL & PIPELINE CONTEXT**

- Maintained production codebases in **Bitbucket**, collaborating on Glue-based ETL pipelines with structured version control and environment-specific configurations.
    
- Worked with **Iceberg tables queried via Athena** as upstream sources, integrating schema-evolving datasets into Spark-based transformation pipelines.
- 