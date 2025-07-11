**Terraform MCQ Answers with Explanations**

1. **B. Infrastructure provisioning**

* Terraform is an infrastructure as code tool used to provision and manage cloud infrastructure.

2. **C. HCL**

* Terraform uses HashiCorp Configuration Language (HCL), a declarative language.

3. **C. terraform init**

* This command initializes a new or existing Terraform working directory.

4. **C. terraform.tfstate**

* The state file tracks the real infrastructure and Terraform's understanding of it.

5. **C. Shows execution plan**

* `terraform plan` previews the changes Terraform will make.

6. **D. Kubernetes Engine**

* Terraform supports Kubernetes through a provider but "Kubernetes Engine" is not a provider.

7. **C. Reuse infrastructure code**

* Modules help in creating reusable pieces of configuration.

8. **C. .tf**

* Terraform config files typically use the `.tf` extension.

9. **B. terraform apply**

* This command applies changes required to reach the desired state.

10. **B. To store values used in configuration**

* Variables allow dynamic inputs to be passed into configurations.

11. **B. variables.tf**

* This is the conventional file name used to store variable definitions.

12. **B. Defines a piece of infrastructure**

* A `resource` block describes infrastructure components like VMs, networks, etc.

13. **D. Both A and C**

* Terraform supports both `//` and `#` for single-line comments.

14. **C. terraform validate**

* This checks configuration syntax without accessing any remote services.

15. **B. Store and manage state files**

* Backends manage where Terraform keeps its state.

16. **C. Removes all managed infrastructure**

* `terraform destroy` deletes all resources defined in the configuration.

17. **D. terraform providers**

* This command shows all providers used in the configuration.

18. **C. aws\_s3\_bucket**

* This is the correct Terraform resource for managing S3 buckets.

19. **C. Formats code files**

* `terraform fmt` formats files to the canonical style.

20. **C. terraform import**

* This command brings existing infrastructure under Terraform management.

21. **A. output.tf**

* Output values are typically declared in a file named `output.tf`.

22. **C. Mark resource for recreation**

* `terraform taint` forces a resource to be destroyed and recreated.

23. **A. data**

* `data` blocks are used to retrieve information from other resources or providers.

24. **D. join()**

* `join()` is used to concatenate elements of a list into a string.

25. **C. State locking**

* DynamoDB in conjunction with S3 ensures state file locking to prevent conflicts.

26. **C. terraform workspace list**

* This lists all available workspaces.

27. **C. A reusable value within a module**

* Locals allow you to assign a name to an expression for reuse.

28. **C. lifecycle { ignore\_changes }**

* This meta-argument tells Terraform to ignore specific changes.

29. **C. Pins provider versions**

* `.terraform.lock.hcl` ensures consistent provider versions.

30. **C. terraform workspace change**

* This is not a valid command; `terraform workspace select` is used instead.

31. **A. terraform workspace current**

* This command displays the current workspace.

32. **C. To provision infrastructure automatically**

* Terraform can be integrated into CI/CD to automate infra changes.

33. **A. default**

* Terraform creates a `default` workspace by default.

34. **C. To set explicit dependencies between resources**

* `depends_on` ensures resources are created/destroyed in the proper order.

35. **C. Policy as code in Terraform Enterprise**

* Sentinel is used for governance in Terraform Enterprise.

36. **C. Directed Acyclic Graph (DAG)**

* Terraform builds a DAG to plan resource creation order.

37. **C. Role-based access control (RBAC)**

* Terraform Cloud supports RBAC to control access.

38. **C. Using modules for reusable code**

* Reusability via modules is a Terraform best practice.

39. **D. terraform init -upgrade**

* This upgrades provider versions to the latest allowed by constraints.

40. **C. Checkov**

* Checkov scans Terraform code for security misconfigurations.

41. **C. Inspect or modify Terraform state**

* `terraform state` provides subcommands for state file operations.

42. **D. vault**

* The provider for integrating with HashiCorp Vault is named `vault`.

43. **B. Displays defined output values**

* `terraform output` shows values from output blocks.

44. **C. Create multiple instances of a resource**

* The `count` parameter allows looping to create multiple resources.

45. **B. terraform.tfstate**

* State files can contain sensitive data and should not be version controlled.

46. **D. XML**

* XML is not supported in Terraform.

47. **B. Use `modules`**

* Modules allow code reuse across environments.

48. **B. To loop over lists or maps to create resources**

* `for_each` lets you iterate over collections.

49. **B. terraform graph**

* This command outputs a Graphviz graph of Terraform resources.

50. **C. Team collaboration and state consistency**

* Remote state storage supports teamwork and consistency across environments.
