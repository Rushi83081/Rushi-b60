# ☁️ Cloud Computing & AWS – Interview / Exam Notes

This document contains **important Cloud Computing and AWS fundamentals** explained in **simple and clear language** for **exams, interviews, and revision**.

---

## 1️⃣ What is Cloud Computing?

**Answer:**

Cloud computing delivers **on-demand computing resources** such as servers, storage, databases, networking, and applications over the internet.

### Key Benefits:
- Scalability
- Flexibility
- Pay-as-you-go pricing
- No upfront hardware investment

---

## 2️⃣ Cloud Service Models

Cloud computing offers three main service models:

### 🔹 IaaS (Infrastructure as a Service)
- Provides virtualized resources
- Example: Amazon EC2

### 🔹 PaaS (Platform as a Service)
- Platform to build and deploy applications
- No infrastructure management

### 🔹 SaaS (Software as a Service)
- Fully managed software via browser or API
- Examples: Gmail, Salesforce

---

## 3️⃣ Cloud Deployment Models

### 🔹 Public Cloud
- Shared infrastructure
- Managed by cloud provider

### 🔹 Private Cloud
- Dedicated infrastructure
- Used by a single organization

### 🔹 Hybrid Cloud
- Combination of public and private cloud

### 🔹 Multi-Cloud
- Uses multiple cloud providers
- Avoids vendor lock-in

---

## 4️⃣ What is IAM Service?

**AWS IAM (Identity and Access Management)** securely controls access to AWS resources by managing:
- Users
- Groups
- Roles
- Permissions

---

## 5️⃣ What are IAM Policies?

IAM Policies are **JSON documents** that define:
- Allowed actions
- Denied actions
- Resources on which actions are allowed

They are attached to **users, groups, or roles**.

---

## 6️⃣ What are IAM Roles?

IAM Roles provide **temporary access** to AWS resources **without sharing credentials**.

### Common Use Cases:
- EC2 accessing S3
- Lambda accessing AWS services
- Cross-account access

---

## 7️⃣ Difference Between Roles and Policies

| Roles | Policies |
|-----|---------|
| Grant temporary permissions | Define allowed or denied actions |
| Used by AWS services | Attached to users, groups, roles |

➡️ **Roles use policies to get permissions**

---

## 8️⃣ What is EC2?

Amazon EC2 (Elastic Compute Cloud) provides **resizable virtual servers** to run applications.

### Features:
- Flexible OS selection
- Scalable compute
- Pay-as-you-go pricing

---

## 9️⃣ EC2 Instance Types & Purchasing Options

### Instance Types:
- Compute optimized
- Memory optimized
- Storage optimized
- GPU optimized

### Purchasing Options:
- **On-Demand** – Pay per second/hour
- **Reserved** – Lower cost for long-term use
- **Spot** – Unused capacity at discounted price
- **Savings Plans** – Flexible long-term pricing

---

## 🔟 Difference Between AMI and Snapshot

| AMI | Snapshot |
|----|----------|
| Template to launch EC2 | Backup of EBS volume |
| Includes OS & software | Stores only disk data |

---

## 1️⃣1️⃣ EBS Volume Types

- **gp3 / gp2** – General Purpose SSD
- **io2 / io1** – High IOPS workloads
- **st1** – Throughput-optimized HDD
- **sc1** – Cold HDD (low cost)

---

## 1️⃣2️⃣ Load Balancing Concept

Load Balancing distributes incoming traffic across multiple servers to ensure:
- High availability
- Fault tolerance
- Better performance

---

## 1️⃣3️⃣ ALB vs NLB

| ALB | NLB |
|---|---|
| Layer 7 | Layer 4 |
| HTTP / HTTPS | TCP / UDP |
| Path-based routing | Ultra-low latency |

---

## 1️⃣4️⃣ Auto Scaling

Auto Scaling automatically:
- Adds instances during high traffic
- Removes instances during low traffic

Ensures **cost efficiency and availability**.

---

## 1️⃣5️⃣ Amazon S3 & Advantages

Amazon S3 is **object storage** offering:
- High durability (99.999999999%)
- Unlimited scalability
- Strong security
- Global access

---

## 1️⃣6️⃣ Difference Between S3, EFS, and EBS

| S3 | EFS | EBS |
|---|----|----|
| Object storage | File storage (NFS) | Block storage |
| Highly scalable | Shared filesystem | Attached to EC2 |

---

## 1️⃣7️⃣ S3 Storage Classes

- **Standard** – Frequent access
- **Intelligent-Tiering** – Automatic cost optimization
- **Standard-IA / One Zone-IA** – Infrequent access
- **Glacier / Deep Archive** – Long-term storage

---

## 1️⃣8️⃣ S3 Lifecycle Policy

Lifecycle policies automatically:
- Move data between storage classes
- Delete old data

Used to **reduce storage cost**.

---

## 1️⃣9️⃣ Amazon VPC

Amazon VPC allows you to create a **private network** in AWS with control over:
- IP ranges
- Subnets
- Route tables
- Security

---

## 2️⃣0️⃣ Public vs Private Subnet

| Public Subnet | Private Subnet |
|-------------|---------------|
| Internet accessible | No direct internet |
| Uses Internet Gateway | Uses NAT Gateway |

---

## 2️⃣1️⃣ NAT (Network Address Translation)

NAT allows **private subnet instances** to access the internet **without being publicly exposed**.

---

## 2️⃣2️⃣ VPC Peering

VPC Peering enables **private communication** between two VPCs using AWS private network.

---

## 2️⃣3️⃣ NACL vs Security Group

| NACL | Security Group |
|----|---------------|
| Subnet level | Instance level |
| Stateless | Stateful |
| Allow & deny rules | Allow rules only |

---

## 2️⃣4️⃣ What is a Domain Name?

A domain name is a **human-readable address** (example: google.com) mapped to an IP address using DNS.

---

## 2️⃣5️⃣ What is a Hosted Zone?

A Hosted Zone stores **DNS records** and manages traffic routing in **Route 53**.

---

## 2️⃣6️⃣ Route 53 Record Types

Common DNS records:
- **A**
- **CNAME**
- **MX**
- **TXT**
- **Alias**

---

## 2️⃣7️⃣ Route 53 Routing Policies

- Simple
- Weighted
- Latency-based
- Failover
- Geolocation
- Geoproximity

---

## 2️⃣8️⃣ What is SSL?

SSL (Secure Sockets Layer) encrypts data between client and server to ensure **secure communication**.

---

## 2️⃣9️⃣ What is CDN?

A CDN (Content Delivery Network) delivers content from nearby servers to:
- Reduce latency
- Improve performance
- Increase availability

---

## 3️⃣0️⃣ What is an Edge Location?

Edge locations cache content **closer to users**, reducing response time and latency.

---

## 3️⃣1️⃣ OAI / OAC in CloudFront

OAI (Origin Access Identity) and OAC (Origin Access Control) restrict S3 access so **only CloudFront** can serve content.

---

## 3️⃣2️⃣ What is Latency?

Latency is the **time delay** between a request and response in a network.

---

✅ **End of Notes**  
📌 Perfect for **AWS interviews, exams, and revision**
