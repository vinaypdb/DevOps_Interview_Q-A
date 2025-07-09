# Kubernetes Explained Simply and Comprehensively

## 🧠 What is Kubernetes?

**Kubernetes (K8s)** is an **open-source container orchestration platform** that automates the deployment, scaling, and management of containerized applications.

Think of it like the **brain** that manages your **containers (like Docker containers)** and ensures:

* Your apps are always running
* They scale up/down based on load
* They can recover from crashes
* You can roll out updates safely

---

## 🛡️ Basic Concepts of Kubernetes

### 1. Cluster

* A **Kubernetes cluster** is a set of machines (VMs or physical servers).
* It consists of:

  * **Master/Control Plane**: The brain (controls the cluster)
  * **Worker Nodes**: The muscles (run your apps)

### 2. Node

* A **node** is a single machine (VM or physical server) in the cluster.
* Two types:

  * **Control Plane Node** (previously called master)
  * **Worker Node**

### 3. Pod

* A **pod** is the **smallest deployable unit** in Kubernetes.
* It wraps **one or more containers** together with storage/network config.
* Usually, **one container per pod**.

### 4. Deployment

* A **deployment** defines **how to run pods**: how many replicas, how to update them, and how to roll back.

### 5. Service

* A **service** provides a **stable IP and DNS name** for accessing pods.
* Types:

  * **ClusterIP** (default): Internal access
  * **NodePort**: Exposes app on a port on each node
  * **LoadBalancer**: Cloud provider's external IP

### 6. Namespace

* Think of a **namespace** as a **virtual cluster inside a physical cluster**.

---

## ⚙️ Kubernetes Control Plane Components

| Component                | Description                       |
| ------------------------ | --------------------------------- |
| kube-apiserver           | Frontend for Kubernetes API       |
| etcd                     | Key-value store for cluster data  |
| kube-scheduler           | Assigns pods to nodes             |
| kube-controller-manager  | Ensures cluster state consistency |
| cloud-controller-manager | Integrates with cloud provider    |

---

## 🛠️ Kubernetes Worker Node Components

| Component         | Description                           |
| ----------------- | ------------------------------------- |
| kubelet           | Talks to API server, runs containers  |
| kube-proxy        | Handles networking and load balancing |
| Container Runtime | Runs containers (e.g., containerd)    |

---

## 🚀 Advanced Kubernetes Concepts

### ReplicaSet

* Ensures a **specified number of pod replicas** are running.

### StatefulSet

* Used for **stateful applications** (e.g., databases).
* Each pod gets a **unique identity and persistent storage**.

### DaemonSet

* Ensures **one pod per node**.

### Job & CronJob

* **Job**: Run a task once and ensure it completes.
* **CronJob**: Run tasks on a schedule.

### ConfigMap & Secret

* **ConfigMap**: Inject **non-sensitive config data** into pods.
* **Secret**: Inject **sensitive data** (passwords, keys).

### Volumes & Persistent Volumes (PV/PVC)

* **Volume**: Persistent storage used by containers.
* **PV**: Actual storage resource
* **PVC**: A request for storage by the user

### Probes: Liveness & Readiness

* **Liveness Probe**: Checks if the app is healthy
* **Readiness Probe**: Checks if the app is ready to receive traffic

### Ingress

* Provides **HTTP/HTTPS routing** to services using **Ingress Controllers**.

### Helm

* **Helm** is the package manager for Kubernetes.
* Helm charts help you install and manage complex apps easily.

### Argo CD

* A **GitOps** continuous delivery tool for Kubernetes.
* Monitors Git repositories and syncs your cluster state.

---

## 🔐 Security Concepts

| Concept                            | Purpose                          |
| ---------------------------------- | -------------------------------- |
| RBAC                               | Role-Based Access Control        |
| Network Policies                   | Control pod-to-pod communication |
| Pod Security Policies (deprecated) | Restrict pod-level permissions   |

---

## 📈 Monitoring & Logging

| Tool                 | Use                   |
| -------------------- | --------------------- |
| Prometheus           | Monitoring & alerting |
| Grafana              | Visualize metrics     |
| Fluentd / Loki / ELK | Logging stack         |

---

## 📦 Example Workflow of an App in Kubernetes

1. Build a Docker image
2. Push to Docker Hub / ECR
3. Write a Deployment manifest
4. Deploy using `kubectl apply`
5. Expose with a Service
6. Add ConfigMaps/Secrets
7. Add monitoring with Prometheus
8. Deploy with Helm or Argo CD

---

## 💡 Summary Table

| Component        | Description                         |
| ---------------- | ----------------------------------- |
| Cluster          | Group of nodes managed by K8s       |
| Node             | Individual machine in the cluster   |
| Pod              | Smallest unit, wraps container(s)   |
| Deployment       | Defines how to run/update pods      |
| Service          | Exposes pods inside/outside cluster |
| ConfigMap/Secret | Configs for your apps               |
| Volume/PVC       | Persistent storage                  |
| Ingress          | HTTP routing layer                  |
| Helm             | K8s package manager                 |
| Argo CD          | GitOps delivery tool                |
