# 🚀 Jenkins CI/CD Pipeline 
---

## 🔧 **What is Jenkins?**

Jenkins is an open-source automation server used to build, test, and deploy applications using **CI/CD pipelines**.

---

## 📐 **Architecture Overview**

* **Controller (Master):** Manages jobs, scheduling, and coordination.
* **Agent (Worker Node):** Executes build and deployment tasks.

---

## 🛠️ **Features**

* ✔️ Continuous Integration & Continuous Deployment (CI/CD)
* ✔️ Supports Freestyle, Pipeline, and Multibranch projects
* ✔️ 1,800+ plugins
* ✔️ Integrates with Git, Maven, Docker, AWS, Kubernetes, etc.

---

## 📁 **Project Types**

### **1. Freestyle Project**

Simple graphical jobs for basic automation.

### **2. Pipeline Project**

Code-based automation using a **Jenkinsfile**.

---

## 📝 **Sample Jenkinsfile**

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building project..."
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
            }
        }
    }
}
```

---

## 🔑 **Credentials Supported**

* Username/Password
* SSH Keys
* AWS Access Keys
* API Tokens
* Secret Text

---

## ⚙️ **Build Triggers**

* ⏱️ Scheduled (Cron)
* 🔗 Webhook from GitHub/GitLab
* 🔄 Poll SCM
* ▶️ Manual trigger

---

## 🐳 **Jenkins + Docker Example**

```groovy
pipeline {
    agent {
        docker {
            image 'maven:3.9.4'
        }
    }

    stages {
        stage('Build with Maven') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
```

---

## ☁️ **Integrations**

* **Version Control:** Git, GitHub, GitLab, Bitbucket
* **Build Tools:** Maven, Gradle, Node.js
* **Cloud:** AWS, Azure, GCP
* **Container Tools:** Docker, Kubernetes

---

## 📦 **Jenkins Home Directory**

```
/var/lib/jenkins/
```

Contains:

* Jobs
* Configurations
* Plugins
* Credentials

---

## ⭐ **Advantages**

* Open-source & free
* Huge plugin ecosystem
* Highly customizable pipelines

## ⚠️ **Disadvantages**

* UI is outdated
* Heavy usage may require scaling

---

## 🙌 **Contribute**

Feel free to fork this repository and create PRs to improve Jenkins examples.

---

### 🏁 **Happy DevOps!** 🚀

