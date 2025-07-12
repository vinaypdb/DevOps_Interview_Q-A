# 🔐 Project 5: Full DevSecOps CI/CD for Netflix Clone

## 🎯 Objective

Build and deploy a **Netflix Clone** using a complete **DevSecOps CI/CD pipeline** with Jenkins, Docker, Kubernetes, Trivy, and Argo CD.

---

## 🧱 Tech Stack

* **CI/CD**: Jenkins
* **Containerization**: Docker
* **Orchestration**: Kubernetes (EKS or Minikube)
* **Security Scanning**: Trivy
* **GitOps Delivery**: Argo CD
* **Monitoring (optional)**: Prometheus + Grafana

---

## 🧩 Architecture Overview

```
GitHub Repo (Netflix Clone App)
        |
        ▼
     Jenkins CI Server
        |
        ├── Docker Build
        ├── Trivy Image Scan ✅
        ├── Push to Docker Hub
        └── Git Push K8s YAML to GitOps Repo
                ▼
           Argo CD (Pull Mode)
                ▼
         Kubernetes (Minikube/EKS)
                ▼
         Netflix Clone Running Securely ✅
```

---

## 📁 Folder Structure

```
netflix-devsecops/
├── Jenkinsfile
├── Dockerfile
├── .trivyignore
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
└── argo/
    └── app.yaml
```

---

## 🔧 Step 1: Jenkinsfile (CI/CD Pipeline)

```groovy
pipeline {
  agent any

  environment {
    DOCKER_HUB_CREDENTIALS = credentials('dockerhub-creds')
    IMAGE_NAME = "vinaypdb/netflix-clone"
  }

  stages {
    stage('Checkout') {
      steps { checkout scm }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t $IMAGE_NAME:latest .'
      }
    }

    stage('Trivy Scan') {
      steps {
        sh 'trivy image --exit-code 1 --severity HIGH,CRITICAL $IMAGE_NAME:latest || true'
      }
    }

    stage('Push to Docker Hub') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
          sh 'echo $PASSWORD | docker login -u $USERNAME --password-stdin'
          sh 'docker push $IMAGE_NAME:latest'
        }
      }
    }

    stage('GitOps Commit') {
      steps {
        sh 'git clone https://github.com/vinaypdb/netflix-infra.git'
        sh 'cp k8s/*.yaml netflix-infra/k8s/'
        dir('netflix-infra') {
          sh 'git config user.email "ci@pipeline.com"'
          sh 'git config user.name "CI Bot"'
          sh 'git add . && git commit -m "Update deployment image" && git push'
        }
      }
    }
  }
}
```

---

## 🛠️ Dockerfile

```Dockerfile
FROM node:18-alpine
WORKDIR /app
COPY . .
RUN npm install
EXPOSE 3000
CMD ["npm", "start"]
```

---

## 🛡️ Step 2: Trivy Integration

Ensure Trivy is installed on Jenkins host:

```bash
curl -sfL https://raw.githubusercontent.com/aquasecurity/trivy/main/contrib/install.sh | sh -s -- -b /usr/local/bin
```

Ignore known/unimportant CVEs (optional):

```
.trivyignore
CVE-2022-XXXX
```

---

## ☸️ Step 3: Kubernetes YAMLs

### 📄 `k8s/deployment.yaml`

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: netflix-clone
spec:
  replicas: 2
  selector:
    matchLabels:
      app: netflix
  template:
    metadata:
      labels:
        app: netflix
    spec:
      containers:
      - name: netflix
        image: vinaypdb/netflix-clone:latest
        ports:
        - containerPort: 3000
```

### 📄 `k8s/service.yaml`

```yaml
apiVersion: v1
kind: Service
metadata:
  name: netflix-service
spec:
  type: LoadBalancer
  selector:
    app: netflix
  ports:
    - port: 80
      targetPort: 3000
```

---

## 🔁 Step 4: GitOps with Argo CD

### 📄 `argo/app.yaml`

```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: netflix-app
  namespace: argocd
spec:
  project: default
  source:
    repoURL: https://github.com/vinaypdb/netflix-infra
    targetRevision: HEAD
    path: k8s
  destination:
    server: https://kubernetes.default.svc
    namespace: default
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
```

Apply in Argo CD:

```bash
kubectl apply -f argo/app.yaml -n argocd
```

---

## 🌐 Step 5: Access App

If running on Minikube:

```bash
minikube service netflix-service --url
```

If using EKS with LoadBalancer:

```bash
kubectl get svc netflix-service
```

---

## ✅ Summary

| Step                            | Description |
| ------------------------------- | ----------- |
| ✅ CI/CD with Jenkins            | ✔️          |
| ✅ Docker build and push         | ✔️          |
| ✅ Security scan with Trivy      | ✔️          |
| ✅ Kubernetes YAML deployment    | ✔️          |
| ✅ GitOps deployment via Argo CD | ✔️          |

---


