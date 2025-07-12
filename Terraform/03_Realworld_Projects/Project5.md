

## 📦 Project 5: Multi-Tier Architecture (Web + DB)

### 📁 Folder: `project-multitier/`

**Goal:** Deploy a secure multi-tier architecture with a web server and a private database instance.

### 🔧 Components:

* VPC with public and private subnets
* Internet Gateway for public access
* NAT Gateway for private subnet internet access
* EC2 instance in public subnet (e.g., Nginx/Flask app)
* RDS instance in private subnet (PostgreSQL)
* Security Groups:

  * Web SG allows SSH & HTTP from internet
  * DB SG allows traffic only from Web SG

### 📄 main.tf (Simplified Sample)

```hcl
provider "aws" {
  region = var.region
}

module "vpc" {
  source = "terraform-aws-modules/vpc/aws"
  name = "multitier-vpc"
  cidr = "10.0.0.0/16"

  azs             = ["us-east-1a", "us-east-1b"]
  public_subnets  = ["10.0.1.0/24", "10.0.2.0/24"]
  private_subnets = ["10.0.3.0/24", "10.0.4.0/24"]

  enable_nat_gateway = true
  single_nat_gateway = true
  enable_dns_hostnames = true
}

resource "aws_security_group" "web_sg" {
  vpc_id = module.vpc.vpc_id
  name   = "web-sg"

  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

resource "aws_security_group" "db_sg" {
  vpc_id = module.vpc.vpc_id
  name   = "db-sg"

  ingress {
    from_port       = 5432
    to_port         = 5432
    protocol        = "tcp"
    security_groups = [aws_security_group.web_sg.id]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

resource "aws_instance" "web" {
  ami           = var.web_ami
  instance_type = var.web_instance_type
  subnet_id     = module.vpc.public_subnets[0]
  vpc_security_group_ids = [aws_security_group.web_sg.id]
  key_name      = var.key_pair

  user_data = file("user_data.sh")
  tags = {
    Name = "web-server"
  }
}

resource "aws_db_instance" "postgres" {
  identifier         = "webapp-db"
  engine             = "postgres"
  instance_class     = "db.t3.micro"
  allocated_storage  = 20
  name               = "appdb"
  username           = var.db_user
  password           = var.db_password
  vpc_security_group_ids = [aws_security_group.db_sg.id]
  db_subnet_group_name   = aws_db_subnet_group.db_subnet_group.name
  skip_final_snapshot    = true
  publicly_accessible    = false
}

resource "aws_db_subnet_group" "db_subnet_group" {
  name       = "db-subnet-group"
  subnet_ids = module.vpc.private_subnets
}
```

### 📄 variables.tf

```hcl
variable "region" { default = "us-east-1" }
variable "web_ami" { default = "ami-0c55b159cbfafe1f0" } # Amazon Linux 2
variable "web_instance_type" { default = "t2.micro" }
variable "key_pair" { default = "your-keypair-name" }
variable "db_user" { default = "postgres" }
variable "db_password" { default = "YourSecurePassword123" }
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

* Multi-tier architecture with isolated DB
* Web server in public subnet
* RDS in private subnet, not publicly accessible
* Secure and production-grade foundational setup

---

## 🔄 Automation Add-ons (Optional for Each Project)

* Use remote backend (S3 + DynamoDB lock)
* Create modules for reusability
* Use `.tfvars` and multiple environments (`dev`, `prod`)
* Add GitHub Actions pipeline

---


