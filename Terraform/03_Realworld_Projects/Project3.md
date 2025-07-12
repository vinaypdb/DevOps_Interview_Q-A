
## 🪣 Project 3: Deploy Static Website to S3

### 📁 Folder: `project-s3-website/`

**Files:**

* `main.tf`
* `variables.tf`
* `index.html` (optional)

### 📄 main.tf

```hcl
provider "aws" {
  region = var.region
}

resource "aws_s3_bucket" "website" {
  bucket = var.bucket_name
  acl    = "public-read"

  website {
    index_document = "index.html"
    error_document = "index.html"
  }

  tags = {
    Name        = "static-site"
    Environment = "dev"
  }
}

resource "aws_s3_bucket_public_access_block" "block" {
  bucket = aws_s3_bucket.website.id

  block_public_acls       = false
  block_public_policy     = false
  ignore_public_acls      = false
  restrict_public_buckets = false
}

resource "aws_s3_bucket_policy" "public_read" {
  bucket = aws_s3_bucket.website.id

  policy = jsonencode({
    Version = "2012-10-17",
    Statement = [
      {
        Sid       = "PublicReadGetObject",
        Effect    = "Allow",
        Principal = "*",
        Action    = "s3:GetObject",
        Resource  = "${aws_s3_bucket.website.arn}/*"
      }
    ]
  })
}

resource "null_resource" "upload_index" {
  provisioner "local-exec" {
    command = "aws s3 cp index.html s3://${aws_s3_bucket.website.id}/index.html"
  }
}
```

### 📄 variables.tf

```hcl
variable "region" {
  default = "us-east-1"
}

variable "bucket_name" {
  default = "terraform-static-site-pdb"
}
```

### 📄 index.html (example)

```html
<html>
  <head><title>My Terraform Site</title></head>
  <body><h1>Hello from S3!</h1></body>
</html>
```

### ▶️ Run the Project

```bash
terraform init
terraform apply
```

### 🧹 Cleanup

```bash
terraform destroy
```

### ✅ Output

* S3 bucket created and configured for website hosting
* Publicly accessible via:

```bash
echo "http://$(terraform output -raw bucket_name).s3-website-$(terraform output -raw region).amazonaws.com"
```

---

