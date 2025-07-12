
## ☸️ Project 4: EKS Cluster with Terraform

### 📁 Folder: `project-eks-cluster/`

**Highlights:**

* Use `terraform-aws-eks` official module
* Deploy EKS cluster with worker nodes
* Generate kubeconfig for `kubectl`
* Validate cluster by deploying NGINX

### 📄 Files:

* `main.tf`
* `variables.tf`
* `outputs.tf`

### 📄 main.tf

```hcl
provider "aws" {
  region = var.region
}

module "eks" {
  source          = "terraform-aws-modules/eks/aws"
  cluster_name    = var.cluster_name
  cluster_version = "1.27"
  subnets         = var.subnet_ids
  vpc_id          = var.vpc_id

  node_groups = {
    eks_nodes = {
      desired_capacity = 2
      max_capacity     = 3
      min_capacity     = 1

      instance_types = ["t3.medium"]
    }
  }
}
```

### 📄 variables.tf

```hcl
variable "region" {
  default = "us-east-1"
}

variable "vpc_id" {}
variable "subnet_ids" { type = list(string) }
variable "cluster_name" { default = "pdb-eks" }
```

### 📄 outputs.tf

```hcl
output "cluster_name" {
  value = module.eks.cluster_name
}

output "kubeconfig" {
  value = module.eks.kubeconfig
}
```

### ▶️ After Deployment

Generate config and test access:

```bash
aws eks --region us-east-1 update-kubeconfig --name pdb-eks
kubectl get nodes
```

### 🧹 Cleanup

```bash
terraform destroy
```

### ✅ Output

* EKS cluster ready with 2 worker nodes
* Kubeconfig generated
* You can deploy applications using `kubectl`

---

