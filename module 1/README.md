# Module 1: Introduction to Data Engineering

**Course**: Data Engineering Foundations  
**Platform**: DeepLearning.AI on Coursera  
**Status**: ✅ Completed

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

**Key Technologies:**
- ✅MySQL: The database system used for the Source System.
- ✅AWS Glue: A service for data integration and ETL (Extract, Transform, Load) processes.
- ✅Terraform: An infrastructure as code tool used to create and manage AWS resources.
- ✅S3 (Amazon Simple Storage Service): Used for storing transformed data.
- ✅Jupyter Notebook: A tool for performing analytical queries on the transformed data.
- ✅AWS Wrangler: A library for interacting with AWS services, particularly for data extraction using Amazon Athena.
- ✅AWS EC2: For hosting the web application and managing computing resources.
    - Security Groups
- ✅Application Load Balancer (ALB): To distribute incoming traffic across EC2 instances.
- ✅AWS CloudWatch: For monitoring performance metrics and resource usage.
- ✅AWS Auto Scaling: To automatically adjust the number of EC2 instances based on traffic demand.
- ✅Apache Benchmark: An open-source tool used for simulating traffic to the web application.
- ✅AWS Lambda: For executing code in response to events, such as model inference.
- ✅Amazon Kinesis Data Streams: For handling real-time data streams.
- ✅Amazon Data Firehose: For loading streaming data into S3.
- ✅Vector Database: For storing user and item embeddings for efficient retrieval.
- ✅Terraform (Infrastructure as Code)

---

### Overall Module courses
- **Description**: We explored the key concepts of data engineering and what is a good data architecture. In week 2, we built an ETL pipeline using AWS Glue to extract data from MySQL (RDS), transform it into a star schema, and load it into S3. We then queried the data using Amazon Athena and created visualizations in Jupyter Notebook. In week 4, we implemented a batch pipeline that feed the training data into the recommender system. Using the data, we then stored the output embeddings using Lambda in a vector database, and finally implemented the streaming pipeline using Kinesis Firehose. It then uses the trained model and the vector database using PostgreSQL to provide real-time product recommendations. 






