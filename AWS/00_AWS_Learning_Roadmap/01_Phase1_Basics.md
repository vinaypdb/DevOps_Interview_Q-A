**AWS Phase 1: Fundamentals (Beginner Level)**

---

## 💼 Objective

To build a strong foundation in AWS by understanding essential cloud concepts, AWS architecture, and practical applications of key services through real-world examples and hands-on labs.

---

## ✅ Topics Covered

### 1. **Introduction to Cloud Computing**

Cloud computing delivers computing services over the internet, allowing users to access servers, storage, databases, and other services on demand without owning physical hardware.

#### a. Cloud Service Models

* **IaaS (Infrastructure as a Service)**: Provides raw infrastructure such as virtual machines, networking, and storage. You manage the OS, applications, and data.
  *Example: Amazon EC2*

* **PaaS (Platform as a Service)**: Offers a platform to develop, test, and deploy applications without managing the underlying hardware.
  *Example: AWS Elastic Beanstalk*

* **SaaS (Software as a Service)**: Delivers software applications over the internet on a subscription basis. Everything is managed by the provider.
  *Example: Gmail, Dropbox*

#### b. Cloud Deployment Models

* **Public Cloud**: Cloud resources are owned and operated by third-party providers and delivered over the internet.
  *Example: AWS*

* **Private Cloud**: Dedicated infrastructure used by a single organization, either on-premise or hosted by a third party.

* **Hybrid Cloud**: Combines public and private clouds to allow data and applications to move between them for flexibility and optimization.

---

### 2. **What is AWS?**

Amazon Web Services (AWS) is the leading cloud platform, offering over 200 fully featured services from data centers globally. AWS helps businesses scale quickly and cost-effectively.

#### a. Global Infrastructure Components

* **Regions**: Physical locations worldwide where AWS clusters data centers. Each region is isolated for availability and compliance.
  *Example: us-east-1 (N. Virginia)*

* **Availability Zones (AZs)**: Multiple isolated data centers within a region that provide high availability and fault tolerance.

* **Edge Locations**: Used by CloudFront (AWS CDN) to cache content closer to users globally, improving performance.

#### b. Shared Responsibility Model

* **AWS's Responsibility**: Securing the underlying infrastructure (hardware, software, networking, and facilities).
* **Your Responsibility**: Managing the security of your data, identities, applications, and access controls.

---

### 3. **Core AWS Services Overview**

Get introduced to the foundational building blocks of AWS:

#### a. Compute: **Amazon EC2**

* Provides resizable compute capacity (virtual machines) in the cloud.
* Key Concepts:

  * **AMI** (Amazon Machine Image): Template for your instance
  * **Instance Types**: Define compute/memory capacity (e.g., t2.micro)
  * **Security Groups**: Virtual firewalls for instances
  * **Key Pairs**: SSH authentication for login

#### b. Storage: **Amazon S3 (Simple Storage Service)**

* Object-based storage ideal for backups, media files, logs, etc.
* Key Features:

  * Durability (99.999999999%)
  * Versioning and Lifecycle Rules
  * Public/Private Access Control

#### c. Networking: **Amazon VPC (Virtual Private Cloud)**

* Allows creation of logically isolated networks within AWS.
* Key Components:

  * **Subnets** (public/private)
  * **Route Tables** (define traffic rules)
  * **Internet Gateway** (for internet access)
  * **NAT Gateway** (for private instances to reach the internet)

#### d. Database: **Amazon RDS & DynamoDB**

* **RDS (Relational Database Service)**:

  * Managed SQL databases like MySQL, PostgreSQL, Oracle
  * Supports Multi-AZ deployment for high availability

* **DynamoDB**:

  * Fully managed NoSQL key-value/document database
  * Offers single-digit millisecond performance at any scale

---

## ⚖️ Hands-on Labs

### 1. **Create a Free AWS Account**

* Visit: [https://aws.amazon.com/free](https://aws.amazon.com/free)
* Sign up with email and billing info (credit/debit card)
* Set up basic security with MFA (multi-factor authentication)
* Configure billing alerts to monitor usage

### 2. **Launch an EC2 Instance**

* Go to EC2 Dashboard
* Choose Amazon Linux AMI
* Select instance type: `t2.micro` (free tier)
* Create key pair and download it (PEM file)
* Configure security group to allow SSH (port 22)
* Launch instance and connect using SSH from terminal

### 3. **Upload a File to S3**

* Open S3 service and create a bucket (name must be globally unique)
* Upload a text or image file
* Set permissions for public access (if testing access)
* Copy and open the object URL to verify

### 4. **Create a Basic VPC**

* Go to VPC Wizard
* Create VPC with CIDR block `10.0.0.0/16`
* Add a public subnet (`10.0.1.0/24`)
* Attach Internet Gateway
* Add route to route table: `0.0.0.0/0` -> Internet Gateway
* Launch EC2 instance inside your VPC

---
