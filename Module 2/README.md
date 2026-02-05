# Module 2: Source Systems, Data Ingestion, and Pipelines

**Course**: Source Systems, Data Ingestion, and Pipelines 
**Platform**: DeepLearning.AI on Coursera  
**Status**: ✅ Completed

---

## 📂 Module Structure

```
├── c2_24_lab_2_Airflow_Best_Practices
│   └── home
│       └── coder
│           └── project
│               ├── C2_W4_Lab_2_Airflow_Best_Practices.md
│               ├── scripts
│               │   └── restart_airflow.sh
│               ├── src
│               │   ├── grouped_tasks_dag.py
│               │   └── simple_dag.py
│               └── src_solution
│                   ├── grouped_tasks_dag_solution.py
│                   └── simple_dag_solution.py
├── c2_w1_lab2
│   └── home
│       └── coder
│           └── project
│               ├── C2_W1_Lab_2_DynamoDB.ipynb
│               ├── data
│               │   └── aws_sample_data
│               │       ├── Forum.json
│               │       ├── ProductCatalog.json
│               │       ├── Reply.json
│               │       └── Thread.json
│               └── images
│                   └── AWSLogout.png
├── c2_w1_lab3
│   └── project
│       ├── C2_W1_Lab_3_S3_Solution.ipynb
│       ├── C2_W1_Lab_3_S3.ipynb
│       ├── data
│       │   ├── csv
│       │   │   └── ratings_ml_training_dataset.csv
│       │   └── json
│       │       └── delivery-stream-one-record.json
│       ├── downloads
│           └── delivery-stream-one-record.json
├── c2_w2
│   └── project
│       ├── C2_W2_Assignment.ipynb
│       ├── images
│       │   └── VSCodeCourseraTerminal.png
│       ├── notes.md
│       └── src
│           ├── __pycache__
│           │   ├── authentication.cpython-312.pyc
│           │   └── endpoint.cpython-312.pyc
│           ├── album_items_2025-12-14T16:24:29Z.json
│           ├── authentication.py
│           ├── endpoint.py
│           ├── env
│           └── main.py
├── c2_w2_lab
│   └── project
│       ├── C2_W2_Lab_1_Streaming_Ingestion.ipynb
│       ├── data
│       │   └── example_record.json
│       ├── src
│       │   ├── cli
│       │   │   ├── consumer_from_cli.py
│       │   │   ├── consumer.log
│       │   │   ├── producer_from_cli.py
│       │   │   └── producer.log
│       │   └── etl
│       │       ├── consumer.log
│       │       └── consumer.py
│       └── src_solution
│           └── etl
│               └── consumer.py
├── c2_w3 assignment great expectations
│   └── project
│       ├── C2_W3_Assignment.ipynb
│       ├── gx
│       │   ├── expectations
│       │   ├── great_expectations.yml
│       │   ├── plugins
│       │   │   └── custom_data_docs
│       │   │       └── styles
│       │   │           └── data_docs_custom_styles.css
│       │   └── uncommitted
│       │       ├── config_variables.yml
│       │       └── validations
│       └── scripts
│           └── setup.sh
├── c2_w3 terraform practice lab
│   └── project
│       ├── C2_W3_Lab_1_Terraform.md
│       ├── terraform
│       │   ├── backend.tf
│       │   ├── main.tf
│       │   ├── modules
│       │   │   └── bastion_host
│       │   │       ├── ec2.tf
│       │   │       ├── iam_roles.tf
│       │   │       ├── network.tf
│       │   │       ├── outputs.tf
│       │   │       ├── policies.tf
│       │   │       ├── providers.tf
│       │   │       ├── rds.tf
│       │   │       └── variables.tf
│       │   ├── outputs.tf
│       │   ├── terraform.tfvars
│       │   └── variables.tf
│       └── terraform_solution
│           ├── modules
│           │   └── bastion_host
│           │       ├── ec2.tf
│           │       ├── network.tf
│           │       ├── outputs.tf
│           │       ├── rds.tf
│           │       └── variables.tf
│           └── variables.tf
├── c2_w4 Building an Advanced Data Pipeline With Data Quality Checks
│   ├── project
│   │   ├── C2_W4_Assignment.md
│   │   ├── data
│   │   │   └── work_zone
│   │   │       └── data_science_project
│   │   │           ├── datasets
│   │   │           │   ├── alitran
│   │   │           │   │   ├── test.parquet
│   │   │           │   │   └── train.parquet
│   │   │           │   ├── easy_destiny
│   │   │           │   │   ├── test.parquet
│   │   │           │   │   └── train.parquet
│   │   │           │   └── to_my_place_ai
│   │   │           │       ├── test.parquet
│   │   │           │       └── train.parquet
│   │   │           ├── test.parquet
│   │   │           └── train.parquet
│   │   ├── scripts
│   │   │   └── restart_airflow.sh
│   │   └── src
│   │       ├── dags
│   │       │   ├── model_trip_duration_alitran.py
│   │       │   ├── model_trip_duration_easy_destiny.py
│   │       │   └── model_trip_duration_to_my_place_ai.py
│   │       ├── model_trip_duration_easy_destiny.py
│   │       └── templates
│   │           ├── dag_configs
│   │           │   ├── config_alitran.json
│   │           │   ├── config_easy_destiny.json
│   │           │   └── config_to_my_place_ai.json
│   │           ├── generate_dags.py
│   │           └── template.py
├── c2_w4 lab 1 -Airflow 101 - Building your First Data Pipeline
│   └── project
│       ├── C2_W4_Lab_1_Airflow101.md
│       ├── scripts
│       │   └── restart_airflow.sh
│       ├── src
│       │   └── user_sessions.py
│       └── src_solution
│           └── user_sessions.py
├── c2w1
│   └── project
│       ├── C2_W1_Assignment.md
│       │   └── download_from_s3.py
│       └── sql
│           ├── copy_data.sql
│           └── ratings_table_ddl.sql
└── README.md
```

---
### Data Pipeline Orchestration
- ✅ Apache Airflow DAG creation
- ✅ TaskFlow API with decorators
- ✅ Workflow dependency management
- ✅ Error handling and retries

### Data Quality Engineering
- ✅ Great Expectations framework
- ✅ Data validation rules
- ✅ Quality check automation
- ✅ Fail-fast strategies

### ML Pipeline Development
- ✅ Model training orchestration
- ✅ Performance evaluation
- ✅ Conditional deployment
- ✅ XCom for metrics passing

### Advanced Patterns
- ✅ Dynamic DAG generation
- ✅ Template-based development
- ✅ Multi-environment support
- ✅ DRY principle application

### AWS Cloud Services
- ✅ EC2 instance management
- ✅ RDS database connectivity
- ✅ VPC and networking
- ✅ Security group configuration

---

## 🔗 Related Resources

- [Apache Airflow Documentation](https://airflow.apache.org/docs/)
- [Great Expectations Docs](https://docs.greatexpectations.io/)
- [TaskFlow API Guide](https://airflow.apache.org/docs/apache-airflow/stable/tutorial/taskflow.html)
