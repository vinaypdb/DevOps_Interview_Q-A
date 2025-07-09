**Kubernetes Multiple Choice Questions (MCQs)**

1. What is Kubernetes primarily used for?
   A. Web development
   B. Machine learning
   C. Container orchestration
   D. Virtualization

2. What does the “kubectl” command do?
   A. Builds Docker images
   B. Deploys Kubernetes clusters
   C. Interacts with Kubernetes clusters
   D. Starts virtual machines

3. Which company originally developed Kubernetes?
   A. Microsoft
   B. Google
   C. Amazon
   D. IBM

4. What is a Pod in Kubernetes?
   A. A physical machine
   B. A group of containers
   C. A virtual machine
   D. A deployment file

5. Which object is the smallest deployable unit in Kubernetes?
   A. Deployment
   B. ReplicaSet
   C. Pod
   D. Service

6. How does Kubernetes expose a set of Pods to external traffic?
   A. Deployment
   B. ReplicaSet
   C. ConfigMap
   D. Service

7. Which component manages the Kubernetes cluster?
   A. kubelet
   B. Containerd
   C. kube-controller
   D. kube-apiserver

8. Which component runs on each worker node?
   A. kube-apiserver
   B. etcd
   C. kubelet
   D. kube-controller-manager

9. What does a ReplicaSet do?
   A. Monitors Pods
   B. Manages number of Pod replicas
   C. Stores container images
   D. Exposes services

10. Which file format is commonly used for Kubernetes manifests?
    A. .json
    B. .yaml
    C. .conf
    D. .ini

11. What command creates a deployment in Kubernetes?
    A. kubectl get deployment
    B. kubectl create deployment
    C. kubectl run
    D. kubectl expose

12. Which object defines how to update Pods automatically?
    A. Pod
    B. ReplicaSet
    C. Deployment
    D. ConfigMap

13. What is the purpose of a ConfigMap?
    A. Store container logs
    B. Store sensitive information
    C. Store configuration data
    D. Store image credentials

14. What is the purpose of a Secret in Kubernetes?
    A. Encrypt container images
    B. Store passwords and tokens
    C. Schedule Pods
    D. Load balancing

15. What kind of storage is ephemeral and deleted when a Pod is deleted?
    A. PersistentVolume
    B. PersistentVolumeClaim
    C. emptyDir
    D. hostPath

16. What is the default namespace in Kubernetes?
    A. default
    B. kube-system
    C. kube-public
    D. dev

17. Which of the following is NOT a valid Kubernetes controller?
    A. ReplicaSet
    B. Deployment
    C. StatefulSet
    D. Dockerfile

18. What is the purpose of a DaemonSet?
    A. Run a pod on selected nodes only
    B. Run a pod on every node
    C. Deploy databases
    D. Scale deployments

19. What is a StatefulSet used for?
    A. Stateless applications
    B. Persistent storage management
    C. Managing stateful applications
    D. Exposing services

20. Which Kubernetes object provides an abstraction over physical storage?
    A. VolumeMount
    B. ConfigMap
    C. PersistentVolume
    D. Secret

21. What is the role of etcd in a Kubernetes cluster?
    A. Node provisioning
    B. Pod scaling
    C. Cluster state storage
    D. Secret storage

22. How do you list all Pods in all namespaces?
    A. kubectl get pods
    B. kubectl get pods --all
    C. kubectl get pods --all-namespaces
    D. kubectl list pods

23. How do you delete a Pod named "myapp-pod"?
    A. kubectl del pod myapp-pod
    B. kubectl remove pod myapp-pod
    C. kubectl delete pod myapp-pod
    D. kubectl destroy pod myapp-pod

24. What kind of service provides external access to a pod using a public IP?
    A. ClusterIP
    B. NodePort
    C. LoadBalancer
    D. Ingress

25. Which resource defines readiness and liveness checks?
    A. Service
    B. Pod
    C. ConfigMap
    D. PersistentVolumeClaim

26. What is a Kubernetes Ingress used for?
    A. Logging
    B. Volume mounting
    C. HTTP/HTTPS routing
    D. Pod autoscaling

27. What does Horizontal Pod Autoscaler scale based on?
    A. Image size
    B. Container memory
    C. Pod logs
    D. CPU/memory utilization

28. How is resource request different from resource limit?
    A. Requests are optional
    B. Requests are soft limits; limits are hard
    C. Limits apply to nodes
    D. They are the same

29. What is the default scheduler in Kubernetes?
    A. kube-scheduler
    B. node-scheduler
    C. pod-scheduler
    D. none

30. What does a ServiceAccount do?
    A. Stores secrets
    B. Manages user authentication
    C. Provides an identity to Pods
    D. Mounts volumes

31. What is the purpose of taints and tolerations?
    A. Encrypt secrets
    B. Control Pod placement
    C. Limit storage
    D. Disable monitoring

32. What does the command `kubectl get svc` do?
    A. Lists deployments
    B. Lists services
    C. Lists secrets
    D. Lists volumes

33. What’s the default port used by Kubernetes API server?
    A. 6443
    B. 443
    C. 8080
    D. 2379

34. Which component maintains node health status?
    A. kubelet
    B. kube-proxy
    C. etcd
    D. scheduler

35. What is kube-proxy responsible for?
    A. Managing Pods
    B. Managing Secrets
    C. Network routing
    D. Scheduling

36. Which command will describe a Pod in Kubernetes?
    A. kubectl get pod <name>
    B. kubectl list pod <name>
    C. kubectl show pod <name>
    D. kubectl describe pod <name>

37. What type of workload maintains stable identities and persistent storage?
    A. DaemonSet
    B. ReplicaSet
    C. StatefulSet
    D. Job

38. What is a Job in Kubernetes used for?
    A. Long-running servers
    B. Restarting crashed Pods
    C. One-time batch operations
    D. Monitoring

39. Which object handles retries of failed Jobs automatically?
    A. ReplicaSet
    B. CronJob
    C. DaemonSet
    D. StatefulSet

40. What is the main role of CronJob?
    A. Schedule periodic tasks
    B. Monitor node health
    C. Manage secrets
    D. Route traffic

41. Which tool is used to install Kubernetes clusters easily?
    A. kubeadm
    B. kubectl
    C. minikube
    D. Docker

42. Which cloud provider offers EKS for Kubernetes?
    A. Azure
    B. GCP
    C. AWS
    D. DigitalOcean

43. What is the role of an Ingress Controller?
    A. Manage Ingress resources
    B. Store logs
    C. Monitor Pods
    D. Backup etcd

44. Which volume type allows sharing between multiple Pods?
    A. emptyDir
    B. hostPath
    C. PersistentVolumeClaim
    D. NFS

45. Which command shows the current context in kubeconfig?
    A. kubectl get context
    B. kubectl current-context
    C. kubectl config current-context
    D. kubectl describe context

46. Which label selector would match `env=prod`?
    A. env=prod
    B. label=env.prod
    C. env-prod
    D. label.env=prod

47. What does `kubectl rollout undo deployment/myapp` do?
    A. Stops the app
    B. Deletes all pods
    C. Rolls back to previous version
    D. Clears logs

48. What does `kubectl exec -it <pod> -- /bin/sh` do?
    A. Executes command in host
    B. Enters shell in the Pod
    C. Restarts the pod
    D. Deletes the pod

49. What is used to restrict access to cluster resources?
    A. ConfigMap
    B. Role/RoleBinding
    C. Namespace
    D. Secret

50. Which of the following is used for monitoring in Kubernetes?
    A. etcd
    B. Prometheus
    C. kubelet
    D. kube-proxy
