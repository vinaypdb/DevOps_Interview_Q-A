
## 📗 Phase 1: GitHub Actions Basics

### 🎯 Objective

Learn the foundational concepts of GitHub Actions and create your first automation workflows in GitHub repositories.

---

### 🔹 What is GitHub Actions?

GitHub Actions is an automation service by GitHub that allows you to define workflows (YAML files) triggered by GitHub events like push, PR, or schedule. It can be used for:

* Running tests
* Building projects
* Deploying apps
* Automating development workflows

---

### 🧩 Core Concepts

* **Workflow**: Defined automation process (YAML file in `.github/workflows/`)
* **Job**: A set of steps run on the same runner
* **Step**: An individual task (e.g., running a script or action)
* **Action**: A reusable extension to perform specific tasks
* **Event**: Triggers like `push`, `pull_request`, `schedule`

---

### 🗂️ File Structure

All workflow files are stored in:

```
.github/workflows/
└── my-workflow.yml
```

---

### 🧪 Example: Hello World Workflow

```yaml
name: Hello World Workflow

on: [push]

jobs:
  greet:
    runs-on: ubuntu-latest
    steps:
      - name: Say Hello
        run: echo "👋 Hello from GitHub Actions!"
```

---

### ⚙️ Workflow Triggers

```yaml
on:
  push:
    branches:
      - main
  pull_request:
    types: [opened, synchronize]
  schedule:
    - cron: '0 0 * * *' # Every day at midnight
```

---

### 🛠️ Using Prebuilt Actions

```yaml
- name: Checkout Repository
  uses: actions/checkout@v3

- name: Setup Node.js
  uses: actions/setup-node@v4
  with:
    node-version: 18
```

---

### 🧰 Common Built-in Variables

* `github.actor`: Person who triggered workflow
* `github.repository`: `owner/repo` name
* `github.ref`: Branch or tag reference
* `runner.os`: Operating system of the runner

---

### 🧪 Debugging Tips

* Use `run: echo` to print debugging messages
* Check `Actions` tab in GitHub UI for logs
* Use `continue-on-error: true` for testing partial steps

---

### ✅ Summary

By the end of Phase 1, you can:

* Understand the structure of workflows
* Create your first YAML file
* Use triggers and basic built-in actions
* Debug simple workflow runs

---
