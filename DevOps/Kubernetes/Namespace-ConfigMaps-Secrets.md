# 📘 Kubernetes — Namespaces, ConfigMaps & Secrets

---

# 🚀 1. Kubernetes Namespaces

Namespaces are used to **logically isolate** resources inside a Kubernetes cluster.
It is just a folder inside Kubernetes cluster.

* We use namespaces to keep things separate and organized.

Example:

dev (for developers)
test (for testing)
prod (for production)

## ✔ Why Use Namespaces?
- Environment separation (dev / test / prod)
- Avoid name conflicts
- Apply resource quotas
- RBAC access control
- Better organization in large clusters

---

## 📘 Namespace Commands

### ➤ Create Namespace
```bash
kubectl create namespace dev
```

### ➤ List Namespaces
```bash
kubectl get ns
```

### ➤ Describe Namespace
```bash
kubectl describe ns dev
```

### ➤ Delete Namespace
```bash
kubectl delete ns dev
```

### ➤ Create resource inside specific namespace
```bash
kubectl apply -f app.yaml -n dev
```

### ➤ Get resources from specific namespace
```bash
kubectl get pods -n kube-system
```

---

## 📄 Namespace YAML (`namespace.yaml`)
```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: dev
```

---

# 🚀 2. Kubernetes ConfigMap

ConfigMap is used to store **non-confidential data** in key-value format.

### ✔ What You Can Store in ConfigMap?
- App configurations  
- Environment variables  
- Entire config files  
- JSON or properties file  

---

## 📘 ConfigMap Commands

### ➤ Create ConfigMap (File)
```bash
kubectl create configmap app-config --from-file=config.txt
```

### ➤ List ConfigMaps
```bash
kubectl get configmap
```

### ➤ Describe ConfigMap
```bash
kubectl describe configmap app-config
```

### ➤ Delete ConfigMap
```bash
kubectl delete configmap app-config
```

---

## 📄 ConfigMap YAML (`configmap.yaml`)
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  app_name: "my-application"
  log_level: "info"
  message: "Welcome to Kubernetes ConfigMap"
```

---

# 🚀 3. Kubernetes Secrets

Secrets store **confidential and sensitive data** in **Base64 encoded** form.

### ✔ What You Can Store in Secrets?
- Passwords  
- API keys  
- Certificates  
- Tokens  
- DB credentials  

---

## 📘 Secret Commands

### ➤ Create Secret (Literal)
```bash
kubectl create secret generic db-secret --from-literal=username=admin --from-literal=password=pass123
```

### ➤ Create Secret (File)
```bash
kubectl create secret generic ssl-cert --from-file=cert.pem
```

### ➤ List Secrets
```bash
kubectl get secrets
```

### ➤ Describe Secret
```bash
kubectl describe secret db-secret
```

### ➤ Delete Secret
```bash
kubectl delete secret db-secret
```

---

## 📘 Base64 Encoding & Decoding

### Encode:
```bash
echo -n "admin123" | base64
```

### Decode:
```bash
echo -n "YWRtaW4xMjM=" | base64 --decode
```

---

## 📄 Secret YAML (`secret.yaml`)
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: db-secret
type: Opaque
data:
  username: YWRtaW4=
  password: cGFzczEyMw==
```

---

# 🚀 4. Using ConfigMap & Secret in a Pod

## 📄 Pod Example (`pod-using-config-secret.yaml`)
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: demo-pod
spec:
  containers:
  - name: app
    image: nginx
    env:
    - name: APP_NAME
      valueFrom:
        configMapKeyRef:
          name: app-config
          key: app_name

    - name: DB_USER
      valueFrom:
        secretKeyRef:
          name: db-secret
          key: username
```

---

# ✅ Conclusion

### ✔ Namespaces  
Used for isolation and organization.

### ✔ ConfigMaps  
Store **non-sensitive** configuration data.

### ✔ Secrets  
Store **sensitive** data in Base64 encoded format.

All three are essential for real-world Kubernetes deployments.

---

Need next topics?  
I can generate **Deployments, Services, Pods, StatefulSets, Volumes** as `.md` files too!
