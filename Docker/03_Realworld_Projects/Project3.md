# ☸️ Project 3: Deploy Dockerized App on Kubernetes (Minikube)

## 🎯 Objective

Deploy a Dockerized application to a local Kubernetes cluster using **Minikube** with Kubernetes YAML manifests.

---

## 🧱 Tech Stack

* **Container Runtime**: Docker
* **Orchestration**: Kubernetes
* **Local K8s Environment**: Minikube
* **CLI Tools**: kubectl, Minikube

---

## 📥 Step 1: Setup Minikube

### 🔧 Installation

* [Minikube Installation Guide](https://minikube.sigs.k8s.io/docs/start/)

```bash
minikube start --driver=docker
kubectl version --client
```

✅ Make sure Docker and kubectl are installed and configured.

---

## 🐳 Step 2: Use Local Docker Image in Minikube

Enable Minikube to use your local Docker images:

```bash
eval $(minikube docker-env)
```

Build the Docker image locally:

```bash
docker build -t birthdaymate:latest .
```

Verify:

```bash
docker images | grep birthdaymate
```

---

## 🧾 Step 3: Create Kubernetes Manifests

### 📄 1. `deployment.yaml`

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: birthdaymate-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: birthdaymate
  template:
    metadata:
      labels:
        app: birthdaymate
    spec:
      containers:
      - name: birthdaymate
        image: birthdaymate:latest
        imagePullPolicy: Never
        ports:
        - containerPort: 8080
```

### 📄 2. `service.yaml`

```yaml
apiVersion: v1
kind: Service
metadata:
  name: birthdaymate-service
spec:
  type: NodePort
  selector:
    app: birthdaymate
  ports:
    - port: 80
      targetPort: 8080
      nodePort: 30080
```

---

## 🚀 Step 4: Apply Manifests

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

Check resources:

```bash
kubectl get pods
kubectl get svc
```

---

## 🌐 Step 5: Access the App

```bash
minikube service birthdaymate-service --url
```

It will return a local URL like `http://127.0.0.1:30080` → open in browser

---

## 🔁 Step 6: Update Image and Redeploy

If app code changes:

```bash
docker build -t birthdaymate:latest .
kubectl rollout restart deployment birthdaymate-deployment
```

---

## 🧹 Step 7: Cleanup

```bash
kubectl delete -f deployment.yaml
kubectl delete -f service.yaml
```

---

## ❓ Interview & Real-World Tips

* Use `imagePullPolicy: Never` to use local images
* Prefer `NodePort` for Minikube local access
* Validate with `kubectl logs` and `describe`

---

## 📌 Summary

| Step                                     | Description |
| ---------------------------------------- | ----------- |
| ✅ Start Minikube and use local Docker    | ✔️          |
| ✅ Build and tag Docker image             | ✔️          |
| ✅ Write deployment and service manifests | ✔️          |
| ✅ Apply and expose the service           | ✔️          |
| ✅ Access locally via browser             | ✔️          |

---
