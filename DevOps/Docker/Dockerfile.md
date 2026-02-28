## 📘 Dockerfile

### 📘 What is a Dockerfile?

🔹 **Dockerfile** is a text document that contains a **set of instructions** used to build a Docker image.  
🔹 It **automates image creation** by defining:
- Environment
- Dependencies
- Commands to run an application inside a container

---

## 🧩 Components of a Dockerfile

---

### 🔹 1. `FROM`
📌 Specifies the **base image** for the container.

```dockerfile
FROM ubuntu:20.04
```
---

🔹 2. MAINTAINER / LABEL

📌 Defines metadata about the image creator.
```
LABEL maintainer="gaikwadrushi2005@gmail.com"
```
---

🔹 3. RUN

📌 Executes commands during image build time.
```
RUN apt-get update && apt-get install -y nginx
```
---

🔹 4. COPY / ADD

📌 Copies files from host machine → container image.
```
COPY index.html /usr/share/nginx/html/
```
---

🔹 5. WORKDIR

📌 Sets the working directory inside the container.
```
WORKDIR /app
```
---

🔹 6. EXPOSE

📌 Documents the port on which the container listens.
```
EXPOSE 80
```
---

🔹 7. CMD

📌 Provides the default command to run when the container starts.
```
CMD ["nginx", "-g", "daemon off;"]
```
---

🔹 8. ENTRYPOINT

📌 Configures the container to run as an executable.
```
ENTRYPOINT ["nginx"]
```
---

🔹 Example 1: Dockerfile for Nginx on Ubuntu
```
# Use Ubuntu as base image
FROM ubuntu:20.04

# Install Nginx
RUN apt-get update && \
    apt-get install -y nginx 

# Copy custom index.html
COPY index.html /var/www/html/index.html

# Expose port 80
EXPOSE 80

# Run Nginx in foreground

CMD ["nginx", "-g", "daemon off;"]
```
---

🔹 Example 2: Create Dockerfile to host httpd webserver
```
FROM amazonlinux:2023    
RUN yum update -y && yum install httpd -y 
COPY index.html /var/www/html 
EXPOSE 80
CMD ["httpd", "-D", "FOREGROUND"]
```
---

🔹 Example 3: Create Dockerfile to host nginx webserver
```
FROM ubuntu
RUN apt-get update -yum
RUN apt install nginx -y 
COPY index.html /var/www/html/
CMD ["nginx", "-g", "daemon off;"]
```
