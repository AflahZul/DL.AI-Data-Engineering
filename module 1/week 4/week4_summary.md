# Week 3 Assignment Summary - Good Data Architecture

## Key AWS Services Used
- **EC2**: Virtual servers (instances)
- **Application Load Balancer (ALB)**: Distributes traffic across instances
- **Auto Scaling Groups**: Automatically adjusts instance count based on demand
- **CloudWatch**: Monitoring and metrics
- **Security Groups**: Virtual firewall rules
- **Launch Templates**: Instance configuration templates
- **VPC/Subnets**: Network isolation and organization


### **I. Foundational Setup and Source Exploration**

*   **Work/Implementation:** The primary implementation tool was **Terraform**, used to programmatically define and configure all necessary AWS resources,,,.
*   **Source Exploration:** The first step involved connecting to the provided **Amazon RDS MySQL database** to explore the source system. This database contained the classic models dataset and an additional **`ratings` table**, which was necessary as the label data for training the recommender system,,.

### **II. Batch Pipeline Implementation (Serving Training Data)**

This phase focused on creating the ETL pipeline required to produce tabular training data for the Data Scientist.

*   **Implementation:** The ETL pipeline resources were created by running Terraform commands (`init`, `plan`, `apply`) on the ETL module configuration files,.
*   **Work:** The user ensured the **AWS Glue ETL Job** configuration was correctly defined in the provided Python script (`glue_job.py`).
*   **Production/Execution:** The Glue Job was started using the AWS CLI (`aws glue start-job-run`), which extracted data from the RDS source, transformed it into the required training format, and loaded it into a dedicated S3 bucket,,.
*   **Outcome:** A new **S3 bucket** (labeled "Data Lake") was populated with the transformed training data, organized (partitioned) by customer number,,.

### **III. Vector Database Setup (Model Output)**

This phase prepared the trained model assets for use by the real-time streaming pipeline.

*   **Work:** The user explored the **S3 bucket labeled "ML Artifacts,"** which contained the pre-trained model outputs, including the **item embeddings** and **user embeddings** in CSV files,.
*   **Implementation:** A **PostgreSQL database instance** was created using Terraform configurations (the VectorDB module),.
*   **Work/Loading Embeddings:** The necessary connection details (host, username, password) were retrieved from the Terraform output,. The user then connected to the PostgreSQL instance and executed provided SQL scripts to load the item and user embeddings from the S3 ML Artifacts bucket into tables within the new **Vector Database**,,.

### **IV. Streaming Pipeline Implementation (Serving Recommendations)**

This final phase established the low-latency stream to generate and deliver real-time product recommendations.

*   **Work/Configuration:** The provided **AWS Lambda function** (Model Inference) required configuration to access the database. The user manually updated its **environmental variables** with the Vector Database hostname, username, and password,.
*   **Implementation:** The streaming workflow resources were created by running Terraform commands on the Streaming module configuration.
*   **Production:** This created the **Amazon Data Firehose** delivery service and the **Stream Transformation Lambda function**. (Note: The **Kinesis Data Streams** source and the **Recommendations S3 bucket** were pre-provided).
*   **Execution/Outcome:** The pipeline was validated: Firehose automatically reads real-time events from the Kinesis source stream, invokes the Lambda function to perform transformation and model inference against the Vector Database, and transfers the final product recommendations into the **S3 Recommendations bucket**,. The data in the recommendations bucket was verified to be partitioned by time (year, month, day, hour).
*   **Troubleshooting Note:** The lab's primary focus was on implementing and connecting these components, with explicit instructions provided for configurations like updating the Lambda environment variables for network access,, rather than extensive troubleshooting of broken network or IAM permissions.