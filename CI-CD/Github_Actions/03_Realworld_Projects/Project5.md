

### 📁 Project 5: Trigger Argo CD App Deployment from Workflow

**🎯 Goal:** Automate Kubernetes deployment by triggering an Argo CD sync when Helm/Kustomize values are updated.

### 📦 Components

* Argo CD set up and connected to the Git repo
* Kubernetes cluster (Minikube, EKS, etc.)
* GitHub workflow to update values.yaml or overlay
* Commit and push change to infra repo

---

### 📂 Directory Structure

```
argocd-trigger/
├── .github/
│   └── workflows/
│       └── deploy.yaml
├── helm-chart/
│   └── values.yaml
└── app/
    └── main.go
```

---

### 🧾 deploy.yaml

```yaml
name: Trigger Argo CD App Deployment

on:
  push:
    branches:
      - main

jobs:
  update-manifests:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Infra Repo
      uses: actions/checkout@v3

    - name: Update Image Tag
      run: |
        sed -i 's|tag:.*|tag: latest|' helm-chart/values.yaml
        git config user.name github-actions
        git config user.email github-actions@github.com
        git commit -am "chore: update image tag"
        git push
```

---

### 🛠️ Setup Instructions

1. Argo CD must be monitoring the GitHub repo with the Helm chart
2. Configure GitHub workflow to update `values.yaml`
3. Use GitHub token or SSH credentials to commit changes
4. Argo CD auto-sync or manual sync will deploy the new app version

---

### ✅ Expected Output

* GitHub Action modifies and commits Helm chart
* Argo CD detects change and deploys updated version to cluster
* Kubernetes app is redeployed automatically

---
