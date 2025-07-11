✅ **Section 6: Advanced Topics (for entry-level but with strong prep)**

These may not always be asked, but help you stand out.

---

### 1. **What is Helm and why is it used in Kubernetes?**

Helm is a package manager for Kubernetes. It helps you define, install, and upgrade complex Kubernetes applications using charts.

**Why use it:**

* Reuse predefined templates (charts)
* Manage application versions
* Easily install dependencies

---

### 2. **What is Argo CD and how is it related to Kubernetes?**

Argo CD is a GitOps continuous delivery tool for Kubernetes.

* It syncs Kubernetes manifests from a Git repository to the cluster.
* Automatically applies changes when code is pushed to Git.
* Enables declarative deployment, rollbacks, and visualization of app health.

---

### 3. **How does RBAC (Role-Based Access Control) work in Kubernetes?**

RBAC controls who can perform what actions on which resources in the cluster.
Key components:

* **Role/ClusterRole**: Define permissions.
* **RoleBinding/ClusterRoleBinding**: Assign roles to users or service accounts.

---

### 4. **What is the purpose of ServiceAccount?**

A **ServiceAccount** provides an identity for processes running in a pod to interact with the Kubernetes API.

* Used by pods for authentication when making API requests.
* Can be attached to RoleBindings or ClusterRoleBindings for permission control.

---

### 5. **What are taints and tolerations?**

* **Taints**: Applied to nodes to prevent pods from scheduling unless they tolerate the taint.
* **Tolerations**: Applied to pods to allow them to be scheduled on tainted nodes.
  Useful for dedicating nodes to specific workloads (e.g., GPU jobs).

---

### 6. **What are node affinity and pod affinity?**

* **Node affinity**: Constraints that limit pod scheduling based on node labels.
* **Pod affinity**: Schedules a pod based on other pods’ locations (co-located or not).
  Helps optimize resource utilization and communication.

---

### 7. **How do you secure Kubernetes clusters?**

* Enable RBAC and audit logging
* Use network policies
* Minimize container privileges
* Use Secrets properly
* Enable TLS and API authentication
* Use security tools like Trivy, kube-bench, Kyverno, etc.

---

### 8. **How do you backup and restore etcd?**

**Backup:**

```bash
ETCDCTL_API=3 etcdctl snapshot save snapshot.db \
  --endpoints=https://127.0.0.1:2379 \
  --cacert=<ca.crt> --cert=<etcd.crt> --key=<etcd.key>
```

**Restore:**

```bash
ETCDCTL_API=3 etcdctl snapshot restore snapshot.db \
  --data-dir=/var/lib/etcd-from-backup
```

Use `etcdctl` with proper certificates and access permissions.

---

### 9. **How does Kubernetes support multi-tenancy?**

* Use **Namespaces** to isolate resources.
* Apply **ResourceQuotas** and **LimitRanges**.
* Use **RBAC** to restrict access per team/project.
* Combine with network policies for traffic isolation.

---

### 10. **What tools do you use to monitor a Kubernetes cluster?**

* **Prometheus**: Metrics collection
* **Grafana**: Metrics visualization
* **Alertmanager**: Alerting system
* **Lens**, **K9s**, **kubectl**, and **Jaeger** for observability and tracing
* **Kube-state-metrics**, **Node Exporter**, and **cAdvisor** for detailed insights

---
