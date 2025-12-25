## 📘 Kubernetes — ReplicaSet (RS) & ReplicationController (RC)

### 🚀 1. What is a ReplicationController (RC)?

A **ReplicationController (RC)** ensures that a specified number of **pod replicas** are always running in Kubernetes.
___

### ✔ Key Features
- Ensures high availability  
- Maintains desired pod count  
- Auto-recreates crashed pods  
- Uses basic label selectors  
- **Legacy component (Replaced by ReplicaSet)**  

## 📘 2. RC Commands

### ➤ Create RC
```bash
kubectl apply -f rc.yaml
```

### ➤ List RCs
```bash
kubectl get rc
```

### ➤ Describe RC
```bash
kubectl describe rc <name>
```

### ➤ Delete RC
```bash
kubectl delete rc <name}
```

## 📄 3. ReplicationController YAML (`rc.yaml`)

```yaml
apiVersion: v1
kind: ReplicationController
metadata:
  name: nginx-rc
spec:
  replicas: 3
  selector:
    app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
          - containerPort: 80
```

---

# 🚀 4. What is a ReplicaSet (RS)?

A **ReplicaSet (RS)** is the modern and recommended method to maintain the desired number of pod replicas.

### ✔ Key Features
- Ensures desired pod count  
- Advanced selectors (matchLabels + matchExpressions)  
- Used internally by **Deployments**  
- Production-ready  
- Self-healing  

## 📘 5. RS Commands

### ➤ Create RS
```bash
kubectl apply -f rs.yaml
```

### ➤ List RS
```bash
kubectl get rs
```

### ➤ Describe RS
```bash
kubectl describe rs <name>
```

### ➤ Delete RS
```bash
kubectl delete rs <name>
```

## 📄 6. ReplicaSet YAML (`rs.yaml`)

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-rs
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
          - containerPort: 80
```

---

# 🔍 7. RC vs RS — Comparison Table

| Feature | ReplicationController (RC) | ReplicaSet (RS) |
|---------|-----------------------------|------------------|
| API Version | v1 | apps/v1 |
| Status | Legacy | Recommended |
| Selector Support | Basic | Advanced |
| Used by Deployment | No | Yes |
| Real Use Case | Not recommended | Widely used |

---

# ✅ Conclusion

- **RC = Old**, basic, not recommended  
- **RS = New**, advanced, used by Deployments  
- Prefer **ReplicaSet or Deployment** in real-world projects  
