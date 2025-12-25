# ☸️ **Kubernetes (K8s) Overview**

Kubernetes (**K8s**) is an **open-source container orchestration platform** that automates the **deployment**, **scaling**, and **management** of containerized applications.

* **container orchestration platform** :- automatically manages containers — it starts them, stops them, scales them, and fixes them if they fail.
---

## ⚙️ **Why Kubernetes?**

- 🔁 **Scalability:** Automatically scales applications based on demand.  
- ⚡ **Self-Healing:** Automatically restarts failed containers and replaces unhealthy ones.  
- 🌐 **Load Balancing:** Efficiently distributes traffic across containers.  
- 🧠 **Declarative Configuration:** Define your *desired state* and let Kubernetes maintain it.  
- ☁️ **Cloud Native:** Works seamlessly across **any cloud provider** (AWS, Azure, GCP, etc.).

---

## 🏗️ **Core Components**

| 🧩 **Component** | 📝 **Description** |
| ---------------- | ----------------- |
| **Pod** | Smallest deployable unit in Kubernetes (one or more containers). |
| **Deployment** | Defines the desired state for Pods and manages updates. |
| **Service** | Exposes applications to the network (internal or external). |
| **Ingress** | Manages **external access** to services (e.g., HTTP/HTTPS). |
| **ConfigMap / Secret** | Store **configuration data** and **sensitive information** securely. |

---
# 🚀 **Kubernetes Architecture Explained**

## 🧠 Master Node (Control Plane)

The **master node** is the **brain** of the Kubernetes cluster — it controls and manages the whole system.

### Key Components:

- 🔹 **API Server**  
  The front door for all commands and requests (from users or tools like `kubectl`).  
  *Everything flows through here first!*

- 🔹 **Scheduler**  
  Decides **which worker node** should run your app’s pods, based on available resources.

- 🔹 **Controller Manager**  
  Watches over the cluster, ensuring apps are running smoothly.  
  Automatically fixes problems by restarting pods or managing resources.

- 🔹 **etcd**  
  A lightweight, distributed **key-value database** storing the entire cluster’s state and configurations.

---

## ⚙️ Worker Node (App Executor)

Worker nodes are where your applications **actually run** — inside containers managed by Kubernetes.

### Key Components:

- 🔹 **Container Runtime**  
  Software like **Docker** or **containerd** that runs your app inside containers.

- 🔹 **kube-proxy**  
  Handles networking and communication between pods and services.  
  Manages IP addresses and load balancing.

- 🔹 **kubelet**  
  The agent on each worker node.  
  Listens to the master’s instructions and manages pods accordingly.  
  Reports status back to the control plane.

---

## 🗂️ Quick Summary Table

| Component          | Node Type   | Description                                       |
|--------------------|-------------|-------------------------------------------------|
| **API Server**     | Master      | Receives all requests and commands               |
| **Scheduler**      | Master      | Chooses nodes to run pods                         |
| **Controller Manager** | Master   | Keeps apps healthy and running                    |
| **etcd**           | Master      | Stores cluster data and config                    |
| **Container Runtime** | Worker    | Runs containers (your app)                        |
| **kube-proxy**     | Worker      | Manages networking between pods                   |
| **kubelet**        | Worker      | Runs pods and reports status to master            |

---

## 📝 Notes to Remember

- A **Pod** is the smallest deployable unit in Kubernetes — usually contains **one container**, but can hold more.  
- A **Node** is a machine (physical or virtual) —  
- The **master node** manages the cluster,  
- The **worker nodes** run your applications.

---
## 1. Check Existing Pods

```bash
kubectl get pods
```

2. Run a Pod (Create a Pod) :- 
Creates a pod named my-pod using the nginx image.
```bash
kubectl run my-pod --image=nginx
```

3. Expose the Pod (Create a Service) :- Creates a service to expose the pod my-pod on port 80.
```bash
kubectl expose pod my-pod --type=NodePort --port=80 --target-port=80
```

4. Check Services :- Lists all services in the current namespace.
```bash
kubectl get services
```

5. Execute Command Inside a Pod (Login) :- Starts an interactive bash shell inside the my-pod container.
```bash
kubectl exec -it my-pod -- /bin/bash
```
* After Login :-
```bash
curl http://<cluster_ip>:80
```

6. Delete the Pod :- Deletes the pod named my-pod.
```bash
kubectl delete pod my-pod
```

7. Delete the Service :- Deletes the service exposing the pod.
```bash
kubectl delete service my-pod
```

---
