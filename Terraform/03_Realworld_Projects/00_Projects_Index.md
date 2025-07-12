# 🌍 Terraform Phase 3: Real-World AWS Projects

## 🎯 Objective

Apply Terraform to create real, working AWS infrastructure components using best practices.

---

## 🔧 Prerequisites

* AWS account
* IAM user with programmatic access
* AWS CLI installed and configured (`aws configure`)
* Terraform installed (`terraform version`)

---

## 🧪 Project 1: Provision EC2 Instance

### 📁 Folder: `project-ec2-basic/`

**Files:**

* `main.tf`
* `variables.tf`
* `outputs.tf`

**Highlights:**

* Launch EC2 instance with public IP
* Tag instance with name
* Output public IP

---

## 🌐 Project 2: VPC + Subnet + Internet Gateway

### 📁 Folder: `project-vpc-basic/`

**Highlights:**

* Create custom VPC
* Create public subnet
* Attach internet gateway
* Route table setup

**Outcome:** Your own VPC network ready for EC2 or services

---

## 🪣 Project 3: Deploy Static Website to S3

### 📁 Folder: `project-s3-website/`

**Highlights:**

* Create an S3 bucket
* Enable static website hosting
* Upload HTML index file using Terraform `local-exec`

**Outcome:** Publicly accessible static site via S3 URL

---

## ☸️ Project 4: EKS Cluster with Terraform

### 📁 Folder: `project-eks-cluster/`

**Highlights:**

* Use `terraform-aws-eks` module
* Create EKS cluster and node group
* Output `kubeconfig`
* Deploy simple app to test cluster

**Outcome:** Production-grade Kubernetes cluster ready for workloads

---

## 📦 Project 5: Multi-Tier Architecture (Web + DB)

### 📁 Folder: `project-multitier/`

**Highlights:**

* 1 EC2 instance in public subnet (web server)
* 1 RDS instance in private subnet (PostgreSQL/MySQL)
* Security groups to allow only app → DB traffic
* Output connection string

**Outcome:** Deploy app-tier to frontend and securely connect to DB

---

## 🔄 Automation Add-ons (Optional for Each Project)

* Use remote backend (S3 + DynamoDB lock)
* Create modules for reusability
* Use `.tfvars` and multiple environments (`dev`, `prod`)
* Add GitHub Actions pipeline

---

## 📌 Summary Table

| Project # | Title                     | Focus                            |
| --------- | ------------------------- | -------------------------------- |
| 1         | EC2 Instance Provisioning | Compute                          |
| 2         | VPC & Networking          | Networking basics                |
| 3         | Static Website on S3      | Serverless web hosting           |
| 4         | EKS Kubernetes Cluster    | Container orchestration          |
| 5         | Multi-Tier App (Web + DB) | Real app deployment architecture |

---
