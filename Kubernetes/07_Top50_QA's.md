✅ **Kubernetes Top 50 Interview Questions & Answers (Simplified)**

These questions are commonly asked and designed to be simple and clear for easy revision.

---

### 1. What is Kubernetes?

Kubernetes is an open-source tool that manages and automates the deployment, scaling, and operation of containers.

### 2. What is a Pod?

A Pod is the smallest unit in Kubernetes. It can contain one or more containers.

### 3. What is a Node?

A Node is a worker machine in Kubernetes where Pods run.

### 4. What is the Control Plane?

The control plane manages the Kubernetes cluster and makes global decisions (like scheduling).

### 5. What is kubelet?

Kubelet is an agent on each node that ensures containers are running.

### 6. What is etcd?

etcd is a key-value store used to store cluster data.

### 7. What is a Deployment?

A Deployment manages ReplicaSets and helps with rolling updates and rollbacks.

### 8. What is a ReplicaSet?

A ReplicaSet ensures the desired number of Pods are running.

### 9. What is a Service?

A Service exposes a set of Pods to other services or users (internal or external).

### 10. What is the default type of Service?

ClusterIP (only accessible inside the cluster).

### 11. What is NodePort?

NodePort exposes the service on each Node's IP using a static port.

### 12. What is LoadBalancer?

It provisions an external load balancer and routes traffic to your service.

### 13. What is Ingress?

Ingress manages external HTTP/HTTPS access to services in the cluster.

### 14. What is ConfigMap?

ConfigMap stores non-sensitive configuration data as key-value pairs.

### 15. What is a Secret?

Secrets store sensitive data like passwords or tokens.

### 16. What is a Namespace?

Namespace separates resources in a cluster. Useful for multi-team environments.

### 17. What is kubectl?

kubectl is the command-line tool to interact with Kubernetes clusters.

### 18. How to view Pods?

```bash
kubectl get pods
```

### 19. How to see pod logs?

```bash
kubectl logs <pod-name>
```

### 20. How to describe a Pod?

```bash
kubectl describe pod <pod-name>
```

### 21. What is a StatefulSet?

StatefulSet is used for stateful applications. It gives Pods a fixed identity.

### 22. What is a DaemonSet?

A DaemonSet runs one Pod on each node.

### 23. What is a Job?

A Job runs a task until completion.

### 24. What is a CronJob?

CronJob schedules Jobs based on time (like a cron job).

### 25. What are Labels?

Labels are key-value pairs to identify and group resources.

### 26. What are Selectors?

Selectors match Labels to select a set of resources.

### 27. What is Liveness Probe?

It checks if a container is still alive.

### 28. What is Readiness Probe?

It checks if a container is ready to receive traffic.

### 29. What is HPA?

HPA (Horizontal Pod Autoscaler) automatically adjusts Pod count based on resource usage.

### 30. What is a volume?

Volume is used for storing data inside a Pod.

### 31. What is emptyDir?

A temporary volume that exists as long as the Pod exists.

### 32. What is hostPath?

Mounts a file/directory from the host node to the Pod.

### 33. What is PVC?

PVC (Persistent Volume Claim) requests storage from a PV (Persistent Volume).

### 34. What are resource requests and limits?

Requests are guaranteed resources; limits are maximum resources.

### 35. What is RBAC?

Role-Based Access Control controls who can do what in the cluster.

### 36. What is a Role and RoleBinding?

A Role defines permissions; RoleBinding assigns the Role to a user/service account.

### 37. What is a ServiceAccount?

A ServiceAccount provides identity for Pods to access the API server.

### 38. What is taint?

A taint prevents Pods from being scheduled unless they tolerate it.

### 39. What is toleration?

Toleration allows a Pod to be scheduled on a tainted node.

### 40. What is node affinity?

It controls which nodes a Pod can run on based on labels.

### 41. How do you restart a Deployment?

```bash
kubectl rollout restart deployment <name>
```

### 42. How do you expose a Deployment?

```bash
kubectl expose deployment <name> --type=NodePort --port=80
```

### 43. How do you create a Secret from literal?

```bash
kubectl create secret generic my-secret --from-literal=key=value
```

### 44. How do you apply a YAML file?

```bash
kubectl apply -f file.yaml
```

### 45. What is Helm?

Helm is a Kubernetes package manager. It uses charts to manage apps.

### 46. What is Argo CD?

Argo CD is a GitOps tool that syncs Kubernetes resources from Git.

### 47. What is kube-proxy?

kube-proxy manages networking and routes traffic to the right Pod.

### 48. How to check events in the cluster?

```bash
kubectl get events
```

### 49. How to delete a Pod?

```bash
kubectl delete pod <name>
```

### 50. What are some monitoring tools?

Prometheus, Grafana, Lens, K9s, Jaeger.

---
