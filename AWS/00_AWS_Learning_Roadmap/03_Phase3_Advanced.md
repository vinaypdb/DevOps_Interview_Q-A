**AWS Phase 3: Advanced Topics**

---

## 🚀 Objective

To master advanced AWS services and architectural practices including serverless computing, containers, DevOps tooling, database optimization, and cloud security. This phase prepares you to build enterprise-grade applications and optimize for performance, security, and cost.

---

## ✅ Topics Covered

### 1. **Databases in AWS (Advanced Use)**

#### a. Amazon RDS

* Multi-AZ deployments for high availability
* Read Replicas for scaling reads
* Automated backups and snapshots
* Performance Insights

#### b. Amazon Aurora

* High-performance managed database compatible with MySQL/PostgreSQL
* Auto-scaling storage and global database support

#### c. DynamoDB Advanced

* On-demand vs Provisioned throughput
* Global Tables for multi-region apps
* DynamoDB Streams for real-time processing

#### Hands-on:

* Enable Multi-AZ in RDS
* Set up DynamoDB Global Tables and Streams

---

### 2. **Serverless Architecture**

#### a. AWS Lambda

* Event-driven compute service
* Supports Node.js, Python, Java, Go, etc.
* Triggered by S3, API Gateway, CloudWatch, DynamoDB

#### b. Amazon API Gateway

* Build and manage RESTful APIs
* Supports request validation, throttling, and authorization

#### c. EventBridge & Step Functions

* Serverless event bus for app integration
* Workflow automation across AWS services

#### Hands-on:

* Build a REST API using API Gateway + Lambda
* Connect S3 uploads to trigger Lambda

---

### 3. **Containers in AWS**

#### a. Amazon ECS (Elastic Container Service)

* Orchestrates Docker containers
* Fargate mode: Serverless container hosting

#### b. Amazon EKS (Elastic Kubernetes Service)

* Managed Kubernetes service
* Run and scale Kubernetes workloads

#### c. Amazon ECR (Elastic Container Registry)

* Private Docker image repository

#### Hands-on:

* Push Docker image to ECR
* Deploy app to ECS (Fargate)
* Explore EKS cluster setup

---

### 4. **DevOps & CI/CD on AWS**

#### a. CodeCommit

* Git-based version control

#### b. CodeBuild

* Compile code, run tests, build artifacts

#### c. CodeDeploy

* Automate EC2, Lambda, or ECS deployments

#### d. CodePipeline

* CI/CD pipeline orchestration

#### Hands-on:

* Create CI/CD pipeline using CodeCommit → CodeBuild → CodeDeploy
* Deploy updates to ECS or Lambda automatically

---

### 5. **Security Services (Advanced)**

#### a. KMS (Key Management Service)

* Manage encryption keys

#### b. AWS WAF (Web Application Firewall)

* Protect apps from SQL injection, XSS, etc.

#### c. AWS Shield

* DDoS protection

#### d. Secrets Manager & Parameter Store

* Securely store and access secrets, configs

#### Hands-on:

* Encrypt S3 bucket using KMS
* Set up WAF rules for ALB

---

### 6. **High Availability & Disaster Recovery**

#### a. Multi-Region Architecture

* Replicate data across regions
* Route 53 for failover routing

#### b. Backup & Restore

* Use AWS Backup, snapshots, and S3 versioning

#### c. DR Strategies

* Backup & Restore, Pilot Light, Warm Standby, Multi-Site

#### Hands-on:

* Configure Route 53 for failover
* Use AWS Backup to automate backups

---

### 7. **Cost Optimization**

#### a. Cost Explorer & Budgets

* Visualize and control cloud spending

#### b. Pricing Models

* On-Demand, Reserved, Spot Instances

#### c. Trusted Advisor

* Cost, performance, security recommendations

#### Hands-on:

* Analyze cost usage with Cost Explorer
* Set budget alerts

---

## ⚙️ Projects to Build

1. **Serverless Web App**

   * S3 static frontend + API Gateway + Lambda + DynamoDB

2. **Microservices on ECS/EKS**

   * Use ECR for container images
   * Deploy with CodePipeline

3. **CI/CD Pipeline with Infra-as-Code**

   * CodeCommit + Terraform + CodePipeline

4. **Secure App Deployment**

   * Enable WAF, Shield, and KMS

---
