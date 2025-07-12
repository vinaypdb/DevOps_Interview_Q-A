

## 🌐 Project 2: VPC + Subnet + Internet Gateway

### 📁 Folder: `project-vpc-basic/`

**Files:**

* `main.tf`
* `variables.tf`
* `outputs.tf`

### 📄 main.tf

```hcl
provider "aws" {
  region = var.region
}

resource "aws_vpc" "main" {
  cidr_block = var.vpc_cidr
  tags = {
    Name = "main-vpc"
  }
}

resource "aws_subnet" "public" {
  vpc_id            = aws_vpc.main.id
  cidr_block        = var.subnet_cidr
  map_public_ip_on_launch = true
  availability_zone = var.az
  tags = {
    Name = "public-subnet"
  }
}

resource "aws_internet_gateway" "igw" {
  vpc_id = aws_vpc.main.id
  tags = {
    Name = "main-igw"
  }
}

resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.igw.id
  }
  tags = {
    Name = "public-rt"
  }
}

resource "aws_route_table_association" "a" {
  subnet_id      = aws_subnet.public.id
  route_table_id = aws_route_table.public.id
}
```

### 📄 variables.tf

```hcl
variable "region" {
  default = "us-east-1"
}

variable "vpc_cidr" {
  default = "10.0.0.0/16"
}

variable "subnet_cidr" {
  default = "10.0.1.0/24"
}

variable "az" {
  default = "us-east-1a"
}
```

### 📄 outputs.tf

```hcl
output "vpc_id" {
  value = aws_vpc.main.id
}

output "subnet_id" {
  value = aws_subnet.public.id
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

* VPC, Subnet, Internet Gateway, and Route Table created
* Subnet publicly accessible via IGW

---

