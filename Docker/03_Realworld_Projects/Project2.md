# 🔐 Project 2: Secure Docker Images with Trivy

## 🎯 Objective

Scan Docker images for vulnerabilities using **Trivy**, a powerful open-source security scanner.

---

## 🧱 Tech Stack

* **Security Tool**: Trivy
* **Containerization**: Docker
* **Target Registry**: Docker Hub or local image

---

## 📥 Install Trivy

### 🔧 On Linux/macOS:

```bash
brew install aquasecurity/trivy/trivy        # macOS
sudo apt install wget -y && \
wget https://github.com/aquasecurity/trivy/releases/latest/download/trivy_0.50.0_Linux-64bit.deb && \
sudo dpkg -i trivy_0.50.0_Linux-64bit.deb    # Linux
```

### 🧪 Verify:

```bash
trivy --version
```

---

## 🐳 Step 1: Create Sample Docker App (Go Example)

```Dockerfile
FROM golang:1.21 as builder
WORKDIR /app
COPY . .
RUN go build -o app

FROM alpine
COPY --from=builder /app/app /app
ENTRYPOINT ["/app"]
```

Build the image:

```bash
docker build -t vinaypdb/birthdaymate:latest .
```

---

## 🛡️ Step 2: Scan Docker Image with Trivy

### 🔍 Basic Usage

```bash
trivy image vinaypdb/birthdaymate:latest
```

### 🔍 Scan Local Image

```bash
trivy image --severity HIGH,CRITICAL birthdaymate:latest
```

### 🔍 Scan Remote Image (Docker Hub)

```bash
trivy image docker.io/vinaypdb/birthdaymate:latest
```

---

## 📄 Sample Output

```
Total: 12 (HIGH: 4, CRITICAL: 2)

+-----------------------------+
| Vulnerability ID | Severity|
+-----------------------------+
| CVE-2024-XXXXXX  | HIGH    |
| CVE-2024-YYYYYY  | CRITICAL|
+-----------------------------+
```

---

## 🛠️ Optional: Export Scan Report

```bash
trivy image --format json --output trivy-report.json vinaypdb/birthdaymate:latest
```

---

## ⚙️ Integrate with CI/CD (Optional)

Example step for GitHub Actions:

```yaml
- name: Scan Docker Image
  uses: aquasecurity/trivy-action@master
  with:
    image-ref: 'vinaypdb/birthdaymate:latest'
    format: 'table'
    severity: 'HIGH,CRITICAL'
```

---

## 📌 Summary

| Step                           | Description |
| ------------------------------ | ----------- |
| ✅ Install and use Trivy        | ✔️          |
| ✅ Scan local and remote images | ✔️          |
| ✅ Identify CVEs and severities | ✔️          |
| ✅ Export scan report           | ✔️          |
| ✅ Integrate scan into CI/CD    | ✔️          |

---
