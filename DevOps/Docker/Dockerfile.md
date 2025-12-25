📘 Dockerfile

🔹 What is a Dockerfile?

* A Dockerfile is a text document that contains a set of instructions used to build a Docker image.
* It automates the process of creating images by defining the environment, dependencies, and commands needed to run an application inside a container.

   ---
🔹 Components of a Dockerfile

----------

1. FROM

* Specifies the base image for the container.
* Example:
```
FROM ubuntu:20.04
```
2. MAINTAINER / LABEL

* Defines metadata about the image creator.
* Example:
```
LABEL maintainer="abhipraydh96@gmail.com"
```
3. RUN

* Executes commands inside the image while building.
* Example:
```
RUN apt-get update && apt-get install -y nginx
```
4. COPY / ADD

* Copies files from host machine to the image.
* Example:
```
COPY index.html /usr/share/nginx/html/
```
5. WORKDIR

* Sets the working directory inside the container.
* Example:
```
WORKDIR /app
```
6. EXPOSE

* Defines the port number the container listens on.
* Example:
```
EXPOSE 80
```
7.CMD

* Provides the default command to run when the container starts.
* Example:
```
CMD ["nginx", "-g", "daemon off;"]
```
8. ENTRYPOINT

* Configures a container to run as an executable.
* Example:
```
ENTRYPOINT ["nginx"]
```

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

🔹 Example 2: Create Dockerfile to host httpd webserver
```
FROM amazonlinux:2023    
RUN yum update -y && yum install httpd -y 
COPY index.html /var/www/html 
EXPOSE 80
CMD ["httpd", "-D", "FOREGROUND"]
```

🔹 Example 3: Create Dockerfile to host nginx webserver
```
FROM ubuntu
RUN apt-get update -yum
RUN apt install nginx -y 
COPY index.html /var/www/html/
CMD ["nginx", "-g", "daemon off;"]
```
