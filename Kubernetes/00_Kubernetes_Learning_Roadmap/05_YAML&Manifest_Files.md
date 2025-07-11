✅ **Section 5: YAML & Manifest Files**

Interviewers expect you to understand and write YAML.

---

### 1. **What is the structure of a Kubernetes YAML manifest?**

A Kubernetes manifest file typically includes these fields:

```yaml
apiVersion: <api-group/version>
kind: <resource-type>
metadata:
  name: <resource-name>
  labels:
    key: value
spec:
  # resource-specific configuration
```

Each YAML defines a single resource (like Pod, Deployment, Service, etc.). Multiple resources can be separated by `---`.

---

### 2. **How to define a Deployment YAML with 3 replicas and expose it via a Service?**

**Deployment YAML:**

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-container
        image: nginx
        ports:
        - containerPort: 80
```

**Service YAML:**

```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: ClusterIP
```

---

### 3. **How do you pass environment variables in a Pod spec?**

```yaml
spec:
  containers:
  - name: my-container
    image: nginx
    env:
    - name: ENV_VAR_NAME
      value: "some-value"
```

You can also reference ConfigMaps or Secrets in `envFrom` or `valueFrom`.

---

### 4. **How to mount a ConfigMap or Secret into a Pod using YAML?**

**Mounting a ConfigMap:**

```yaml
spec:
  containers:
  - name: my-container
    image: nginx
    volumeMounts:
    - name: config-volume
      mountPath: /etc/config
  volumes:
  - name: config-volume
    configMap:
      name: my-configmap
```

**Mounting a Secret:**

```yaml
spec:
  containers:
  - name: my-container
    image: nginx
    volumeMounts:
    - name: secret-volume
      mountPath: /etc/secret
  volumes:
  - name: secret-volume
    secret:
      secretName: my-secret
```

---

### 5. **How to define resource limits and requests in Pod YAML?**

```yaml
spec:
  containers:
  - name: my-container
    image: nginx
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
      limits:
        memory: "128Mi"
        cpu: "500m"
```

* **requests**: Minimum guaranteed resources
* **limits**: Maximum resources allowed

---
