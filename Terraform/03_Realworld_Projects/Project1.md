

## 🧪 Project 1: EC2 Instance Provisioning

### 📁 Folder: `project-ec2-basic/`

**Files:**

* `main.tf`
* `variables.tf`
* `outputs.tf`

### 📄 main.tf

```hcl
provider "aws" {
  region = var.region
}

resource "aws_instance" "example" {
  ami           = var.ami
  instance_type = var.instance_type
  tags = {
    Name = var.instance_name
  }
}
```

### 📄 variables.tf

```hcl
variable "region" {
  default = "us-east-1"
}

variable "ami" {
  default = "ami-0c55b159cbfafe1f0"  # Amazon Linux 2
}

variable "instance_type" {
  default = "t2.micro"
}

variable "instance_name" {
  default = "terraform-demo-instance"
}
```

### 📄 outputs.tf

```hcl
output "instance_id" {
  value = aws_instance.example.id
}

output "public_ip" {
  value = aws_instance.example.public_ip
}
```

### ▶️ Run the Project

```bash
terraform init
terraform plan
terraform apply
```

### 🧹 Cleanup

```bash
terraform destroy
```

### ✅ Output

* EC2 instance created in specified region
* Name tag applied
* Public IP printed after creation

---

