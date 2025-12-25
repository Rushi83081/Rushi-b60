# 🧩 Overview

* **Docker** is a platform that enables developers to build, package, and run applications in containers, which are lightweight and portable environments that include everything an application needs to run.

## ⚙️ Why Docker?

**🚀 Lightweight**: Uses fewer resources than VMs.

**🔁 Consistency**: Works across any environment — “It works on my machine” problem solved.

**🧱 Isolation**: Each container runs in its own environment.

**🔧 Speed**: Faster deployments and rollbacks.

**🌍 Portability**: Run anywhere — cloud, on-prem, or local machine.

# 🛠️ Core Concepts

| Concept        | Description                                         |
| -------------- | --------------------------------------------------- |
| **Image**      | A blueprint for containers (e.g., Ubuntu + Nginx).  |
| **Container**  | A running instance of an image.                     |
| **Dockerfile** | A script with instructions to build a Docker image. |
| **Docker Hub** | Repository to store and share images.               |
| **Volume**     | Persistent data storage for containers.             |

# 🧱 Basic Commands

**1.Build an image**
```bash
docker build -t myapp .
```
**2.Run a container**
```bash
docker run -itd --name c1 -p 80:80 myapp
```
**3.List containers**
```bash
docker ps
```
**4.Pull image**
```bash
docker pull nginx
```
**5.Push image to Docker Hub**
```bash
docker push username/myapp
```
**6.Access the container’s shell (interactive mode)**
```bash
docker exec -it <container_id_or_name> /bin/bash
```
**7.Stop and remove containers**
```
docker stop <container_id><br>
docker rm <container_id>
```
