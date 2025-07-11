✅ **Section 2: Intermediate Concepts**

These questions require practical experience or hands-on knowledge.

---

### 1. **What is a StatefulSet and how is it different from a Deployment?**

A **StatefulSet** manages the deployment of stateful applications. It provides each pod with a unique, persistent identity and stable storage.

**Difference**: Deployments are for stateless applications; StatefulSets are for stateful apps that require stable network identity and persistent storage.

---

### 2. **What is a DaemonSet and when would you use it?**

A **DaemonSet** ensures that a pod runs on all (or specific) nodes in the cluster.

**Use cases**:

* Running monitoring agents (e.g., Prometheus node-exporter)
* Log collectors (e.g., Fluentd)
* Network plugins or system daemons

---

### 3. **What is the purpose of a Job and CronJob in Kubernetes?**

* **Job**: Runs a pod to completion (once or until success).
* **CronJob**: Schedules Jobs to run periodically based on a cron schedule (e.g., backups, report generation).

---

### 4. **Explain Liveness and Readiness Probes.**

* **Liveness Probe**: Checks if the container is alive. If it fails, the container is restarted.
* **Readiness Probe**: Checks if the container is ready to receive traffic. If it fails, the pod is removed from service endpoints.

---

### 5. **How does Kubernetes handle rolling updates and rollbacks?**

Kubernetes handles rolling updates via Deployments, updating pods incrementally without downtime. You can rollback to a previous version using:

```bash
kubectl rollout undo deployment <name>
```

---

### 6. **What is the role of etcd in Kubernetes?**

`etcd` is a distributed key-value store that stores all cluster configuration data, desired and current states of Kubernetes objects.

---

### 7. **How does autoscaling work in Kubernetes (Horizontal Pod Autoscaler)?**

The **Horizontal Pod Autoscaler (HPA)** automatically scales the number of pods based on metrics like CPU/memory usage:

```bash
kubectl autoscale deployment my-app --cpu-percent=50 --min=1 --max=10
```

---

### 8. **Explain the lifecycle of a Pod.**

Pod lifecycle phases:

1. **Pending**: Pod is accepted but not yet scheduled.
2. **Running**: Containers are running.
3. **Succeeded**: All containers have completed successfully.
4. **Failed**: At least one container terminated with failure.
5. **Unknown**: State could not be obtained.

---

### 9. **What are resource requests and limits in Kubernetes?**

* **Requests**: Minimum resources guaranteed to a container.
* **Limits**: Maximum resources a container is allowed to use.
  Defined in pod specs to ensure fair resource usage.

---

### 10. **How do you perform a rolling update in Kubernetes using kubectl?**

Update the deployment using:

```bash
kubectl set image deployment/my-app my-container=myimage:v2
```

Kubernetes will perform a rolling update by default.

---

### 11. **What is a Persistent Volume (PV) and Persistent Volume Claim (PVC)?**

* **Persistent Volume (PV)**: Storage resource provisioned in the cluster.
* **Persistent Volume Claim (PVC)**: A request for storage by a pod.
  PVC binds to a suitable PV to provide durable storage.

---

### 12. **What is the difference between emptyDir, hostPath, and PVC volumes?**

* **emptyDir**: Temporary storage created when a pod is assigned to a node. Deleted when pod is removed.
* **hostPath**: Mounts a file or directory from the node’s filesystem into the pod.
* **PVC (Persistent Volume Claim)**: Used for requesting persistent storage provisioned through a Persistent Volume.

---
