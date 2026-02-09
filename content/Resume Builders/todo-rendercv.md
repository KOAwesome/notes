https://www.linkedin.com/posts/josesilesdata_i-used-to-spend-a-lot-of-time-adjusting-my-activity-7410960201626996736-uLab?utm_source=share&utm_medium=member_desktop&rcm=ACoAADme3p8BWs6StE8O0ClexFkQYfpKLRmS56g



## **SAI RAHUL NALLANDHIGHAL**

  

**Data Engineer**

Hyderabad, India | 📧 mkssps42@gmail.com | 📞 8499036028

GitHub: KOAwesome | Portfolio: nsrahul

---

### **SUMMARY**

  

Data Engineer with **1.5+ years of experience** designing **metadata-driven data quality frameworks** and building **large-scale Spark-based transformation pipelines on AWS**. Strong hands-on experience with **PySpark, AWS Glue, S3, Athena, and Iceberg**, implementing **temporal joins, window aggregations, and complex financial transformations** for regulatory, accreditation, and credit-risk analytics. Proven ability to handle production-scale data, enforce data quality, and optimize Spark performance.

---

### **EXPERIENCE**

  

**Developer 1 – Software Engineering**

**UST Global** | Hyderabad | **Jul 2024 – Present**

- Designed and implemented a **metadata-driven Data Quality Framework in PySpark**, supporting profiling, rule-based validation, threshold evaluation, and historical drift detection.
    
- Built a **hard vs soft validation rule engine**, where hard failures block downstream pipelines and soft failures generate warnings, enabling controlled enforcement of data quality.
    
- Developed **AWS Glue–based ETL pipelines** consuming **Iceberg tables via Athena** and writing curated **Parquet datasets to S3**.
    
- Implemented **historical profile comparison** to detect month-over-month deviations in data distributions and identify upstream data issues early.
    
- Built a **large-scale limited company transformation pipeline**, consolidating **22+ source tables into a unified 150+ column dataset** for credit risk and business intelligence.
    
- Implemented **temporal self-joins with time-range conditions** to correctly align historical financial records and prevent future-data leakage.
    
- Designed **multi-window Spark aggregations** to compute YoY changes, rolling indicators, and latest snapshot metrics.
    
- Programmatically applied **dynamic aggregations across 40+ financial columns** using reusable Spark window specifications.
    
- Implemented complex **financial derivations** including currency normalization, percentage change calculations, and null-safe arithmetic.
    
- Optimized Spark workloads using **column pruning, repartitioning (up to 150 partitions), and staged transformations**.
    
- Implemented **structured failure handling and error reporting**, generating Step Functions–friendly summaries and detailed CSV reports in S3.
    
- Maintained production codebases in **Bitbucket** with environment-specific configurations.
    

---

### **PROJECTS**

  

**Market Data Analytics Pipeline**

_PySpark, Apache Spark, Delta Lake, SQL_

- Built an end-to-end **Spark-based Bronze–Silver–Gold pipeline** for time-series market data.
    
- Implemented **deduplication, schema enforcement, and data quality validation** at each layer.
    
- Used **Delta Lake MERGE** for idempotent processing and safe reprocessing of historical data.
    

  

**Google Pay Transaction Analysis**

_Python, PySpark, Regex_

- Parsed raw Google Pay HTML statements using **regex-based extraction**.
    
- Processed and enriched data using **PySpark** and implemented rule-based spend categorization.
    

  

**Sportify – Cricket Tournament Management System**

_SQL, Azure Data Factory, Power BI_

- Designed **OLTP and OLAP models** and built ETL pipelines using **ADF**.
    
- Developed **Power BI dashboards** for operational and analytical KPIs.
    

---

### **SKILLS**

  

**Languages & Processing:** Python, PySpark, SQL, Apache Spark

**Cloud & Data:** AWS Glue, S3, Athena, Iceberg, Azure Data Factory, Azure Synapse

**Data Engineering:** Metadata-driven ETL, Data Quality Frameworks, Schema Evolution, CDC, Window Functions

**Storage & Tools:** Delta Lake, Parquet, Databricks, Linux/Unix

---

This version is **ready to apply**.

Now we tailor it.

---

# **PART 2 — COMPANY-SPECIFIC TAILORING**

  

## **🔹 For** 

## **Franklin Templeton / Finance / Asset Management**

  

When applying, **slightly modify summary + 2 bullets**:

  

### **Summary tweak (finance-heavy):**

  

> Data Engineer with 1.5+ years of experience building Spark-based transformation pipelines and data quality frameworks for **financial, regulatory, and credit-risk datasets** on AWS.

  

### **Add this bullet under experience:**

- Built and validated **financial health, credit risk, and payment performance indicators** used for downstream analytical and decisioning systems.
    

  

Why this works:

- Franklin Templeton cares about **data correctness + lineage + finance semantics**
    
- You already do this — now it’s explicit
    

---

## **🔹 For** 

## **Product / Big Tech (Amazon, Uber-style DE roles)**

  

Add emphasis on **scale & Spark**:

  

Replace one bullet with:

- Designed Spark transformations involving **large joins, multi-level window functions, and performance tuning** for production-scale datasets.
    

  

And move **Spark, Window Functions** to the **top of Skills**.

---

## **🔹 For** 

## **Fintech / Risk / Credit companies**

  

Add:

- Implemented **strict data quality gates** to prevent incorrect financial data from propagating to downstream risk and reporting systems.
    

---

# **PART 3 — INTERVIEW ANSWERS MAPPED TO YOUR RESUME (CRITICAL)**

  

Below is how you **answer confidently**, without rambling.

---

### **❓ “Tell me about your current role”**

  

**Answer (use this structure):**

  

> I work as a Data Engineer building Spark-based transformation pipelines on AWS. My primary responsibility is designing metadata-driven data quality frameworks and implementing complex PySpark transformations for financial and regulatory datasets. I work heavily with Glue, Iceberg, Athena, and S3, and handle temporal joins, window aggregations, and performance tuning in production pipelines.

---

### **❓ “Is your work more testing or development?”**

  

**Never hesitate. Say:**

  

> It’s primarily development. The data quality framework itself is a reusable Spark component integrated directly into ETL pipelines, and I also work extensively on transformation logic, temporal joins, and performance optimization.

---

### **❓ “What’s the most complex thing you built?”**

  

**Answer:**

  

> A financial transformation pipeline where I had to align historical records using temporal self-joins, apply multi-window aggregations for YoY and rolling metrics, and dynamically compute 40+ financial fields while ensuring no future-data leakage.

---

### **❓ “How do you handle Spark performance?”**

  

**Answer:**

  

> I prune columns early, control partition counts explicitly, avoid unnecessary shuffles, and design joins and windows carefully. For large joins, I repartition strategically and coalesce before writes to manage both execution time and file sizes.

---

### **❓ “Why should we hire you?”**

  

**Answer:**

  

> I’ve already worked on production pipelines where correctness matters as much as scale. I’m comfortable owning Spark transformations end to end — from data quality enforcement to complex business logic and performance optimization.

---