# ⚙️ Kubernetes Workloads
---

## 🧱 StatefulSet

A **StatefulSet** manages stateful applications that need stable network identities and persistent storage per Pod (like databases, queues, or clustered systems).  
Unlike Deployments, Pods in a StatefulSet have ordered, unique names and can keep data across restarts using persistent volumes.[web:32][web:35]

### 🔑 Key Characteristics

- Stable Pod names such as `mongo-0`, `mongo-1`, `mongo-2`.[web:32]  
- Ordered deployment and termination (Pods are created and deleted in a specific sequence).[web:31][web:33]  
- Typically uses a **Headless Service** for stable DNS records per Pod.[web:31][web:32]  
- Designed for apps needing **persistent volumes** and per-Pod storage that should not be shared.[web:32][web:35]

### ✅ When to Use StatefulSet

- Databases (PostgreSQL, MySQL, MongoDB, Cassandra).[web:33][web:35]  
- Distributed systems that need stable identities and storage (e.g., ZooKeeper, Kafka, RabbitMQ).[web:34][web:38]  
- Any workload where Pod identity and ordering matter for replication or failover.[web:32][web:38]

## StatefulSet.yaml
```
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
accessModes: ["ReadWriteOnce"]
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

A **DaemonSet** ensures that a copy of a Pod runs on **every node** (or on a selected subset of nodes).  
It is typically used for cluster-wide agents such as logging, monitoring, or storage daemons.[web:36][web:39]

### 🔑 Key Characteristics

- Automatically runs one Pod per node (or per matching node selector / taint rules).[web:36]  
- When a node is added, a Pod is automatically scheduled onto it; when a node is removed, its Pod is deleted.[web:36][web:39]  
- Ideal for node-level functionality like log collection, metrics, or networking agents.[web:36][web:39]

### ✅ When to Use DaemonSet

- Log collectors (Fluentd, Filebeat, Logstash) on every node.[web:36][web:39]  
- Monitoring agents (Prometheus node exporter, Datadog agent) on all nodes.[web:36][web:39]  
- Network plugins or storage daemons that must run node-wide.[web:36]

## deamonSet.yaml
```
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
---

## 🚦 Canary Deployment

A **canary deployment** is a **release strategy**, not a separate Kubernetes object.  
It gradually shifts a small portion of traffic to a new version, observes its behavior, and then either rolls forward or rolls back, reducing risk compared to an all-at-once rollout.[web:37][web:40]

### 🔑 Key Characteristics

- Run **two versions** at the same time: stable (current) and canary (new).[web:37]  
- Route only a small percentage (for example 5–10%) of traffic to the canary initially.[web:37][web:40]  
- Increase traffic in steps after successful monitoring; if issues appear, roll back quickly.[web:37][web:40]

### ✅ Typical Canary Flow

1. **Deploy v1 (stable)** under a Service (e.g., `my-app-svc`).  
2. **Deploy v2 (canary)** using another Deployment or by adjusting replicas/labels.  
3. Use one of:
   - Weighted routing via Ingress / Service mesh (NGINX Ingress, Istio, Linkerd, Traefik, etc.).  
   - Tools like **Flagger**, **Argo Rollouts**, etc., for automated progressive delivery.[web:37][web:40]  
4. Gradually increase the percentage of traffic to v2 (e.g., 5% → 20% → 50% → 100%).[web:37][web:40]  
5. Monitor metrics (latency, error rate, CPU) and **either complete rollout or roll back**.[web:40]

## canary.yaml
```
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

apiVersion: v1
kind: Service
metadata:
name: my-app-svc
spec:
selector:
app: my-app
ports:
- port: 80
- targetPort: 80
```
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
