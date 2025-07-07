✅ **Section 4: Troubleshooting & Debugging**

These are scenario-based and often asked to check your practical understanding.

---

### 1. **A pod is stuck in CrashLoopBackOff—how do you troubleshoot?**

Steps to troubleshoot:

* Check pod logs:

  ```bash
  kubectl logs <pod-name> --previous
  ```
* Check pod events:

  ```bash
  kubectl describe pod <pod-name>
  ```
* Common causes:

  * Application crashes due to config errors
  * Failed liveness probes
  * Missing environment variables or secrets
  * Insufficient resources

---

### 2. **How to debug a pod that's not starting?**

* Use `kubectl describe pod <pod-name>` to check events and scheduling issues.
* Use `kubectl get events` to get recent warnings/errors.
* Check for:

  * Image pull issues (ImagePullBackOff)
  * Node resource constraints
  * Incorrect volume mounts
  * Network policies blocking dependencies

---

### 3. **How to check the logs of a pod and monitor its behavior?**

* View logs:

  ```bash
  kubectl logs <pod-name>
  ```
* For multiple containers in a pod:

  ```bash
  kubectl logs <pod-name> -c <container-name>
  ```
* For previous container instance:

  ```bash
  kubectl logs <pod-name> --previous
  ```
* Monitor in real-time:

  ```bash
  kubectl logs -f <pod-name>
  ```

---

### 4. **How do you restart a deployment or pod manually?**

* Restart a deployment:

  ```bash
  kubectl rollout restart deployment <deployment-name>
  ```
* Delete a pod (it will be recreated by ReplicaSet):

  ```bash
  kubectl delete pod <pod-name>
  ```

---

### 5. **What is the difference between kubectl logs and kubectl describe?**

* **`kubectl logs`**: Shows the stdout/stderr of container logs. Used to debug application-level issues.
* **`kubectl describe`**: Gives a detailed description of a resource including events, conditions, volumes, environment variables, and error messages from the control plane.

Use both together for effective debugging.

---
