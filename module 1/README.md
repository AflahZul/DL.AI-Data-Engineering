# Module 1: Introduction to Data Engineering

**Course**: Data Engineering Foundations  
**Platform**: DeepLearning.AI on Coursera  
**Status**: ✅ Completed (99.88%)

---

## Course Overview

This module covers the fundamentals of data engineering, including the data engineering lifecycle, data architecture principles, and building end-to-end data pipelines. It is divided into week 1, 2, 3, and 4, each covering the fundamentals according to https://www.redpanda.com/guides/fundamentals-of-data-engineering

## Learning Outcomes

- **Data Engineering Lifecycle**: Understanding generation, storage, ingestion, transformation, and serving of data
- **Data Architecture**: Security, performance, reliability, and scalability principles
- **Batch Processing**: ETL pipelines with AWS Glue
- **Streaming Processing**: Real-time data pipelines with Kinesis
- **Infrastructure as Code**: Managing AWS resources with Terraform
- **Vector Databases**: Working with embeddings for ML applications

---

## 📂 Course Content

### Week 1: Introduction to Data Engineering
- **Status**: ✅ Passed
- **Description**: Covers the data engineering lifecycle, including data generation, ingestion, transformation, storage, and serving data to stakeholders. It exposes learners with on importance of gather stakeholder needs, translate them into system requirements, and design data pipelines on AWS.

### Week 2: An Example of the Data Engineering Lifecycle
- **Status**: ✅ Passed
- **Description**:  We've built an end-to-end data pipeline on AWS, focusing on extracting, transforming, and loading data from a relational database. And then implemented a star schema for data modeling to facilitate easier querying for a data analyst interested in historical purchase records.

**Key Technologies:**
- MySQL: The database system used for the Source System.
- AWS Glue: A service for data integration and ETL (Extract, Transform, Load) processes.
- Terraform: An infrastructure as code tool used to create and manage AWS resources.
- S3 (Amazon Simple Storage Service): Used for storing transformed data.
- Jupyter Notebook: A tool for performing analytical queries on the transformed data.
- AWS Wrangler: A library for interacting with AWS services, particularly for data extraction using Amazon Athena.

---
### Week 3: Good Data Architecture
- **Status**: ✅ Passed
- **Description**: We explored key aspects of good architecture, focusing on Security, Reliability, Performance Efficiency, Cost Optimization, and Scalability, by optimized a web application. Using CloudWatch,  we configured security groups, implemented auto-scaling, and monitored resources.

**Key Technologies:**

- AWS EC2: For hosting the web application and managing computing resources.
    - Security Groups
- Application Load Balancer (ALB): To distribute incoming traffic across EC2 instances.
- AWS CloudWatch: For monitoring performance metrics and resource usage.
- AWS Auto Scaling: To automatically adjust the number of EC2 instances based on traffic demand.
- Apache Benchmark: An open-source tool used for simulating traffic to the web application.

---

### Week 4: Building End-to-End Batch and Streaming Data Pipelines
- **Status**: ✅ Passed
- **Description**: We implemented a batch pipeline that serves the training data for the recommender system. Using the data, we then stored the output embeddings of the model (using Lambda) in a vector database, and finally implemented the streaming pipeline(Kinesis Firehose) that uses the trained model and the vector database (using PostgreSQL) to provide real-time product recommendations. 

**Key Technologies:**

- AWS Glue ETL: For data ingestion and transformation.
- AWS S3: For storing transformed data and model artifacts.
- AWS Lambda: For executing code in response to events, such as model inference.
- Amazon Kinesis Data Streams: For handling real-time data streams.
- Amazon Data Firehose: For loading streaming data into S3.
- Vector Database: For storing user and item embeddings for efficient retrieval.
- Terraform (Infrastructure as Code)




