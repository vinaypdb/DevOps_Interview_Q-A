**Kubernetes MCQs: Answers with Explanations**

1. **C - Container orchestration**: Kubernetes automates container deployment, scaling, and operations.

2. **C - Interacts with Kubernetes clusters**: `kubectl` is the CLI to manage Kubernetes resources.

3. **B - Google**: Google created Kubernetes and later donated it to CNCF.

4. **B - A group of containers**: A Pod can host one or more containers.

5. **C - Pod**: The smallest deployable unit in Kubernetes is a Pod.

6. **D - Service**: Services expose Pods for external or internal communication.

7. **D - kube-apiserver**: It is the main control plane interface.

8. **C - kubelet**: kubelet runs on each node to manage containers.

9. **B - Manages number of Pod replicas**: ReplicaSet maintains a stable set of replica Pods.

10. **B - .yaml**: YAML is commonly used for defining resources in Kubernetes.

11. **B - kubectl create deployment**: Used to create a Deployment.

12. **C - Deployment**: Deployment manages rolling updates of Pods.

13. **C - Store configuration data**: ConfigMaps store configuration values separately from code.

14. **B - Store passwords and tokens**: Secrets are used to store sensitive information.

15. **C - emptyDir**: A temporary directory that exists as long as the Pod runs.

16. **A - default**: The `default` namespace is used when none is specified.

17. **D - Dockerfile**: Not a Kubernetes controller; it's used for creating container images.

18. **B - Run a pod on every node**: DaemonSets ensure Pods run on all (or selected) nodes.

19. **C - Managing stateful applications**: StatefulSets provide identity and stable storage.

20. **C - PersistentVolume**: Represents a storage resource in the cluster.

21. **C - Cluster state storage**: `etcd` is a distributed key-value store for all cluster data.

22. **C - kubectl get pods --all-namespaces**: Lists Pods from all namespaces.

23. **C - kubectl delete pod myapp-pod**: Deletes a specific Pod.

24. **C - LoadBalancer**: Creates an external IP using cloud provider load balancers.

25. **B - Pod**: Liveness and readiness probes are configured inside Pod definitions.

26. **C - HTTP/HTTPS routing**: Ingress routes HTTP(S) traffic to Services.

27. **D - CPU/memory utilization**: Horizontal Pod Autoscaler uses metrics to scale.

28. **B - Requests are soft limits; limits are hard**: Requests reserve, limits cap usage.

29. **A - kube-scheduler**: Assigns Pods to available nodes.

30. **C - Provides an identity to Pods**: ServiceAccount allows Pods to access Kubernetes API securely.

31. **B - Control Pod placement**: Taints and tolerations control where Pods can be scheduled.

32. **B - Lists services**: `kubectl get svc` shows Services in a namespace.

33. **A - 6443**: Default API server port.

34. **A - kubelet**: Monitors and reports node health.

35. **C - Network routing**: kube-proxy handles network rules for Pod access.

36. **D - kubectl describe pod <name>**: Shows detailed Pod information.

37. **C - StatefulSet**: Used for stateful applications needing stable identity.

38. **C - One-time batch operations**: Jobs run once and exit when done.

39. **B - CronJob**: Runs Jobs on a schedule, automatically handles retries.

40. **A - Schedule periodic tasks**: CronJobs run tasks like backups or reports on schedule.

41. **A - kubeadm**: Tool to bootstrap Kubernetes clusters.

42. **C - AWS**: AWS offers Elastic Kubernetes Service (EKS).

43. **A - Manage Ingress resources**: Ingress Controllers implement Ingress rules.

44. **D - NFS**: Network File System can be mounted across Pods.

45. **C - kubectl config current-context**: Shows the active context from kubeconfig.

46. **A - env=prod**: This is a valid label selector syntax.

47. **C - Rolls back to previous version**: Rollback to previous Deployment revision.

48. **B - Enters shell in the Pod**: `kubectl exec` opens an interactive shell.

49. **B - Role/RoleBinding**: RBAC uses Roles and RoleBindings to restrict access.

50. **B - Prometheus**: Commonly used for monitoring and alerting in Kubernetes clusters.
