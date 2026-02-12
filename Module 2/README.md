# Module 2: Source Systems, Data Ingestion, and Pipelines

**Course:** Source Systems, Data Ingestion, and Pipelines

**Platform:** DeepLearning.AI on Coursera

**Status:** ✅ Completed

---

## 📖 Course Overview

This module transitions from theory to the practical implementation of the data engineering lifecycle. It focuses on how data moves from diverse source systems (SQL, NoSQL, APIs) into the cloud through both batch and streaming patterns, while emphasizing the "undercurrents" of orchestration, monitoring, and DataOps.

### 🎯 Learning Outcomes

* **Ingestion Patterns:** Implementing both **Batch** (ETL/ELT) and **Streaming** (Real-time) pipelines on AWS.
* **Orchestration:** Using **Apache Airflow** to automate complex workflows and manage task dependencies.
* **Data Quality (DataOps):** Integrating the **Great Expectations** framework to validate data and prevent "silent failures" in production.
* **Cloud Infrastructure:** Troubleshooting VPC networking, database connectivity, and managing resources using **Terraform**.

---

## 🛠️ Key Technologies

| Technology | Role in Project |
| --- | --- |
| **Apache Airflow** | Orchestrating workflows using the TaskFlow API and DAGs. |
| **Great Expectations** | Defining and automating data validation rules (expectations). |
| **Amazon Kinesis** | Handling real-time streaming ingestion and delivery. |
| **Amazon DynamoDB** | Interacting with NoSQL data sources for high-performance retrieval. |
| **Terraform** | Automating the deployment of VPCs, EC2s, and RDS instances. |
| **Pandas / Parquet** | Data manipulation and optimized storage formats for analytics. |

---

## 🚀 Project Implementation & Architecture

### **The Pipeline Summary**

I built a production-grade data ecosystem that ingests data from multiple sources (RDS MySQL, DynamoDB, and external APIs). The system uses Airflow to manage the flow of data through a "Medallion-like" architecture, moving from raw landing zones to processed work zones while ensuring every step meets strict data quality standards.

### **Workflow Breakdown**

1. **Ingestion & Networking:** * configured AWS networking (VPC, Subnets, Security Groups) to establish secure connections between EC2 bastions and RDS/S3.
* Implemented streaming ingestion using **Kinesis Data Streams** and batch ingestion from REST APIs.


2. **Orchestration & Automation:** * Developed **Airflow DAGs** to automate user session processing and model training.
* Applied **Dynamic DAG generation** and the DRY principle to scale pipeline creation across multiple projects.


3. **Data Quality & Observability:** * Integrated **Great Expectations** to catch schema drifts and null values early.
* Used **XComs** within Airflow to pass performance metrics and drive conditional logic (e.g., only deploying models that meet accuracy thresholds).

---
