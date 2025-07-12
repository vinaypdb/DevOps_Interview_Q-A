# 🚀 Terraform Phase 2: Intermediate Concepts

## 🎯 Objective

Go deeper into Terraform’s power by learning how to write reusable infrastructure with modules, manage inputs/outputs, use data sources, and configure remote state storage.

---

## 🧱 Topics Covered

* Input and Output Variables
* Local Values
* Terraform Modules (Reusable Infrastructure)
* Data Sources
* Provisioners
* Remote Backend (S3 Bucket for state storage)

---

## 🔹 Input and Output Variables

### 📥 Input Variable Example (variables.tf)

```hcl
variable "instance_type" {
  type    = string
  default = "t2.micro"
}
```

### 📤 Output Variable Example (outputs.tf)

```hcl
output "instance_id" {
  value = aws_instance.example.id
}
```

You can override variables using `terraform.tfvars` or CLI:

```bash
terraform apply -var="instance_type=t2.medium"
```

---

## 🔸 Local Values

```hcl
locals {
  common_tags = {
    Environment = "dev"
    Owner       = "pdb"
  }
}

resource "aws_s3_bucket" "example" {
  bucket = "my-unique-bucket-name"
  tags   = local.common_tags
}
```

---

## 🧩 Terraform Modules (Reusable Code)

### 📁 Structure:

```
modules/
└── ec2/
    ├── main.tf
    ├── variables.tf
    └── outputs.tf

main.tf (root)
```

### 📄 Root `main.tf`

```hcl
module "web_server" {
  source        = "./modules/ec2"
  instance_type = "t2.micro"
  ami           = "ami-0c55b159cbfafe1f0"
}
```

### ✅ Benefits

* Clean separation
* Reuse code
* Easier testing & CI/CD

---

## 🔍 Data Sources

Use existing resources (not manage) in your config.

```hcl
data "aws_ami" "ubuntu" {
  most_recent = true
  owners      = ["099720109477"]  # Canonical

  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-20.04-amd64-server-*"]
  }
}

resource "aws_instance" "example" {
  ami           = data.aws_ami.ubuntu.id
  instance_type = "t2.micro"
}
```

---

## 🔧 Provisioners (Use with Caution)

Run scripts after resource creation.

```hcl
resource "aws_instance" "example" {
  # ...
  provisioner "remote-exec" {
    inline = [
      "sudo apt update",
      "sudo apt install -y nginx"
    ]
  }
}
```

⚠️ Use only when other Terraform-native methods are not possible.

---

## ☁️ Remote Backend (State in S3)

Avoid storing state locally. Store it in S3 for team access.

### 📄 backend.tf

```hcl
terraform {
  backend "s3" {
    bucket = "my-terraform-state-bucket"
    key    = "state/dev/terraform.tfstate"
    region = "us-east-1"
  }
}
```

Initialize with:

```bash
terraform init
```

---

## 📌 Summary

| Concept             | Status        |
| ------------------- | ------------- |
| Variables & Outputs | ✔️            |
| Local values        | ✔️            |
| Modules             | ✔️            |
| Data sources        | ✔️            |
| Provisioners        | ✔️ (optional) |
| Remote backend      | ✔️            |

---

