✅ **Top 50 CI/CD Interview Questions and Answers (Simple but Comprehensive)**

---

### 1. **What is CI/CD?**

CI/CD stands for Continuous Integration and Continuous Delivery/Deployment. It automates software integration, testing, and deployment.

---

### 2. **What is the difference between Continuous Integration, Delivery, and Deployment?**

* **CI**: Merging code changes into a shared repo with automated testing.
* **CD (Delivery)**: Automatically preparing code for release.
* **CD (Deployment)**: Automatically releasing code to production.

---

### 3. **What are the benefits of CI/CD?**

* Faster releases
* Early bug detection
* Reduced manual errors
* Better team collaboration

---

### 4. **What tools are used in CI/CD pipelines?**

* **CI**: Jenkins, GitHub Actions, GitLab CI, CircleCI
* **CD**: Argo CD, Spinnaker, Helm
* **Testing**: JUnit, Selenium

---

### 5. **What is Jenkins?**

Jenkins is an open-source CI/CD tool used to automate building, testing, and deploying applications.

---

### 6. **How does Jenkins work?**

It uses pipelines (jobs) to define steps like code checkout, build, test, and deploy. You configure these using GUI or `Jenkinsfile`.

---

### 7. **What is a Jenkinsfile?**

A text file that defines the pipeline steps using Groovy syntax. Stored in the code repo.

---

### 8. **What are the types of Jenkins pipelines?**

* Declarative
* Scripted
  Declarative is simpler and preferred for most use cases.

---

### 9. **What is GitOps?**

GitOps is a DevOps practice where Git is the single source of truth for infrastructure and deployment automation.

---

### 10. **What is Argo CD?**

Argo CD is a GitOps-based continuous deployment tool for Kubernetes. It syncs cluster state with Git repo.

---

### 11. **How do GitHub Actions work?**

They run workflows triggered by events like `push`, `pull_request`, etc. Workflows are defined in YAML files.

---

### 12. **What is a CI/CD pipeline?**

A series of steps to build, test, and deploy software automatically.

---

### 13. **Why are automated tests important in CI/CD?**

They catch bugs early, ensure stability, and reduce the need for manual testing.

---

### 14. **What is Canary Deployment?**

Releasing an update to a small subset of users to minimize risk before full rollout.

---

### 15. **What is Blue-Green Deployment?**

You have two environments: Blue (current) and Green (new). Switch traffic to Green after verification.

---

### 16. **What is Rollback?**

Reverting to a previous stable version if a deployment fails.

---

### 17. **What is a build artifact?**

The result of a build process, like a Docker image, binary, or WAR file.

---

### 18. **What is Artifact Repository?**

A place to store and manage build artifacts. Examples: Nexus, Artifactory, GitHub Packages.

---

### 19. **What is Webhook in CI/CD?**

A way for one service to notify another about an event (e.g., push to GitHub triggers Jenkins).

---

### 20. **What is the role of Docker in CI/CD?**

Docker packages apps in containers for consistency across environments.

---

### 21. **What is Dockerfile?**

A file with instructions to build a Docker image.

---

### 22. **What is Kubernetes' role in CI/CD?**

It serves as the deployment environment. CD tools deploy to Kubernetes clusters.

---

### 23. **What is a deployment strategy?**

A method of updating software in production (e.g., rolling, blue-green, canary).

---

### 24. **What is the difference between push and pull deployment in CD?**

* **Push**: CI/CD server deploys to environment.
* **Pull**: Cluster pulls from Git (used in GitOps).

---

### 25. **What is YAML in CI/CD?**

YAML is used to define workflows and configurations (e.g., GitHub Actions, Kubernetes manifests).

---

### 26. **What is a runner/agent in CI/CD?**

A machine that executes CI/CD jobs (e.g., GitLab Runner, Jenkins Agent).

---

### 27. **What is version control and why is it needed in CI/CD?**

It tracks changes in code. Enables collaboration, rollbacks, and integration with CI/CD.

---

### 28. **What is Infrastructure as Code (IaC)?**

Managing infrastructure using code (e.g., Terraform, Ansible). It can be part of CI/CD pipelines.

---

### 29. **What is a stage in a pipeline?**

A logical phase in CI/CD (e.g., Build, Test, Deploy).

---

### 30. **What are some best practices for CI/CD?**

* Commit often
* Use branching strategy
* Automate tests
* Isolate environments
* Monitor deployments

---

### 31. **What is Continuous Testing?**

Running automated tests continuously during the development lifecycle.

---

### 32. **What is test coverage?**

A measure of how much of the code is tested by automated tests.

---

### 33. **What is linting in CI/CD?**

Static code analysis to detect syntax/style issues early.

---

### 34. **How do you handle secrets in CI/CD?**

* Use secret managers (e.g., HashiCorp Vault, AWS Secrets Manager)
* Store in CI/CD tool's secrets section (e.g., GitHub Secrets)

---

### 35. **What is pipeline as code?**

Defining the CI/CD pipeline in version-controlled files (e.g., Jenkinsfile, `.github/workflows`).

---

### 36. **What is the use of caching in CI/CD?**

To speed up builds by reusing dependencies (e.g., `npm ci` with cache).

---

### 37. **What is a matrix build?**

Running a job in parallel with different combinations (e.g., OS, language version).

---

### 38. **What is approval gate in CI/CD?**

A manual checkpoint where someone approves the next stage (often used in CD).

---

### 39. **What is deployment pipeline vs release pipeline?**

* **Deployment pipeline**: Builds and delivers software.
* **Release pipeline**: Controls how and when features go live.

---

### 40. **What is trunk-based development?**

All developers commit to a single branch (usually main/master) with frequent merges.

---

### 41. **How do you roll back a failed deployment?**

* Use deployment history (e.g., `kubectl rollout undo`)
* Restore previous artifact from repository

---

### 42. **What is a job in CI/CD?**

A single unit of work (e.g., run tests, build image) in the pipeline.

---

### 43. **What is integration testing?**

Testing combined components or services to ensure they work together.

---

### 44. **What is a production freeze?**

A period during which no new deployments are allowed to reduce risk.

---

### 45. **What is SLA/SLO in CI/CD monitoring?**

* **SLA**: Service Level Agreement
* **SLO**: Service Level Objective (e.g., 99.9% uptime)
  Used for reliability tracking.

---

### 46. **How do you monitor CI/CD pipelines?**

* Built-in dashboards (Jenkins, GitHub Actions)
* Custom dashboards with Prometheus/Grafana

---

### 47. **What is feedback loop in CI/CD?**

The process of receiving fast feedback from code changes, builds, and deployments.

---

### 48. **What is tagging and versioning in CI/CD?**

Tagging code or artifacts for traceability and rollback (e.g., `v1.0.0`).

---

### 49. **What is a monorepo vs polyrepo in CI/CD?**

* **Monorepo**: All code in one repository
* **Polyrepo**: Each service/module has its own repo

---

### 50. **How do you secure a CI/CD pipeline?**

* Use strong authentication for SCM/CI tools
* Scan code and containers for vulnerabilities
* Use secrets management
* Audit logs and permissions

---
