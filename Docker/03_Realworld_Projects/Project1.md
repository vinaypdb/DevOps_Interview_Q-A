# 🚀 Project 1: CI/CD for Dockerized App using GitHub Actions

## 🎯 Objective

Automatically build, test, and push a Docker image to Docker Hub when code is pushed to the `main` branch.

---

## 🧱 Tech Stack

* **Language**: Go or Python
* **CI Tool**: GitHub Actions
* **Containerization**: Docker
* **Registry**: Docker Hub

---

## 📁 Project Structure

```
ci-cd-docker-app/
├── app/                    # Application source code
│   └── main.go             # Or app.py
├── Dockerfile              # Docker container definition
├── .github/
│   └── workflows/
│       └── ci.yml          # GitHub Actions workflow
└── README.md
```

---

## 📄 Dockerfile (Go Example)

```Dockerfile
FROM golang:1.21 as builder
WORKDIR /app
COPY . .
RUN go build -o app

FROM alpine
COPY --from=builder /app/app /app
ENTRYPOINT ["/app"]
```

---

## 🔧 GitHub Actions Workflow: `.github/workflows/ci.yml`

```yaml
name: CI/CD Pipeline

on:
  push:
    branches:
      - main

jobs:
  build-and-push:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v2

      - name: Set up Docker
        uses: docker/setup-buildx-action@v2

      - name: Build Docker image
        run: docker build -t vinaypdb/birthdaymate:latest .

      - name: Login to Docker Hub
        run: echo "${{ secrets.DOCKER_PASS }}" | docker login -u "${{ secrets.DOCKER_USER }}" --password-stdin

      - name: Push Docker image
        run: docker push vinaypdb/birthdaymate:latest
```

---

## 🔐 GitHub Secrets Required

Set these in **GitHub Repo → Settings → Secrets and variables → Actions**:

* `DOCKER_USER` = `vinaypdb`
* `DOCKER_PASS` = Docker Hub password or access token

---

## ✅ How to Run

1. Push this project to your GitHub repository.
2. Add the two secrets: `DOCKER_USER` and `DOCKER_PASS`.
3. Push any changes to the `main` branch.

📦 GitHub Actions will:

* Build Docker image
* Login to Docker Hub
* Push image to `vinaypdb/birthdaymate:latest`

---

## 🔍 Validation

* Check GitHub repo → **Actions tab** for CI logs.
* Go to Docker Hub → Verify the image under `vinaypdb/birthdaymate`.

---

## 📌 Summary

| Step                                     | Description |
| ---------------------------------------- | ----------- |
| ✅ Setup Dockerfile                       | ✔️          |
| ✅ Configure GitHub Actions               | ✔️          |
| ✅ Secure credentials with GitHub Secrets | ✔️          |
| ✅ Automated CI/CD pipeline               | ✔️          |

---
