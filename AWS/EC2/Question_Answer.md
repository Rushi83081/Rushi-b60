# AWS – **Top 50 Important Interview Questions & Answers**

This **README.md** contains **50 most important AWS interview questions**, formatted clearly for **GitHub, exams, and interviews**.

---

## 1. **What is virtualization and why is it important in cloud computing?**

👉 **Virtualization** allows multiple **virtual machines (VMs)** to run on a single physical server. It improves **hardware utilization**, **workload isolation**, and enables **scalability and flexibility** in cloud environments.

---

## 2. **Differentiate IaaS, PaaS, and SaaS with examples.**

👉

* **IaaS (Infrastructure as a Service)**: EC2, EBS, VPC
* **PaaS (Platform as a Service)**: Elastic Beanstalk
* **SaaS (Software as a Service)**: Gmail, Salesforce

---

## 3. **Explain AWS Regions and Availability Zones (AZs).**

👉 A **Region** is a **geographical location**, and an **Availability Zone (AZ)** is an **isolated data center** within a region. Using multiple AZs provides **high availability** and **fault tolerance**.

---

## 4. **What is an EC2 instance type and how do you choose one?**

👉 An **EC2 instance type** defines **CPU, memory, storage, and networking capacity**. Choose it based on workload needs such as **general purpose**, **compute-optimized**, or **memory-optimized**.

---

## 5. **What is an EC2 instance family?**

👉 An **instance family** groups similar instance types (e.g., **T, M, C**). Each family is optimized for specific workloads like **general**, **compute-intensive**, or **memory-intensive** applications.

---

## 6. **Describe the steps to launch an EC2 instance.**

👉 **Choose AMI → Select instance type → Configure network & storage → Configure security group → Create key pair → Launch instance**.

---

## 7. **What is EC2 user data?**

👉 **User data** is a script that runs at instance launch to **automate tasks** such as installing software, configuring services, or starting applications.

---

## 8. **What is EC2 instance metadata?**

👉 **Instance metadata** provides information like **instance ID, private IP, AMI ID** and can be accessed from inside the instance using:
`http://169.254.169.254`

---

## 9. **What is an AMI and why is it used?**

👉 An **Amazon Machine Image (AMI)** is a template containing the **OS, software, and configuration**, used to launch EC2 instances quickly and consistently.

---

## 10. **Difference between AMI and Snapshot.**

👉

* **AMI**: Used to launch EC2 instances
* **Snapshot**: Backup of an **EBS volume** stored in S3

---

## 11. **What are Security Groups?**

👉 **Security Groups** act as **virtual firewalls** at the instance level. They are **stateful** and control **inbound and outbound traffic**.

---

## 12. **Difference between Security Group and NACL.**

👉

* **Security Group**: Instance-level, **stateful**, allow rules only
* **NACL**: Subnet-level, **stateless**, allow and deny rules

---

## 13. **Difference between public and private subnet.**

👉 A **public subnet** has a route to an **Internet Gateway**, while a **private subnet** does not and usually accesses the internet through a **NAT Gateway**.

---

## 14. **Why should databases be placed in a private subnet?**

👉 For **security reasons**. Private subnets prevent direct internet access and allow controlled access only from application servers.

---

## 15. **What is Auto Scaling?**

👉 **Auto Scaling** automatically increases or decreases EC2 instances based on demand, ensuring **high availability**, **scalability**, and **cost efficiency**.

---

## 16. **What is Elastic Load Balancing (ELB)?**

👉 **ELB** distributes incoming traffic across multiple EC2 instances and integrates with **Auto Scaling** for fault tolerance.

---

## 17. **Difference between ALB and NLB.**

👉

* **ALB (Application Load Balancer)**: Layer 7, HTTP/HTTPS, path-based routing
* **NLB (Network Load Balancer)**: Layer 4, TCP traffic, ultra-low latency

---

## 18. **What happens if one EC2 instance fails behind ELB?**

👉 ELB **health checks** detect the failure and automatically route traffic to **healthy instances only**.

---

## 19. **What is a Placement Group?**

👉 A **Placement Group** is a logical grouping of instances to optimize **network latency**, **throughput**, or **fault tolerance**.

---

## 20. **Difference between Availability Zone and Placement Group.**

👉 **AZ** is a physical data center location, while a **Placement Group** is a logical grouping of EC2 instances.

---

## 21. **What is Amazon EBS?**

👉 **Elastic Block Store (EBS)** is block-level storage attached to EC2 instances, mainly used for **OS, applications, and databases**.

---

## 22. **Difference between EBS and S3.**

👉

* **EBS**: Block storage, attached to one EC2 instance
* **S3**: Object storage, highly scalable and durable

---

## 23. **Types of EBS volumes and use cases.**

👉

* **gp3 / gp2**: General workloads
* **io1 / io2**: High IOPS databases
* **st1**: Throughput-intensive workloads
* **sc1**: Cold data storage

---

## 24. **What is Provisioned IOPS (PIOPS)?**

👉 **PIOPS** provides consistent high performance for **I/O intensive workloads** like databases.

---

## 25. **How to resize an EBS volume?**

👉 Modify volume size → Extend partition → Resize filesystem. Always take a **snapshot** before resizing.

---

## 26. **What is an EBS snapshot?**

👉 An **EBS snapshot** is a point-in-time backup stored in S3, used for **backup and disaster recovery**.

---

## 27. **Best practices for encrypting EBS volumes.**

👉 Enable encryption by default, use **AWS KMS keys**, and enforce encryption using **IAM policies**.

---

## 28. **Difference between EBS-backed and Instance-store-backed EC2.**

👉

* **EBS-backed**: Persistent storage
* **Instance-store**: Temporary storage, data lost on stop

---

## 29. **How to monitor EC2 and EBS performance?**

👉 Use **Amazon CloudWatch** for metrics, alarms, logs, and monitoring.

---

## 30. **What is IAM?**

👉 **Identity and Access Management (IAM)** controls access to AWS resources using **users, roles, groups, and policies**.

---

## 31. **Difference between IAM User and Role.**

👉

* **User**: Permanent identity
* **Role**: Temporary permissions (recommended for EC2)

---

## 32. **Best practice for EC2 accessing S3.**

👉 Attach an **IAM Role** to EC2 instead of using access keys.

---

## 33. **What is VPC peering?**

👉 **VPC Peering** enables private communication between two VPCs using AWS backbone network.

---

## 34. **How can EC2 access the internet from a private subnet?**

👉 Using a **NAT Gateway** with proper **route table** configuration.

---

## 35. **What is Amazon EFS?**

👉 **Elastic File System (EFS)** provides shared file storage that can be mounted on multiple EC2 instances.

---

## 36. **Difference between EBS and EFS.**

👉 **EBS** is single-instance block storage, while **EFS** is shared file storage.

---

## 37. **How to automate EBS backups?**

👉 Use **AWS Backup** or **EventBridge + Lambda** for scheduled snapshots.

---

## 38. **What is Route 53?**

👉 **Amazon Route 53** is a DNS service used for domain routing and health checks.

---

## 39. **Difference between A, CNAME, and Alias records.**

👉

* **A**: Domain to IP
* **CNAME**: Domain to domain
* **Alias**: AWS resource mapping

---

## 40. **What is CloudFront?**

👉 **Amazon CloudFront** is a CDN that caches content globally to reduce latency.

---

## 41. **How does DNS resolution work?**

👉 Browser → Resolver → Root → TLD → Authoritative DNS → IP returned.

---

## 42. **What is AWS Lambda?**

👉 **AWS Lambda** is a serverless compute service where you run code without managing servers.

---

## 43. **Difference between Lambda and EC2.**

👉 **Lambda** is serverless and auto-scales, while **EC2** requires server management.

---

## 44. **How to trigger Lambda automatically?**

👉 Using **S3 events, EventBridge schedules, API Gateway, or CloudWatch alarms**.

---

## 45. **What is Amazon CloudWatch?**

👉 **CloudWatch** monitors AWS resources using metrics, logs, and alarms.

---

## 46. **What are custom CloudWatch metrics?**

👉 Application-specific metrics pushed using **CLI, SDK, or CloudWatch Agent**.

---

## 47. **How to centralize logs from EC2?**

👉 Install **CloudWatch Agent** and send logs to **CloudWatch Logs**.

---

## 48. **What is Amazon RDS?**

👉 **Relational Database Service (RDS)** is a managed database service supporting MySQL, PostgreSQL, and more.

---

## 49. **How to enable high availability in RDS?**

👉 Enable **Multi-AZ deployment** with automatic failover.

---

## 50. **Design a highly available and scalable web application.**

👉 Use **Multi-AZ EC2**, **ALB**, **Auto Scaling**, **CloudFront**, **Route 53**, **S3**, and **RDS Multi-AZ**.

---

✅ **Formatted perfectly for GitHub README and AWS interviews**
