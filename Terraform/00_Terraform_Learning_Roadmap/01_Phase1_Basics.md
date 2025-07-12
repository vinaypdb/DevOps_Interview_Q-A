# 🌱 Terraform Phase 1: Basics

## 🎯 Objective

Understand the fundamentals of Terraform—its core building blocks, usage, and a simple project example.

---

## 🔍 What is Terraform?

Terraform is an open-source Infrastructure as Code (IaC) tool created by HashiCorp. It allows you to define cloud and infrastructure resources in declarative configuration files and provision them automatically.

---

## 🆚 Terraform vs Other IaC Tools

| Tool               | Type        | Cloud Support                        |
| ------------------ | ----------- | ------------------------------------ |
| Terraform          | Declarative | Multi-cloud (AWS, GCP, Azure, etc.)  |
| AWS CloudFormation | Declarative | AWS only                             |
| Ansible            | Imperative  | Multi-cloud (good for configuration) |

---

## ⚙️ Key Terraform Concepts

### 🔸 Providers

A provider defines which platform (e.g., AWS, Azure) Terraform will interact with.

```hcl
provider "aws" {
  region = "us-east-1"
}
```

### 🔸 Resources

Resources are the basic building blocks—things like EC2 instances, S3 buckets, etc.

```hcl
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}
```

### 🔸 Variables

Let you parameterize Terraform configuration.

```hcl
variable "region" {
  default = "us-east-1"
}
```

### 🔸 Output

Used to display useful info after deployment.

```hcl
output "instance_ip" {
  value = aws_instance.example.public_ip
}
```

---

## 🛠️ Basic Terraform Workflow

1. **terraform init** → Initialize the project directory
2. **terraform plan** → Preview the infrastructure to be created
3. **terraform apply** → Apply the changes
4. **terraform destroy** → Tear down the infrastructure

---

## 📁 Example: Launch an EC2 Instance

### 🔧 Folder Structure

```
terraform-ec2-demo/
├── main.tf
├── variables.tf
├── outputs.tf
```

### 📄 main.tf

```hcl
provider "aws" {
  region = var.region
}

resource "aws_instance" "example" {
  ami           = var.ami
  instance_type = var.instance_type
  tags = {
    Name = "TerraformInstance"
  }
}
```

### 📄 variables.tf

```hcl
variable "region" {
  default = "us-east-1"
}

variable "ami" {
  default = "ami-0c55b159cbfafe1f0"
}

variable "instance_type" {
  default = "t2.micro"
}
```

### 📄 outputs.tf

```hcl
output "instance_id" {
  value = aws_instance.example.id
}

output "instance_public_ip" {
  value = aws_instance.example.public_ip
}
```

### ▶️ Commands to Run

```bash
terraform init
terraform plan
terraform apply
terraform destroy  # when done
```

---

## 📌 Tips

* All files must end with `.tf`
* `.terraform/` and `terraform.tfstate` are auto-generated
* Use `.tfvars` file to pass variables dynamically

---

## ✅ Summary

| Concept                         | Covered |
| ------------------------------- | ------- |
| Terraform installation          | ✔️      |
| Providers, resources, variables | ✔️      |
| Init, plan, apply, destroy      | ✔️      |
| Hands-on EC2 demo               | ✔️      |

---

