**Terraform Multiple Choice Questions (MCQs)**

1. What is the primary purpose of Terraform?

* A. Application development
* B. Infrastructure provisioning
* C. Database management
* D. Container orchestration

2. Which language is used for writing Terraform configuration files?

* A. JSON
* B. YAML
* C. HCL
* D. XML

3. Which command initializes a Terraform working directory?

* A. terraform start
* B. terraform setup
* C. terraform init
* D. terraform config

4. What file does Terraform use to store the current state of infrastructure?

* A. terraform.log
* B. terraform.tf
* C. terraform.tfstate
* D. terraform.state

5. What is the function of `terraform plan`?

* A. Applies infrastructure changes
* B. Destroys infrastructure
* C. Shows execution plan
* D. Validates configuration

6. Which provider is NOT officially supported by Terraform?

* A. AWS
* B. Azure
* C. GCP
* D. Kubernetes Engine

7. What is the purpose of a `module` in Terraform?

* A. Manage users
* B. Create network policies
* C. Reuse infrastructure code
* D. Encrypt secrets

8. What type of file extension do Terraform configuration files use?

* A. .yaml
* B. .conf
* C. .tf
* D. .json

9. Which command will apply the changes required to reach the desired state of the configuration?

* A. terraform start
* B. terraform apply
* C. terraform build
* D. terraform update

10. What is the use of a variable in Terraform?

* A. To define resource types
* B. To store values used in configuration
* C. To manage permissions
* D. To debug logs

11. What is the default file name for Terraform variable definitions?

* A. terraform.tf
* B. variables.tf
* C. terraformvars.tf
* D. config.tf

12. Which of the following best describes a `resource` block in Terraform?

* A. Stores variable values
* B. Defines a piece of infrastructure
* C. Handles encryption
* D. Specifies provider credentials

13. How do you comment a single line in a `.tf` file?

* A. // comment
* B. <!-- comment -->
* C. # comment
* D. Both A and C

14. What command is used to check syntax and validity of Terraform code?

* A. terraform plan
* B. terraform check
* C. terraform validate
* D. terraform lint

15. What is the purpose of a backend in Terraform?

* A. Manage plugins
* B. Store and manage state files
* C. Deploy containers
* D. Create IAM roles

16. What is the role of `terraform destroy`?

* A. Initializes configuration
* B. Validates settings
* C. Removes all managed infrastructure
* D. Undoes changes

17. Which command shows all available Terraform providers?

* A. terraform providers list
* B. terraform show providers
* C. terraform init
* D. terraform providers

18. Which Terraform resource type is used to manage an S3 bucket?

* A. aws\_bucket
* B. aws\_storage
* C. aws\_s3\_bucket
* D. aws\_s3

19. What does `terraform fmt` do?

* A. Applies changes
* B. Validates configs
* C. Formats code files
* D. Lists resources

20. How can you use Terraform to import existing infrastructure?

* A. terraform load
* B. terraform migrate
* C. terraform import
* D. terraform pull

21. Which file can be used to define output values?

* A. output.tf
* B. result.tf
* C. output.json
* D. terraform.tf

22. What is the purpose of `terraform taint`?

* A. Temporarily disable a resource
* B. Format the code
* C. Mark resource for recreation
* D. Lock a resource

23. Which block helps read information from external sources?

* A. data
* B. resource
* C. input
* D. module

24. Which Terraform function would you use to combine strings?

* A. concat()
* B. merge()
* C. format()
* D. join()

25. What type of locking does remote backend with S3 and DynamoDB provide?

* A. SSH locking
* B. Manual locking
* C. State locking
* D. Role-based locking

26. What is the command to list all workspaces?

* A. terraform list workspaces
* B. terraform show workspaces
* C. terraform workspace list
* D. terraform env show

27. What is a `local` value in Terraform?

* A. A provider configuration
* B. A variable shared globally
* C. A reusable value within a module
* D. An environment variable

28. How do you ignore changes to a Terraform-managed resource?

* A. ignore\_updates
* B. skip\_changes
* C. lifecycle { ignore\_changes }
* D. mutate { skip }

29. What does a `.terraform.lock.hcl` file do?

* A. Locks variable values
* B. Stores user permissions
* C. Pins provider versions
* D. Logs Terraform actions

30. Which of the following is not a valid Terraform workspace command?

* A. terraform workspace new
* B. terraform workspace list
* C. terraform workspace change
* D. terraform workspace select

31. What command can you use to view your current workspace?

* A. terraform workspace current
* B. terraform get workspace
* C. terraform show workspace
* D. terraform workspace view

32. How can Terraform be used in a CI/CD pipeline?

* A. To build Docker images
* B. To define environment variables
* C. To provision infrastructure automatically
* D. To deploy applications

33. What is the default workspace name in Terraform?

* A. default
* B. dev
* C. main
* D. global

34. What is the purpose of `depends_on`?

* A. To manage IAM roles
* B. To create modules
* C. To set explicit dependencies between resources
* D. To handle network routing

35. What is the purpose of Sentinel?

* A. Monitor EC2 instances
* B. Test resource availability
* C. Policy as code in Terraform Enterprise
* D. Scan for security issues

36. What kind of graph does Terraform generate to determine resource order?

* A. Linear graph
* B. Decision tree
* C. Directed Acyclic Graph (DAG)
* D. Flowchart

37. How do you restrict access to specific resources in Terraform Cloud?

* A. Workspace names
* B. State files
* C. Role-based access control (RBAC)
* D. Plan files

38. Which of the following best practices is recommended in Terraform?

* A. Hardcoding values
* B. Committing .tfstate to version control
* C. Using modules for reusable code
* D. Avoiding version constraints

39. Which command upgrades the provider plugins?

* A. terraform update
* B. terraform plugins upgrade
* C. terraform get -upgrade
* D. terraform init -upgrade

40. Which tool helps scan Terraform code for security misconfigurations?

* A. Sentinel
* B. Vault
* C. Checkov
* D. Chef

41. What is the purpose of `terraform state` command?

* A. Encrypt the state file
* B. Validate configuration files
* C. Inspect or modify Terraform state
* D. Plan infrastructure changes

42. Which plugin lets you manage secrets in HashiCorp Vault with Terraform?

* A. vault\_secret
* B. hashicorp\_vault
* C. vault\_provider
* D. vault

43. What does `terraform output` command do?

* A. Shows logs
* B. Displays defined output values
* C. Lists available commands
* D. Dumps the state file

44. What is the function of `count` in a resource block?

* A. Restrict parallelism
* B. Count modules
* C. Create multiple instances of a resource
* D. Limit output lines

45. Which file should be added to `.gitignore` for security?

* A. main.tf
* B. terraform.tfstate
* C. backend.tf
* D. variables.tf

46. Which of these formats is not directly used in Terraform?

* A. HCL
* B. YAML
* C. JSON
* D. XML

47. How do you reuse code across multiple environments in Terraform?

* A. Use `locals`
* B. Use `modules`
* C. Use `outputs`
* D. Use `workspaces`

48. What is the function of `for_each`?

* A. To limit resource usage
* B. To loop over lists or maps to create resources
* C. To replace `count`
* D. To loop over output values

49. What command shows a visual representation of the Terraform dependency graph?

* A. terraform show
* B. terraform graph
* C. terraform dag
* D. terraform plan --graph

50. What is the benefit of remote state in Terraform?

* A. Faster CLI commands
* B. Version control of configuration
* C. Team collaboration and state consistency
* D. Improved formatting
