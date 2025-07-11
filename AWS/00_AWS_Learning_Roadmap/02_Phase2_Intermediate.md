**AWS Phase 2: Intermediate Concepts**

---

## 💡 Objective

To deepen your understanding of AWS by focusing on identity management, networking, compute scaling, and monitoring. This phase introduces practical skills required to build secure, scalable, and production-ready cloud architectures.

---

## ✅ Topics Covered

### 1. **IAM (Identity and Access Management)**

IAM is the backbone of security in AWS, allowing you to control who can do what in your account.

#### a. IAM Components

* **Users**: Individual identities (with credentials) for people or apps
* **Groups**: Collection of IAM users with common permissions
* **Roles**: Used for temporary access, especially for AWS services (e.g., EC2 assuming a role)
* **Policies**: JSON documents defining permissions (Allow/Deny actions)

#### b. Best Practices

* Use least privilege access
* Enable MFA (Multi-Factor Authentication)
* Avoid using root user for daily tasks

#### c. Hands-on

* Create IAM users with programmatic and console access
* Attach policies (e.g., AmazonS3ReadOnlyAccess)
* Create a role and attach it to an EC2 instance

---

### 2. **Amazon EC2 Advanced Configuration**

Amazon EC2 offers deep customization for compute resources.

#### a. Key Concepts

* **AMI**: Custom images with pre-installed software
* **User Data Scripts**: Used for boot-time automation (install packages, configure apps)
* **EBS Volumes**: Persistent storage attached to EC2

#### b. Hands-on

* Launch EC2 with custom AMI
* Add EBS volume
* Use User Data to install Apache server on launch

---

### 3. **Amazon S3 Deep Dive**

Go beyond basic file storage to manage versioning, lifecycle, and security.

#### a. Features

* **Versioning**: Keep multiple versions of objects
* **Lifecycle Rules**: Transition objects to Glacier or delete after a time
* **Bucket Policies**: Control access at the bucket level

#### b. Hands-on

* Enable versioning on a bucket
* Write a lifecycle rule to archive data to Glacier
* Apply a bucket policy to allow only read access

---

### 4. **Amazon VPC Deep Dive**

Learn to design a secure and segmented network in the cloud.

#### a. Key Components

* **Subnets**: Logical segments of your VPC (Public for internet, Private for backend)
* **Internet Gateway**: Allows public subnet access to the internet
* **NAT Gateway**: Allows private subnets to reach the internet
* **Route Tables**: Rules for routing traffic
* **Security Groups & NACLs**: Virtual firewalls

#### b. Hands-on

* Create custom VPC with 2 subnets
* Configure Internet Gateway and NAT Gateway
* Set up routing tables
* Launch EC2s in both public and private subnets

---

### 5. **Elastic Load Balancing (ELB) & Auto Scaling**

Automatically manage application traffic and server capacity.

#### a. ELB Types

* **Application Load Balancer (ALB)**: For HTTP/HTTPS with path-based routing
* **Network Load Balancer (NLB)**: High-performance TCP traffic

#### b. Auto Scaling

* Define Launch Templates and Auto Scaling Groups (ASGs)
* Scale based on CPU usage, schedule, or demand

#### c. Hands-on

* Set up ALB for EC2 instances
* Create an Auto Scaling Group with minimum and maximum capacity

---

### 6. **Monitoring and Logging**

Track application performance, set alarms, and audit user actions.

#### a. Amazon CloudWatch

* **Metrics**: Monitor CPU, network, memory
* **Logs**: Centralized logging for EC2 and Lambda
* **Alarms**: Trigger notifications or scaling actions

#### b. AWS CloudTrail

* Records all API calls for auditing

#### c. Hands-on

* Monitor EC2 metrics with CloudWatch
* Create alarm for high CPU usage
* View API logs in CloudTrail

---

## ⚙️ Hands-on Projects

### 1. **2-Tier Architecture Deployment**

* Frontend EC2 (public subnet)
* Backend RDS (private subnet)
* Security groups to allow HTTP/DB access

### 2. **Custom VPC Setup**

* Full VPC with NAT, IGW, route tables
* Launch EC2 instances in multiple AZs

### 3. **Auto Scaling + ELB**

* Launch scalable EC2 group behind an ALB
* Observe automatic scaling behavior

---
