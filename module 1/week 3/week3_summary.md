# Week 3 Assignment Summary - Good Data Architecture

## Key AWS Services Used
- **EC2**: Virtual servers (instances)
- **Application Load Balancer (ALB)**: Distributes traffic across instances
- **Auto Scaling Groups**: Automatically adjusts instance count based on demand
- **CloudWatch**: Monitoring and metrics
- **Security Groups**: Virtual firewall rules
- **Launch Templates**: Instance configuration templates
- **VPC/Subnets**: Network isolation and organization

## Key Objectives

 1. **Explore and Monitor (Operational Excellence):**
 -  Access the AWS console and find the Application Load Balancer (ALB) under the EC2 service.
 - Obtain the webpage address (DNS name) from the ALB details
 - Use **AWS CloudShell** to install the open-source **Apache Benchmark** tool.
 - Simulate traffic (stress test) by running a command (e.g., sending 7,000 requests) against the web application address.
 - Monitor the **CPU Utilization** and **Networking Activities** (inbound/outbound bytes) graphs in the Monitoring tab of the Auto Scaling Group via **Amazon CloudWatch** to observe the processing of the simulated traffic.

2. **Prioritize Security (Security Pillar):**
- Verify a security flaw by accessing the webpage address using port 90 (e.g., appending `:90`), which leaks private data due to incorrect configuration
- Fix the issue by adjusting the **Security Group** associated with the **Application Load Balancer**
- Edit the inbound rules: Delete the overly permissive rule and restrict traffic to **Port 80 (HTTP)** only, sourcing from all IP addresses
- Confirm the fix by attempting to access port 90 again; the site should no longer be reachable,.

3. **Reliability (Reliability Pillar):**
- Verify the application's reliability by confirming that the Auto Scaling Group spans multiple **Availability Zones (AZs)**,. Refreshing the webpage address should show requests being processed by different EC2 instances located in different AZs,.

4. **Cost Optimization and Performance Efficiency (FinOps Pillar):**
-  Address cost optimization by modifying the **launch template** of the Auto Scaling Group,.
- Create a new launch template version to switch the instance type from the current **T3 micro** instances to the less powerful and more cost-effective **T3 nano** instances
- Terminate the currently running T3 micro instances; the ASG automatically replaces them with the new T3 nano instances to maintain the desired capacity of two,,,.

5. **Architect for Scalability (Performance Efficiency Pillar):**
- Enable automatic scaling by creating a **Target Tracking Scaling Policy** on the Auto Scaling Group.
- Set the **Metric Type** to _Application Load Balancer request count per target_ and define a threshold (Target Value, e.g., 60 requests),.
- Run a severe stress test (e.g., 1 million requests) using Apache Benchmark in CloudShell.
- Monitor the Auto Scaling Group's activity tab to observe that the policy successfully triggered the launch of **additional EC2 instances** to handle the heavy traffic load,.