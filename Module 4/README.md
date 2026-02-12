# Module 4: Data Modeling, Transformation, and Serving

**Course:** Data Modeling, Transformation, and Serving + Capstone Project
**Platform:** DeepLearning.AI on Coursera
**Status:** ✅ Completed

---

## 📖 Course Overview

This final module shifts the focus from the technical "plumbing" of data engineering to **Value Creation**. The goal is to structure raw data into high-performance models that power business intelligence and machine learning. This culminates in a **Capstone Project** where I built an end-to-end music streaming analytics platform.

### 🎯 Learning Outcomes

* **Dimensional Modeling:** Designing **Star Schemas** to separate quantitative metrics (Facts) from descriptive context (Dimensions).
* **Modern Transformation:** Mastering the shift from **ETL** (AWS Glue/Spark) to **ELT** (dbt/Redshift).
* **The Semantic Layer:** Using **dbt** to define consistent business metrics and automate documentation.
* **Serving Strategies:** Implementing **Materialized Views** in Amazon Redshift to slash dashboard latency.

---

## 🚀 Capstone Project: "De Ftunes" Music Streaming

**Objective:** Build a robust, scalable pipeline to analyze user purchases and streaming habits for a growing music platform.

### **The Architecture (Medallion Pattern)**

| Stage | Technology | Purpose |
| --- | --- | --- |
| **Ingestion** | **AWS Glue & FastAPI** | Extracts raw logs from APIs and Postgres into an S3 **Bronze** layer. |
| **Transformation** | **PySpark (Glue)** | Unnests complex JSON, cleans schemas, and stores as Parquet in the **Silver** layer. |
| **Serving (Gold)** | **dbt & Redshift** | Models data into a **Star Schema** within Redshift for final analytics. |
| **Orchestration** | **Apache Airflow** | Manages the end-to-end DAG, handling retries and dependencies. |

### **The Data Model (Star Schema)**

* **fct_purchases:** The central fact table where each row represents a single song purchase. It tracks `price`, `timestamp`, and `session_id`.
* **dim_users:** Enriched with geographic and demographic data unnested from the User API.
* **dim_songs:** Descriptive metadata (artist, genre, duration) pulled from the source PostgreSQL system.
* **dim_time:** A critical dimension generated to analyze trends (daily sales, peak streaming hours).

---

## 🛠️ Key Technologies & Concepts

### **1. dbt (Data Build Tool)**

dbt acts as the "compiler" for the data warehouse. I used it to transform SQL SELECT statements into production-ready tables and views in Redshift.

* **Version Control:** All business logic is stored in Git.
* **Automated Testing:** Built-in tests ensure **Surrogate Keys** are unique and critical columns are not null.

### **2. ETL vs. ELT**

* **ETL (Extract-Transform-Load):** Used **AWS Glue (Spark)** for the heavy lifting of unnesting JSON and initial cleaning *before* the data reached the warehouse.
* **ELT (Extract-Load-Transform):** Used **dbt** inside **Redshift** to perform final business logic modeling, leveraging the warehouse's massive compute power.

### **3. Performance Tuning: Materialized Views**

To support real-time BI dashboards, I implemented **Materialized Views**. Unlike standard views, these pre-compute the results of complex joins (like `fct_purchases` joined with `dim_songs`), allowing reports to load in milliseconds rather than seconds.

---
