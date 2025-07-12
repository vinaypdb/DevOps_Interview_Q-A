 Real-World Projects with GitHub Actions

### 🎯 Objective

Apply GitHub Actions to real-world DevOps use cases, such as CI/CD pipelines, Docker builds, static site deployment, and GitOps automation.

---

### 📁 Project 1: CI Pipeline for a Node.js App

* Trigger on push and PR events
* Install dependencies and run tests using Node.js
* Upload test reports as artifacts

### 📁 Project 2: Build and Push Docker Image to Docker Hub

* Trigger on push to `main`
* Build image using Dockerfile
* Push image to Docker Hub using secrets

### 📁 Project 3: Deploy Static Site to GitHub Pages

* Trigger on push to `main` branch
* Use `actions-gh-pages` to deploy built static files from `dist/`

### 📁 Project 4: Auto Release Generator using GitHub Actions

* Trigger on push with version tag (e.g. `v1.0.0`)
* Use `release-drafter` or custom steps to publish GitHub releases

### 📁 Project 5: Trigger Argo CD App Deployment from Workflow

* Update Helm chart values or Kustomize overlays in Git repo
* Commit changes and let Argo CD sync changes to Kubernetes
* Optionally notify Slack or Discord

---
