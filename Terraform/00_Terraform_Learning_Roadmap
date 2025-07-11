# Terraform: Simple to Advanced Guide

## 🌍 What is Terraform?

**Terraform** is an open-source **Infrastructure as Code (IaC)** tool developed by **HashiCorp**. It allows you to define, provision, and manage cloud infrastructure using a **declarative configuration language** called **HashiCorp Configuration Language (HCL)**.

---

## 🧠 Why Use Terraform?

* ✅ Automates infrastructure provisioning and management
* ✅ Supports **multi-cloud** (AWS, Azure, GCP, etc.) and on-prem infrastructure
* ✅ Enables **version-controlled**, **auditable**, and **repeatable** environments
* ✅ Detects configuration drift using plan/apply lifecycle
* ✅ Promotes collaboration with shared **remote state backends** and **workspaces**

---

## ⚙️ Core Concepts of Terraform

### 1. **Providers**

* Interface with external platforms (e.g., AWS, Azure, GitHub, Kubernetes).
* Terraform downloads provider plugins based on declarations.
* Example:

  ```hcl
  provider "aws" {
    region = "us-west-2"
  }
  ```

### 2. **Resources**

* The fundamental building block for defining infrastructure.
* Used to manage components like compute instances, storage, networking, etc.
* Example:

  ```hcl
  resource "aws_instance" "web" {
    ami           = "ami-0c55b159cbfafe1f0"
    instance_type = "t2.micro"
  }
  ```

### 3. **Variables and Locals**

* **Variables** allow dynamic configuration inputs.
* **Locals** store calculated values for reuse.
* Example:

  ```hcl
  variable "env" {
    default = "dev"
  }

  locals {
    instance_name = "web-${var.env}"
  }
  ```

### 4. **Outputs**

* Return values after Terraform apply.
* Useful for exporting info to users or modules.
* Example:

  ```hcl
  output "instance_ip" {
    value = aws_instance.web.public_ip
  }
  ```

### 5. **State File** (`terraform.tfstate`)

* Tracks current state of infrastructure.
* Required for planning updates or deletions.
* Supports **remote backends** (S3, Azure Blob, GCS, etc.) for team use.

### 6. **Modules**

* Group of resources used together.
* Support code reuse and abstraction.
* Example module usage:

  ```hcl
  module "vpc" {
    source = "terraform-aws-modules/vpc/aws"
    name   = "my-vpc"
    cidr   = "10.0.0.0/16"
  }
  ```

### 7. **Lifecycle Rules**

* Control resource creation and destruction:

  * `create_before_destroy`
  * `prevent_destroy`
  * `ignore_changes`
* Example:

  ```hcl
  resource "aws_s3_bucket" "example" {
    bucket = "my-bucket"
    lifecycle {
      prevent_destroy = true
    }
  }
  ```

### 8. **Data Sources**

* Read data from existing infrastructure.
* Example:

  ```hcl
  data "aws_ami" "latest" {
    most_recent = true
    owners      = ["amazon"]
    filter {
      name   = "name"
      values = ["amzn2-ami-hvm-*-x86_64-gp2"]
    }
  }
  ```

### 9. **Backends**

* Define how and where Terraform stores state files.
* Supports local, S3, GCS, Azure Blob, and more.
* Example (S3 backend):

  ```hcl
  terraform {
    backend "s3" {
      bucket = "my-tf-state"
      key    = "env/dev/terraform.tfstate"
      region = "us-east-1"
    }
  }
  ```

### 10. **Workspaces**

* Allow multiple environments using the same configuration (e.g., dev, prod).
* Example commands:

  ```sh
  terraform workspace new prod
  terraform workspace select dev
  ```

### 11. **Command Summary**

| Command              | Purpose                                   |
| -------------------- | ----------------------------------------- |
| `terraform init`     | Initialize project and download providers |
| `terraform plan`     | Show what will change                     |
| `terraform apply`    | Apply infrastructure changes              |
| `terraform destroy`  | Delete managed resources                  |
| `terraform fmt`      | Format configuration files                |
| `terraform validate` | Check syntax and config validity          |
| `terraform taint`    | Mark a resource for recreation            |
| `terraform import`   | Bring existing infra under Terraform      |
| `terraform state`    | Inspect and modify state files            |

---

## 🚀 Advanced Terraform Concepts

### 🔄 Remote State Locking

* Prevents concurrent modifications to state.
* DynamoDB table used for S3 backend state locking in AWS.

### 🧪 Testing with Terratest

* Go-based framework for testing Terraform modules.
* Supports unit/integration tests of infrastructure.

### 🧩 Dependency Graph

* Terraform builds a DAG (Directed Acyclic Graph) to determine resource ordering.
* Helps avoid manual sequencing of operations.

### 🔐 Secrets Management

* Avoid secrets in `.tf` files or state.
* Use tools like:

  * AWS Secrets Manager
  * Vault by HashiCorp
  * SOPS (with Terraform provider)

### 📊 Policy as Code

* Use **Sentinel**, **OPA (Open Policy Agent)**, or **Conftest** to enforce security/compliance.
* Examples:

  * Ensure no public S3 buckets
  * Disallow large instance types

### 🔁 CI/CD Integration

* Integrate with GitHub Actions, GitLab CI/CD, Jenkins, CircleCI
* Typical CI flow:

  1. `terraform fmt -check`
  2. `terraform validate`
  3. `terraform plan`
  4. Manual or automated `terraform apply`

### 🌩 Terraform Cloud & Enterprise

* Cloud-hosted Terraform workflow platform
* Features:

  * Remote state storage
  * Policy enforcement
  * VCS integration
  * Team access control

---

## 🔐 Terraform in DevSecOps

* Integrate security tools:

  * **Checkov**: Scans `.tf` files for misconfigurations
  * **TFSec**: Lightweight static analysis
  * **KICS**: Open-source IaC security scanner
* Enforce policies with Sentinel or OPA

---

## ✅ Summary

Terraform is a powerful IaC tool suitable for single engineers to enterprise teams. Mastering both the core and advanced features equips you to build scalable, secure, and automated infrastructure systems across any environment.
