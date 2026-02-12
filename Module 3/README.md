# Module 3: Data Storage and Queries

**Course:** Data Storage and Queries
**Platform:** DeepLearning.AI on Coursera
**Status:** ✅ Completed

---

## 📖 Course Overview

This module explores the **Storage** stage of the data engineering lifecycle, focusing on the hierarchy from physical components to high-level abstractions like Data Lakes and Lakehouses. The primary objective is to evaluate the trade-offs between storage cost and query performance to design efficient data systems.

### 🎯 Learning Outcomes

* **Storage Evaluation:** Assessing hardware (HDD vs. SSD), serialization, and compression algorithms.
* **Database Paradigms:** Comparing **Row-oriented** (OLTP) vs. **Column-oriented** (OLAP) storage and their impact on analytical speed.
* **Modern Architectures:** Implementing **Data Lake** and **Data Lakehouse** patterns on AWS.
* **Advanced Querying:** Executing graph traversals with **Cypher** and performing **Vector Search** for similarity-based retrieval.

---

## 🛠️ Key Technologies

| Technology | Role in Project |
| --- | --- |
| **Neo4j & Cypher** | Graph database for relationship-heavy data and vector similarity search. |
| **Amazon Redshift** | Columnar storage for high-performance OLAP benchmarking. |
| **AWS Glue & Athena** | Serverless ETL for Parquet conversion and SQL-on-S3 querying. |
| **Amazon S3** | Primary storage layer for the Data Lake and Parquet files. |
| **Terraform** | Automating storage infrastructure (Buckets, Crawlers, and IAM). |
| **PostgreSQL** | Row-oriented storage used to benchmark transactional vs. analytical workloads. |

---

## 🚀 Project Implementation & Architecture

### **The Pipeline Summary**

I developed an automated storage architecture that optimizes for both cost and query speed. The pipeline ingests raw JSON data into an S3 Landing Zone, transforms it into an optimized columnar Parquet format using AWS Glue, and provides immediate SQL access via Amazon Athena. I also benchmarked query performance across different storage engines to quantify the advantages of columnar storage for analytical workloads.

### **Workflow Breakdown**

1. **Benchmarking & Storage Selection**:
* Compared **PostgreSQL** (Row-oriented) and **Amazon Redshift** (Column-oriented) using the TPCH benchmark.
* Quantified how columnar storage reduces disk I/O for analytical aggregations (e.g., calculating average price across millions of rows).


2. **Infrastructure as Code (IaC)**:
* Managed the entire storage stack using **Terraform**, ensuring modularity through a `modules/` directory structure.
* Automated S3 bucket creation, Glue ETL job definitions, and IAM policy assignments.


3. **Graph & Vector Search**:
* Used **Neo4j** to model complex relationship data (Airports and Routes).
* Implemented **Vector Search** to find "nearest neighbors" in a dataset, bridging the gap between traditional databases and AI/ML applications.


4. **Data Lake to Athena**:
* Configured **AWS Glue Crawlers** to automatically infer schema and populate the Data Catalog.
* Used **Amazon Athena** to run ad-hoc SQL queries directly on S3 data, effectively implementing a serverless query layer.

---