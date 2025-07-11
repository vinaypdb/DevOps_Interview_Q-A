✅ **Section 3: Networking & Ingress**

Important for understanding communication within and outside the cluster.

---

### 1. **What is the difference between ClusterIP, NodePort, and LoadBalancer?**

* **ClusterIP** (default): Exposes the service on an internal IP within the cluster. Not accessible externally.
* **NodePort**: Exposes the service on each Node's IP at a static port (range 30000–32767). External clients can access the service using `<NodeIP>:<NodePort>`.
* **LoadBalancer**: Provisions an external load balancer (usually by cloud providers) that routes traffic to the service.

---

### 2. **What is Ingress in Kubernetes and why is it used?**

**Ingress** is an API object that manages external HTTP/HTTPS access to services within the cluster.

**Why it's used:**

* To consolidate multiple services behind a single external IP or domain.
* To enable advanced traffic routing (e.g., based on path or host).
* To configure TLS/SSL termination for HTTPS.

---

### 3. **How does DNS work inside a Kubernetes cluster?**

Kubernetes uses **CoreDNS** to provide DNS-based service discovery.

* Every service gets a DNS entry like `service-name.namespace.svc.cluster.local`.
* Pods can resolve these DNS names to service cluster IPs to communicate internally.

---

### 4. **What is a NetworkPolicy and how does it secure your Pods?**

A **NetworkPolicy** is a Kubernetes resource that controls the traffic flow to/from pods at the IP address or port level.

**Uses:**

* Restrict which pods/services can talk to each other.
* Define ingress and egress rules.
* Enhance cluster security by implementing zero-trust networking.

Note: Network policies require a compatible network plugin (e.g., Calico, Cilium).

---

### 5. **How does traffic routing happen in Kubernetes with Ingress controllers like NGINX?**

* The **Ingress Controller** (e.g., NGINX) watches the Ingress resources and configures itself accordingly.
* External traffic hits the Ingress Controller (via LoadBalancer or NodePort).
* The controller inspects the request’s host/path and routes it to the appropriate service.
* Optional: TLS termination, redirects, rate limiting, authentication, etc., can be handled by the controller.

---
