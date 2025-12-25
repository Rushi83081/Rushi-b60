# ⚙️ Kubernetes Workloads
---

## 🧱 StatefulSet

- A StatefulSet is used for applications that need fixed names and permanent storage, like databases.
- Each Pod gets a unique name and keeps its data even after restart, unlike a Deployment.
 
## 🔑 Key Characteristics of StatefulSet

- 🏷️ **Stable Pod Names**  
  Pods have fixed, predictable names like `mongo-0`, `mongo-1`, `mongo-2`.

- 🔁 **Ordered Deployment & Termination**  
  Pods are created, updated, and deleted **in a specific sequence**.

- 🌐 **Headless Service Support**  
  Uses a **Headless Service** to provide **stable DNS records** for each Pod.

- 💾 **Persistent Storage per Pod**  
  Each Pod gets its **own Persistent Volume**, and data is **not shared** with other Pods.

---

## ✅ When to Use a StatefulSet

- 🗄️ **Databases**  
  PostgreSQL, MySQL, MongoDB, Cassandra

- 🔗 **Distributed / Clustered Systems**  
  ZooKeeper, Kafka, RabbitMQ

- 🔐 **Identity-Sensitive Workloads**  
  Applications where **Pod identity, ordering, replication, or failover** is critical

---

## 🎯 One-Line Summary (Interview Ready)

> **StatefulSet is used for applications that need stable Pod names, ordered operations, and persistent storage.**

---


## StatefulSet.yaml

```yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: web

spec:
  serviceName: "web"
  replicas: 3

  selector:
    matchLabels:
      app: web

  template:
    metadata:
      labels:
        app: web
    spec:
      containers:
        - name: web
          image: nginx
          ports:
            - containerPort: 80

  volumeClaimTemplates:
    - metadata:
        name: web-data
      spec:
        accessModes:
          - ReadWriteOnce
        resources:
          requests:
            storage: 1Gi

```

### 🧾 Useful StatefulSet Commands

Create from manifest
```
kubectl apply -f statefulset.yaml
```
List StatefulSets
```
kubectl get statefulsets
kubectl get sts
```
Describe a specific StatefulSet
```
kubectl describe statefulset web
```
List Pods created by the StatefulSet
```
kubectl get pods -l app=web
```
Scale a StatefulSet
```
kubectl scale statefulset web --replicas=5
```
Delete a StatefulSet but keep persistent volumes (PVCs)
```
kubectl delete statefulset web
```
---

## 🛰️ DaemonSet

### 📘 What is a DaemonSet?

A **DaemonSet** ensures that **one copy of a Pod runs on every node**  
(or on a **selected subset of nodes**) in a Kubernetes cluster.

It is commonly used for **cluster-wide services** such as logging, monitoring, and storage agents.

---

## 🔑 Key Characteristics of DaemonSet

- 🖥️ **One Pod per Node**  
  Automatically runs a Pod on **every node** (or nodes matching selectors/taints).

- 🔄 **Automatic Node Handling**  
  - When a node is **added**, a Pod is created automatically  
  - When a node is **removed**, the Pod is deleted automatically

- 🛠️ **Node-Level Responsibilities**  
  Ideal for workloads that must run **directly on each node**.

---

## ✅ When to Use a DaemonSet

- 📜 **Log Collection**  
  Fluentd, Filebeat, Logstash

- 📊 **Monitoring Agents**  
  Prometheus Node Exporter, Datadog Agent

- 🌐 **Networking & Storage Components**  
  CNI plugins, storage daemons, security agents

---

## 🎯 One-Liner

> **A DaemonSet ensures that a Pod runs on every node in a Kubernetes cluster.**

## deamonSet.yaml

```yaml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: node-logger

spec:
  selector:
    matchLabels:
      app: node-logger

  template:
    metadata:
      labels:
        app: node-logger
    spec:
      containers:
        - name: logger
          image: my-logger-image:latest
          resources:
            limits:
              cpu: "100m"
              memory: "128Mi"
```

### 🧾 Useful DaemonSet Commands

Create from manifest
```
kubectl apply -f daemonset.yaml
```
List DaemonSets
```
kubectl get daemonsets
kubectl get ds
```
Delete a DaemonSet
```
kubectl delete daemonset node-logger
```

## 🚦 Canary Deployment

### 📘 What is a Canary Deployment?

A **Canary Deployment** is a **release strategy**, not a Kubernetes object.  
It gradually sends a **small portion of traffic** to a new application version, observes its behavior, and then either **rolls forward or rolls back**.

This approach **reduces risk** compared to deploying a new version to all users at once.

---

## 🔑 Key Characteristics of Canary Deployment

- 🔁 **Two Versions Running Together**  
  - **Stable (v1)** → current version  
  - **Canary (v2)** → new version

- 📊 **Partial Traffic Routing**  
  Initially route a small percentage of traffic (e.g., **5–10%**) to the canary version.

- 📈 **Gradual Traffic Increase**  
  Traffic is increased step-by-step if the canary performs well.

- 🔙 **Quick Rollback**  
  If issues are detected, traffic is immediately routed back to the stable version.

---

## ✅ Typical Canary Deployment Flow

1️⃣ **Deploy v1 (Stable)**  
Deploy the current version behind a Service (e.g., `my-app-svc`).

2️⃣ **Deploy v2 (Canary)**  
Deploy the new version using:
- A separate Deployment  
- Or adjusted labels / replica counts

3️⃣ **Configure Traffic Routing** using:
- 🌐 Ingress Controllers (NGINX Ingress, Traefik)  
- 🧩 Service Mesh (Istio, Linkerd)  
- 🤖 Progressive Delivery Tools (Flagger, Argo Rollouts)

4️⃣ **Increase Traffic Gradually**  
Example flow:  
`5% → 20% → 50% → 100%`

5️⃣ **Monitor & Decide**  
Monitor:
- Latency
- Error rate
- CPU / Memory usage

✔ Success → complete rollout  
❌ Failure → rollback to stable version

---

## 🎯 Interview One-Liner

> **Canary deployment releases a new version to a small set of users first to reduce deployment risk.**
---

## canary.yaml

### 🔹 Deployment (Stable)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app-stable

spec:
  replicas: 8
  selector:
    matchLabels:
      app: my-app
      version: v1

  template:
    metadata:
      labels:
        app: my-app
        version: v1
    spec:
      containers:
        - name: app
          image: my-app:v1
```

### 🧾 Useful Canary Commands

Check Deployments and Pods
```
kubectl get deploy
kubectl get pods -l app=my-app -o wide
```
Update image for the canary (e.g., new version)
kubectl set image deployment/my-app-canary app=my-app:v2.1

Scale canary up/down to change traffic share (if using replica-based weighting)
```
kubectl scale deployment my-app-canary --replicas=4
kubectl scale deployment my-app-stable --replicas=6
```
Roll back canary easily by scaling it down to zero or updating image
```
kubectl scale deployment my-app-canary --replicas=0
```
