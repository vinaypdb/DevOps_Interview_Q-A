

### 📁 Project 2: Build and Push Docker Image to Docker Hub

**🎯 Goal:** Automate building a Docker image and pushing it to Docker Hub using GitHub Actions.

### 📦 Components

* Dockerfile for Node.js or Go app
* GitHub repository
* Docker Hub credentials stored as secrets

---

### 📂 Directory Structure

```
docker-pipeline/
├── .github/
│   └── workflows/
│       └── docker-build.yml
├── Dockerfile
└── app/
    └── main.js
```

---

### 🧾 docker-build.yml

```yaml
name: Docker Build and Push

on:
  push:
    branches:
      - main

jobs:
  docker:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Code
      uses: actions/checkout@v3

    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v3

    - name: Log in to Docker Hub
      uses: docker/login-action@v3
      with:
        username: ${{ secrets.DOCKERHUB_USERNAME }}
        password: ${{ secrets.DOCKERHUB_TOKEN }}

    - name: Build and Push Docker Image
      uses: docker/build-push-action@v5
      with:
        context: .
        push: true
        tags: yourdockerhubuser/yourapp:latest
```

---

### 🛠️ Setup Instructions

1. Create a Dockerfile in your repo
2. Create GitHub secrets:

   * `DOCKERHUB_USERNAME`
   * `DOCKERHUB_TOKEN` (use Docker Hub access token)
3. Place `docker-build.yml` in `.github/workflows/`
4. Push code to `main` to trigger the action

---

### ✅ Expected Output

* Docker image is built
* Authenticates with Docker Hub
* Image is pushed to your repo (e.g. `vinaypdb/myapp:latest`)

---
