## 🚀 1. What is a ReplicationController (RC)?

A ReplicationController (RC) is a Kubernetes object that ensures a specified number of pod replicas are running at all times.

✔ Key Features

Maintains desired replica count

Recreates pods if they crash

Ensures high availability

Older version (legacy)

Uses selector to match pods

❌ RC is outdated

ReplicationController is old and has been replaced by ReplicaSet.

## 📘 RC Commands
Create RC using YAML
kubectl apply -f rc.yaml

Get all RC
kubectl get rc

Describe RC
kubectl describe rc <name>

Delete RC
kubectl delete rc <name>

## 📄 ReplicationController YAML (rc.yaml)
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

## 🚀 2. What is a ReplicaSet (RS)?

A ReplicaSet (RS) is the newer and improved version of ReplicationController.

✔ Key Features

Maintains desired pod count

Self-healing

Supports label selectors (matchLabels / matchExpressions)

Used internally by Deployments

Replacement for ReplicationController

⭐ Recommended: Always use ReplicaSet or Deployment, not RC.
## 📘 RS Commands
Create ReplicaSet
kubectl apply -f rs.yaml

Get ReplicaSet
kubectl get rs

Describe ReplicaSet
kubectl describe rs <name>

Delete ReplicaSet
kubectl delete rs <name>

## 📄 ReplicaSet YAML (rs.yaml)
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

## 🔍 RC vs RS (Summary Table)
Feature	RC	RS
API Version	v1	apps/v1
Status	Old / Legacy	New / Recommended
Label Selector	Basic	Advanced (matchLabels, matchExpressions)
Used By Deployment	❌ No	✔ Yes
Production Use	Not recommended	✔ Recommended
## ✅ Conclusion

ReplicaSet (RS) is the modern and recommended way to maintain pod replicas.

ReplicationController (RC) is old but still works for backward compatibility.

Most real clusters use a Deployment → which internally uses a ReplicaSet.
