# DeepLearning.AI Data Engineering Professional Certificate
---

## 🗂️ Repository Structure

```
deeplearning-ai-data-engineering-certificate/
├── module1/                   # Course 1: Introduction to Data Engineering
│   ├── week2/                 # ETL Pipeline Assignment
│   ├── week3/                 # Good Data Architecture Assignment
│   ├── week4/                 # Batch & Streaming Pipelines Assignment
│   └── README.md              # module 1 summary
│
├── module2/                   # Course 2: Source Systems & Data Ingestion
│   ├── week1/                 # Database Connectivity Troubleshooting
│   ├── week2/                 # Batch Data Processing from API
│   ├── week3/                 # Data Quality with Great Expectations
│   ├── week4/                 # Advanced Airflow ML Pipeline
│   └── README.md              # Module 2 summary
│
├── module3/                   # Course 3: Data Transformation
│   ├── week1/                 # Graph Databases & Vector Search
│   ├── week2/                 # Data Lakehouse - AWS and Apache
│   ├── week3/                 # Advanced SQL queries
│   └── README.md              # Module 3 summary 
│
├── module4/                   # Course 4: Data Serving
│   ├── week1/                 # dbt & Star Schema
│   ├── week2/                 # Modelling and Transformation for ML
│   └── week3/                 # CaptureDataChange w. Apache Spark            
│   ├── week4/                 # dbt and superset
│   └── week5/                 # Capstone
└── README.md                   # Overall  
```

---

## Importance

### Data Engineering Fundamentals
- Data Engineering Lifecycle (Generation → Storage → Ingestion → Transformation → Serving)
- Data Architecture Principles (Security, Performance, Reliability, Scalability)
- Batch vs. Streaming Processing

### AWS Cloud Technologies
- **Compute**: EC2, Lambda (Serverless)
- **Storage**: S3 (Data Lake)
- **Databases**: RDS (MySQL, PostgreSQL), Vector Databases (pgvector)
- **ETL/Processing**: AWS Glue, Kinesis Data Streams, Kinesis Firehose
- **Analytics**: Amazon Athena
- **Monitoring**: CloudWatch
- **Networking**: VPC, Security Groups, Load Balancers
- **Infrastructure**: Terraform (IaC)

### Data Pipeline Patterns
- ETL (Extract, Transform, Load)
- ELT (Extract, Load, Transform)
- Batch Processing
- Real-time Streaming
- Lambda Architecture

### Database Applications
- Relational Databases (MySQL, PostgreSQL)
- Vector Databases for ML/AI
- Star Schema Design
- SQL Query Optimization

## 📚 Technical Milestones

### 🏗️ Module 1: Data Engineering Foundations
Focus: The Data Engineering Lifecycle, Infrastructure as Code (IaC), and AWS Fundamentals.

- ✅ Production ETL Architecture: Designed and deployed a high-availability pipeline extracting data from Amazon RDS (MySQL), transforming it via AWS Glue, and loading it into Amazon S3.
- ✅ Infrastructure as Code (IaC): Automated resource provisioning (S3, Glue Jobs, IAM roles) using Terraform, transitioning from manual console configuration to code-based management.
- ✅ MLOps & Vector Databases: Deployed inference pipelines for a recommendation system, integrating PostgreSQL + pgvector to store embeddings for RAG (Retrieval-Augmented Generation) workflows.

### 📥 Module 2: Source Systems & Ingestion
Focus: Ingestion patterns (Batch vs. Stream), Orchestration, and Data Quality.

- ✅ API Integration (Batch): Built a robust batch pipeline to ingest data from the Spotify Web API, handling OAuth2 authentication (getAuthHeader), pagination, and rate limiting.
- ✅ Streaming Architectures: Implemented real-time ingestion using Amazon Kinesis Data Streams and Firehose to deliver event data to a data lake.
- ✅ Data Quality Automation: Integrated Great Expectations to validate data. Configured S3-backed "Data Docs" to automatically generate quality reports and detect schema drift.
- ✅ Advanced Orchestration: Developed Dynamic DAGs in Apache Airflow using the TaskFlow API and BranchPythonOperator for conditional logic.
- ✅ Cloud Networking: Diagnosed and resolved EC2-to-RDS connectivity issues by configuring VPC Subnets and Security Groups.

### 🔄 Module 3: Storage & Queries
Focus: Storage Abstractions, NoSQL, and Graph Data Engineering.

- ✅ Storage Optimization: Evaluated Row vs. Columnar formats (Parquet vs. CSV) to optimize analytical query performance and storage compression.
- ✅ Graph Engineering: Mastered Neo4j and Cypher to map complex relationships. Implemented multi-hop path analysis (e.g., airport routes) and vector searches within the graph.
- ✅ Data Lakehouse Architecture: Implemented a "Medallion" architecture (Bronze/Silver/Gold) using AWS Lake Formation and Apache Iceberg for ACID transactions on the data lake.

### 🍽️ Module 4: Data Serving & Modeling (Capstone)
Focus: Dimensional Modeling, dbt, and delivering business value.

- ✅ Analytical Modeling: Transformed normalized OLTP data into a Star Schema (Fact and Dimension tables) optimized for high-performance OLAP aggregations.
- ✅ dbt (Data Build Tool): Built a modular transformation layer; defined schema.yml for automated testing (unique, not_null) and generated lineage graphs.
🏆 Capstone Project - "DeFtunes": Architected an end-to-end music streaming pipeline.
- Ingestion: Extracted from PostgreSQL and APIs.
- Transformation: Used Spark to flatten complex JSON arrays and enforce schemas
- Serving: Created Materialized Views in Amazon Redshift for low-latency analytics dashboards.