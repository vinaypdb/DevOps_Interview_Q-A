✅ **Terraform Interview Q\&A (Comprehensive, Beginner-Friendly)**

---

### 1. **What is Terraform?**

Terraform is an open-source Infrastructure as Code (IaC) tool by HashiCorp. It lets you define cloud and on-prem resources using declarative configuration files.

---

### 2. **What is Infrastructure as Code (IaC)?**

IaC means managing infrastructure (servers, networks, etc.) through code instead of manual processes.

---

### 3. **What language does Terraform use?**

Terraform uses HCL (HashiCorp Configuration Language).

---

### 4. **What are Terraform Providers?**

Providers are plugins that interact with APIs of cloud platforms like AWS, Azure, GCP, etc.

---

### 5. **What is a Terraform Module?**

A module is a reusable group of resources. Think of it as a container for multiple `.tf` files.

---

### 6. **What is the difference between `terraform init`, `plan`, `apply`, and `destroy`?**

* `init`: Initializes a Terraform project.
* `plan`: Shows what will be created/changed/destroyed.
* `apply`: Executes the plan.
* `destroy`: Deletes all managed infrastructure.

---

### 7. **What is the `terraform.tfstate` file?**

It keeps the current state of your infrastructure. It helps Terraform know what to change or keep.

---

### 8. **Is it safe to edit the `tfstate` file manually?**

No. It can break the state and cause inconsistencies.

---

### 9. **What is remote state?**

Storing `tfstate` file in a remote backend (e.g., S3) so multiple team members can share it safely.

---

### 10. **What are Terraform Backends?**

Backends define how state is loaded and how operations are performed. Example: `local`, `s3`, `consul`.

---

### 11. **What is a data source in Terraform?**

It lets you fetch read-only data from providers (e.g., get existing VPC ID).

---

### 12. **What are Terraform variables?**

Variables make code reusable and configurable. You define them using `variable` blocks.

---

### 13. **How do you pass variables to Terraform?**

* Using `-var` flag
* `.tfvars` files
* Environment variables

---

### 14. **What is `terraform output` used for?**

To show values after execution (like IP addresses, URLs).

---

### 15. **What is the purpose of `locals` in Terraform?**

To store intermediate values that are reused in the configuration.

---

### 16. **What is a Terraform resource?**

A resource is a block that defines infrastructure (like `aws_instance`).

---

### 17. **What is a `null_resource` in Terraform?**

It allows you to run provisioners without creating real infrastructure.

---

### 18. **What is Terraform Workspace?**

Workspaces allow you to use the same code for multiple environments (like dev, prod).

---

### 19. **What is a Terraform Provisioner?**

Used to execute scripts or commands on the target machine after resource creation.

---

### 20. **Name common provisioners.**

* `file`
* `local-exec`
* `remote-exec`

---

### 21. **What is the use of the `depends_on` keyword?**

For creating explicit resource dependencies.

---

### 22. **What is a `count` parameter in Terraform?**

Used to create multiple instances of a resource.

---

### 23. **What is `for_each` in Terraform?**

Used for looping over maps or sets for creating multiple resources.

---

### 24. **How does Terraform handle resource dependencies?**

It automatically builds a dependency graph and handles ordering.

---

### 25. **What is a `dynamic` block in Terraform?**

Used for generating nested blocks dynamically based on variables or lists.

---

### 26. **How to import existing infrastructure into Terraform?**

Use the `terraform import` command with resource type and ID.

---

### 27. **What happens if you delete a resource manually that Terraform manages?**

Terraform will detect the drift in the next plan and may recreate it.

---

### 28. **What is drift detection in Terraform?**

Detects changes made outside Terraform.

---

### 29. **Can you write conditions in Terraform?**

Yes, using ternary expressions and `count`/`for_each`.

---

### 30. **How do you loop in Terraform?**

Using `for`, `count`, or `for_each`.

---

### 31. **What are the types of Terraform files?**

* `.tf`: Main configuration file
* `.tfvars`: Variable values
* `.terraform/`: Initialization files

---

### 32. **What is Terraform Registry?**

A public repository of Terraform modules and providers.

---

### 33. **How can you handle secrets in Terraform?**

* Use environment variables
* Use `vault` provider
* Avoid hardcoding in `.tf` files

---

### 34. **What is the difference between `count` and `for_each`?**

* `count` is for a list of items
* `for_each` is for maps or sets

---

### 35. **How can you reuse code in Terraform?**

Using modules.

---

### 36. **What is the difference between Terraform and Ansible?**

* Terraform: Infrastructure provisioning (declarative)
* Ansible: Configuration management (procedural)

---

### 37. **What is a module output?**

Used to expose information from a module to the parent module.

---

### 38. **Can you use loops in modules?**

Yes, using `count` and `for_each` with module blocks.

---

### 39. **What are lifecycle rules in Terraform?**

Used to control behavior like create-before-destroy or prevent-destroy.

---

### 40. **How do you upgrade Terraform providers?**

Update the version in `required_providers` and run `terraform init -upgrade`.

---

### 41. **What happens during `terraform init`?**

* Initializes backend
* Installs provider plugins
* Prepares working directory

---

### 42. **Can Terraform be used with on-prem infrastructure?**

Yes, using providers like `vsphere`, `openstack`, or `libvirt`.

---

### 43. **What are some popular Terraform cloud providers?**

* AWS
* Azure
* GCP
* DigitalOcean
* Kubernetes

---

### 44. **What is the difference between `plan` and `apply`?**

* `plan`: Shows what changes will be made
* `apply`: Actually performs the changes

---

### 45. **How to destroy a single resource?**

```bash
terraform destroy -target=aws_instance.example
```

---

### 46. **What is a backend block?**

Defines where the Terraform state is stored remotely (e.g., S3).

---

### 47. **What is `sensitive = true` in output?**

Hides output values (e.g., passwords) from being shown in CLI.

---

### 48. **Can we use Terraform with GitOps?**

Yes, using tools like Atlantis, Spacelift, or Terraform Cloud.

---

### 49. **What is Terraform Cloud?**

A SaaS offering from HashiCorp to manage Terraform securely with version control, team access, remote runs, and state management.

---

### 50. **How to ensure best practices in Terraform projects?**

* Use modules
* Store state remotely
* Use version control
* Use linters like `tflint`
* Follow naming conventions

---
