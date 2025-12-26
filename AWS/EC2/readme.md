# ☁️ **Amazon EC2 (Elastic Compute Cloud) – Overview**

Amazon **EC2** is a web service that provides **resizable compute capacity** in the cloud.  
It allows you to **launch virtual servers** (instances) on demand and scale them easily.

---

## ⚙️ **Key Features**

| 🚀 Feature | 📝 Description |
| ----------- | --------------- |
| **Elasticity** | Scale up/down instantly based on workload. |
| **Pay-as-you-go** | Pay only for what you use. |
| **Multiple Instance Types** | Choose CPU, memory, and storage configurations. |
| **Custom AMIs** | Create your own Amazon Machine Images. |
| **Security Groups** | Virtual firewalls for inbound/outbound traffic. |

---

## 🧠 **Use Cases**

- 🖥️ Hosting Web Applications  
- 🧮 Running Big Data Jobs  
- ⚙️ CI/CD Build Servers  
- 🧰 Application Backend Hosting  
- 🎮 Game Server Deployment

---

⭐ *EC2 = Your on-demand cloud-based computer.*

# 🧩 **Core Components of Amazon EC2**

---

Amazon EC2 consists of several building blocks that work together to deliver flexible, scalable, and secure compute power in the cloud.

---

## 🖥️ **1. EC2 Instances**

An **EC2 Instance** is a **virtual server** running on AWS infrastructure.  
Each instance provides different combinations of **CPU, memory, storage, and networking** capabilities to match specific workload needs.

---

### 💡 **Instance Types**

AWS categorizes EC2 instances into **families** based on their performance and use case:

| 🏷️ **Instance Family** | 💻 **Example Type** | 🧠 **Best For** |
| ----------------------- | ------------------ | --------------- |
| **General Purpose** | `t3`, `t4g`, `m5`, `m6i` | Balanced compute, memory, and networking (e.g., web servers, dev environments) |
| **Compute Optimized** | `c5`, `c6g`, `c7i` | High-performance compute workloads like gaming or scientific modeling |
| **Memory Optimized** | `r5`, `r6g`, `x2idn` | Applications needing large memory (e.g., in-memory databases) |
| **Storage Optimized** | `i3`, `i4i`, `d2` | High I/O workloads such as big data or NoSQL databases |
| **Accelerated Computing** | `p4`, `g5`, `inf2` | GPU/AI/ML workloads requiring hardware acceleration |

📘 **Tip:** Choose your instance family based on workload type and performance requirements.

---

# EC2 Purchasing Options

## 1. On-Demand Instances

**Description:** Pay per second/hour with no long-term commitment.

**Use Cases:**

* Short-term workloads
* Testing and development
* Unpredictable traffic

* No upfront cost
* Highly flexible

* Most expensive option

---

## 2. Reserved Instances (RI)

**Description:** Commit to a 1-year or 3-year term for discounted pricing.

**Types:**

* Standard Reserved Instances
* Convertible Reserved Instances

**Use Cases:**

* Steady-state applications
  
* Long-term production workloads

* Up to ~72% cost savings compared to On-Demand

* Long-term commitment required

---

## 3. Spot Instances

**Description:** Use spare AWS capacity at very low cost. Instances can be interrupted with short notice.

**Important:**

* AWS can terminate instances with a 2-minute warning

**Use Cases:**

* Batch processing
* Data analytics
* CI/CD jobs

* Cheapest option (up to ~90% discount)

* Not suitable for critical or long-running workloads

---

## 4. Dedicated Host

**Description:** A physical server dedicated to a single customer.

**Use Cases:**

* Compliance requirements
* Bring Your Own License (BYOL)
* Full control over physical hardware
* Meets regulatory and licensing needs
* Most expensive option

---

## Quick Comparison

| Option         | Cost    | Commitment | Best For               |
| -------------- | ------- | ---------- | ---------------------- |
| On-Demand      | High    | None       | Short-term workloads   |
| Reserved       | Medium  | 1–3 Years  | Long-term applications |
| Spot           | Lowest  | None       | Fault-tolerant jobs    |
| Dedicated Host | Highest | 1–3 Years  | Compliance & licensing |

---

## 💾 **2. AMI (Amazon Machine Image)**

An **AMI** is a **template** that defines the software configuration of your instance.  
It includes:
- Operating System (e.g., Amazon Linux, Ubuntu, Windows)
- Application server (e.g., Apache, Nginx)
- Preinstalled applications or configurations

🧱 **Use Case:** You can create a **custom AMI** after setting up your preferred environment to reuse later.

---

## 🌐 **3. EBS (Elastic Block Store)**

Amazon **EBS** provides **persistent block storage** for EC2 instances.  
It behaves like a **hard disk**, retaining data even after the instance stops.

### 🔸 **EBS Volume Types:**
| Type | Description |
|------|--------------|
| **gp3 / gp2 (SSD)** | General-purpose, balanced price and performance |
| **io2 / io1 (SSD)** | High-performance SSD for critical workloads |
| **st1 / sc1 (HDD)** | Low-cost magnetic storage for large, sequential workloads |

📦 **Note:** You can attach multiple EBS volumes to a single instance.

---

## 🔒 **4. Security Groups**

A **Security Group** acts as a **virtual firewall** controlling inbound and outbound traffic to your EC2 instances.

- You can specify **allowed ports**, **protocols**, and **IP ranges**.
- Security Groups are **stateful** — if you allow inbound traffic, the corresponding outbound response is automatically allowed.

💡 Example Rule:
| Type | Protocol | Port | Source |
|------|-----------|------|--------|
| SSH | TCP | 22 | Your IP |
| HTTP | TCP | 80 | 0.0.0.0/0 |

---

## 🛜 **5. Elastic IP (EIP)**

An **Elastic IP** is a **static public IPv4 address** assigned to your account.  
It allows you to:
- Maintain a **consistent IP** even if the instance stops or restarts.
- Quickly **remap IPs** between instances for failover or maintenance.

⚠️ **Note:** AWS charges for unused Elastic IPs — release them when not in use.

---

## 🧭 **6. Key Pairs**

**Key Pairs** are used for **secure SSH authentication** to your EC2 instances.

- When you launch an instance, you can select or create a key pair.
- AWS stores the **public key**, and you store the **private key (.pem file)**.

🔐 Example SSH command:
```bash
ssh -i mykey.pem ec2-user@<public-ip>
```
# ⚙️ **EC2 Configuration & Management**

Amazon EC2 gives you full control to configure, connect, monitor, and manage your virtual servers in the AWS Cloud.  
Below are the **detailed steps** for setting up and managing EC2 instances effectively.

---

## 🧰 **1. Launching an EC2 Instance**

You can launch an instance using the **AWS Management Console** or **AWS CLI**.  
Here’s how you can do it step by step using the **Console** 👇

---

### 🪜 **Step-by-Step via AWS Console**

1. **Sign in to AWS Console**  
   Go to 👉 [https://console.aws.amazon.com/ec2](https://console.aws.amazon.com/ec2)

2. **Click “Launch Instance”**  
   Choose a **name** for your instance (e.g., `MyFirstEC2`).

3. **Select an AMI (Amazon Machine Image)**  
   - Example: `Amazon Linux (Free Tier eligible)`  
   - You can also choose Ubuntu, Windows, or a custom AMI.

4. **Choose Instance Type**  
   - Example: `t3.micro` (1 vCPU, 1 GB RAM) – Free Tier eligible  
   - Select based on workload type.

5. **Configure Key Pair (SSH Key)**  
   - Create a **new key pair** or select an existing one.  
   - Example Key Name: `my-ec2-key.pem`

6. **Configure Network Settings**
   - Select a **VPC** and **Subnet**.
   - Allow inbound ports such as:
     - `22` → SSH
     - `80` → HTTP (for web apps)

7. **Add Storage**
   - Default: 8 GB EBS volume  
   - You can increase size for databases or heavy workloads.

8. **Review & Launch**
   - Review all settings and click **Launch Instance** 🚀

---
## For More - 
https://github.com/abhipraydhoble/devops-b60/tree/d8ae7094b83c8baf64959978ddd68f768ce59537/AWS/EC2
