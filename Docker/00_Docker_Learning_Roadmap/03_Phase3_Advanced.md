# 🧠 Docker Phase 3: Advanced Concepts

---

## 🔀 Multi-Stage Builds

Used to create small, optimized images by separating build and runtime environments.

### 🎯 Benefits

* Smaller final image size
* No need to include build tools or source code in production image

### 🧪 Example: Go App

```Dockerfile
# Stage 1 - Builder
FROM golang:1.21 AS builder
WORKDIR /app
COPY . .
RUN go build -o app

# Stage 2 - Final image
FROM alpine
COPY --from=builder /app/app /app
ENTRYPOINT ["/app"]
```

---

## 💚 Health Checks

Used to monitor the health of running containers.

### 📄 Example:

```Dockerfile
HEALTHCHECK CMD curl --fail http://localhost:8080 || exit 1
```

### 📌 Use Cases

* Restart unhealthy containers automatically
* Integrated with orchestration systems (like Docker Swarm, Kubernetes)

---

## 🛡️ Docker Security Best Practices

1. **Use trusted base images**
2. **Run containers as non-root user**
3. **Minimize image size** (use Alpine, multi-stage builds)
4. **Scan images** regularly (e.g., Trivy, Docker Scout)
5. **Limit container capabilities**

   ```bash
   docker run --cap-drop all --cap-add NET_BIND_SERVICE ...
   ```

### 📦 Add a Non-Root User in Dockerfile

```Dockerfile
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser
```

---

## 🔐 Image Scanning Tools

| Tool         | Use Case                                    |
| ------------ | ------------------------------------------- |
| Trivy        | Image, repo, config scanning                |
| Docker Scout | Official Docker image vulnerability scanner |
| Snyk         | Advanced scanning with remediation advice   |

### 🔎 Example: Trivy

```bash
trivy image myapp:latest
```

---

## 📤 Docker Registry (Private/Public)

### 🧰 Use Cases

* Store private images
* Version control for Docker images

### 📄 Docker Hub

```bash
docker login

docker tag myapp vinaypdb/myapp:latest
docker push vinaypdb/myapp:latest
```

### 🏢 Self-Hosted Registry

```bash
docker run -d -p 5000:5000 --name registry registry:2
```

Push/pull from localhost:

```bash
docker tag myapp localhost:5000/myapp
docker push localhost:5000/myapp
```

---

## ⚙️ CI/CD Integration

### 📍 Use Docker in GitHub Actions, GitLab CI, Jenkins

**GitHub Actions Example:**

```yaml
jobs:
  docker:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Build Docker image
        run: docker build -t myapp .
      - name: Push to Docker Hub
        run: |
          echo "$DOCKER_PASSWORD" | docker login -u $DOCKER_USERNAME --password-stdin
          docker push myapp
```

---

## 📦 Real-World Project: CI/CD Pipeline for Go App

### 🔧 Dockerfile

```Dockerfile
FROM golang:1.21 as builder
WORKDIR /app
COPY . .
RUN go build -o birthdaymate

FROM alpine
COPY --from=builder /app/birthdaymate /birthdaymate
ENTRYPOINT ["/birthdaymate"]
```

### 🔁 GitHub Actions Workflow

```yaml
name: CI
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Docker Build & Push
        run: |
          docker build -t vinaypdb/birthdaymate:latest .
          echo ${{ secrets.DOCKER_PASS }} | docker login -u ${{ secrets.DOCKER_USER }} --password-stdin
          docker push vinaypdb/birthdaymate:latest
```

---

## 📈 Bonus: Docker Swarm & Kubernetes Intro

| Tool         | Purpose                                                               |
| ------------ | --------------------------------------------------------------------- |
| Docker Swarm | Simple native clustering/orchestration                                |
| Kubernetes   | Advanced orchestration (auto-scaling, health checks, rolling updates) |

### 🧪 Docker Swarm Example

```bash
docker swarm init
docker service create --name web -p 80:80 nginx
```

---

## ❓ Interview Questions (Advanced)

1. What are multi-stage builds in Docker and why are they useful?
2. How do you secure Docker containers in production?
3. What is the difference between CMD and ENTRYPOINT?
4. How do you perform image scanning in Docker?
5. How do you integrate Docker with CI/CD pipelines?
6. What are the advantages of a private Docker registry?

---

## 📌 Summary

| Skill                        | Gained |
| ---------------------------- | ------ |
| ✅ Built multi-stage images   | ✔️     |
| ✅ Implemented health checks  | ✔️     |
| ✅ Secured Docker containers  | ✔️     |
| ✅ Used image scanning tools  | ✔️     |
| ✅ Pushed to Docker registry  | ✔️     |
| ✅ Integrated Docker in CI/CD | ✔️     |
