✅ **Section 1: Kubernetes Basics**

These questions test your foundational knowledge.

---

### 1. **What is Kubernetes?**

Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.

---

### 2. **What are the main components of the Kubernetes architecture?**

* **Master (Control Plane) components**:

  * **kube-apiserver**: Frontend of the control plane that handles API requests.
  * **controller-manager**: Manages controllers (e.g., NodeController, ReplicaSetController) to ensure the cluster’s desired state.
  * **scheduler**: Assigns pods to nodes based on resource availability and constraints.
  * **etcd**: A consistent and highly available key-value store used as Kubernetes' backing store for all cluster data.

* **Node components**:

  * **kubelet**: Agent running on each node; ensures containers are running as expected.
  * **kube-proxy**: Handles network routing and forwarding for services.
  * **Container runtime**: The software responsible for running containers (e.g., containerd, Docker, CRI-O).

---

### 3. **What is a Pod in Kubernetes?**

A **Pod** is the smallest deployable unit in Kubernetes, which encapsulates one or more containers that share the same network namespace (IP, port space) and storage volumes.

---

### 4. **What is a ReplicaSet?**

A **ReplicaSet** ensures that a specified number of pod replicas are running at any given time. If a pod crashes, the ReplicaSet creates a new one to maintain the desired count.

---

### 5. **What is a Deployment? How does it differ from a ReplicaSet?**

A **Deployment** provides declarative updates for Pods and ReplicaSets. It manages ReplicaSets and offers versioning, rollbacks, and rolling updates.

**Difference**: You usually don’t create ReplicaSets directly; you define a Deployment, which in turn creates and manages ReplicaSets automatically.

---

### 6. **What is a Namespace? Why is it used?**

A **Namespace** is a logical partition in a Kubernetes cluster used to isolate resources. It is useful in multi-team or multi-project environments to separate resources like pods, services, etc.

---

### 7. **What are Labels and Selectors in Kubernetes?**

* **Labels**: Key-value pairs attached to objects like Pods, used to organize and select subsets of objects.
* **Selectors**: Allow users to filter resources based on labels. Commonly used by ReplicaSets and Services to target specific Pods.

---

### 8. **How does Kubernetes handle service discovery?**

Kubernetes handles service discovery using:

* **DNS**: Each service gets a DNS name (e.g., `my-service.my-namespace.svc.cluster.local`).
* **Environment Variables**: Injected into containers at startup for internal communication.

---

### 9. **What is a Service in Kubernetes? Types of Services?**

A **Service** is an abstraction that defines a logical set of Pods and a policy by which to access them.

**Types of Services**:

* **ClusterIP** (default): Accessible only within the cluster.
* **NodePort**: Exposes service on a static port on each node.
* **LoadBalancer**: Provisions an external load balancer (cloud-based).
* **ExternalName**: Maps the service to an external DNS name.

---

### 10. **What is a ConfigMap and how is it used?**

A **ConfigMap** is used to store non-confidential configuration data (key-value pairs) that can be consumed by Pods as environment variables or configuration files.

---

### 11. **What is a Secret and how is it different from a ConfigMap?**

A **Secret** stores sensitive data such as passwords, tokens, or keys.

**Difference**:

* ConfigMaps are for non-sensitive data.
* Secrets are encoded (base64) and have access restrictions.

---

### 12. **How do you expose a Pod to external traffic?**

You can expose a Pod using:

* **Service of type NodePort or LoadBalancer**
* **Ingress** resource for advanced routing via HTTP(S)
* **Port forwarding** using `kubectl port-forward`

---

### 13. **What is `kubectl`? How do you use it to inspect resources?**

`kubectl` is the command-line tool used to interact with Kubernetes clusters.

**Examples**:

```bash
kubectl get pods               # List all pods
kubectl describe pod <name>   # Detailed info about a pod
kubectl get svc               # List all services
kubectl get deployments       # List deployments
kubectl get all               # Get all resources in a namespace
```

---
