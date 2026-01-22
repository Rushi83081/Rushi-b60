# 🚀 EC2 & EBS – Important Interview Questions and Answers

---

## 1. **What is an EC2 instance type, and how do you choose the right one for your application?**
👉 An **EC2 instance type** defines the **CPU, memory, storage, and networking capacity**. Choose it based on workload needs such as **general purpose**, **compute-optimized**, **memory-optimized**, or **storage-optimized** instances.

---

## 2. **What is an EC2 instance family, and when would you use one family over another?**
👉 An **instance family** groups similar instance types optimized for workloads:  
- **T / M** → General purpose  
- **C** → Compute-intensive  
- **R / X** → Memory-intensive  
- **I / D** → Storage-intensive  

---

## 3. **Describe the typical steps involved in launching an EC2 instance.**
👉 Select **AMI → Choose instance type → Configure network → Add storage → Configure security group → Create key pair → Launch instance**.

---

## 4. **What is an EC2 user data script, and how can it be used during instance launch?**
👉 **User data** is a script that runs at first boot to **install software, configure services, and automate setup tasks**.

---

## 5. **Explain the purpose of EC2 instance metadata and how you can access it from within an instance.**
👉 **Instance metadata** provides information like **instance ID, IP address, AMI ID**, accessed using  
`http://169.254.169.254` from inside the instance.

---

## 6. **How can you create custom AMIs, and why might you want to do so?**
👉 Create an AMI from a configured instance to **reuse configurations, reduce launch time, and ensure consistency** across environments.

---

## 7. **What are security groups, and how do they control inbound and outbound traffic to EC2 instances?**
👉 **Security Groups** act as **virtual firewalls** at the instance level. They are **stateful** and allow traffic based on **allow rules only**.

---

## 8. **Explain the use of Network Access Control Lists (NACLs) and how they differ from security groups.**
👉 **NACLs** operate at the **subnet level**, are **stateless**, and support **allow and deny rules**, unlike security groups.

---

## 9. **How do you enable and configure AWS WAF in front of an EC2-based web application?**
👉 Deploy **ALB or CloudFront** in front of EC2 and associate **AWS WAF** rules to block malicious traffic like **SQL injection or XSS**.

---

## 10. **What is Auto Scaling, and how can it ensure high availability?**
👉 **Auto Scaling** automatically adjusts EC2 capacity based on demand, ensuring **availability, scalability, and cost optimization**.

---

## 11. **Explain the purpose of Amazon Elastic Load Balancing (ELB).**
👉 **ELB** distributes incoming traffic across multiple EC2 instances and performs **health checks** to route traffic only to healthy instances.

---

## 12. **What is Amazon EC2 Container Service (ECS)?**
👉 **ECS** is a container orchestration service that allows running **Docker containers** on EC2 or Fargate without managing control planes.

---

## 13. **How can you configure Amazon Route 53 for DNS-based load balancing?**
👉 Use **routing policies** like **weighted, latency-based, or failover routing** to distribute traffic across EC2 instances.

---

## 14. **What is status check in an EC2 instance?**
👉 **Status checks** monitor **system health (AWS hardware)** and **instance health (OS issues)** to detect failures.

---

## 15. **How to change instance types without downtime?**
👉 Use **Auto Scaling Group**, **Load Balancer**, or **blue-green deployment** to replace instances with new types seamlessly.

---

## 16. **What is the difference between AMI and Snapshot?**
👉  
- **AMI** → Used to launch EC2 instances  
- **Snapshot** → Backup of EBS volumes  

---

## 17. **How to troubleshoot boot issues like kernel panic in EC2?**
👉 Stop instance → Detach root volume → Attach to another EC2 → Fix kernel/filesystem → Reattach and start.

---

## 18. **How many maximum IPs can be attached to an EC2 instance?**
👉 Depends on **instance type**. Each instance has limits for **ENIs and private IPs** as defined by AWS.

---

## 19. **Describe different EC2 purchasing options.**
👉  
- **On-Demand** → Pay per use  
- **Reserved Instances** → Long-term discount  
- **Savings Plans** → Flexible commitment  
- **Spot Instances** → Cheapest, interruptible  
- **Dedicated Hosts** → Physical server control  

---

## 20. **What are the types of AWS Placement Groups?**
👉  
- **Cluster** → Low latency, high throughput  
- **Spread** → Fault tolerance  
- **Partition** → Large distributed systems  

---

## 21. **Can you change the placement group of a running instance?**
👉 **No**, you must **stop the instance** to change its placement group.

---

## 22. **Difference between Availability Zone and Placement Group.**
👉 **AZ** is a physical data center, while **Placement Group** is a logical grouping within AZs.

---

## 23. **Best practices for Placement Groups.**
👉 Use same **instance types**, same **AZ**, and ensure **capacity availability** before launch.

---

## 24. **Limitations of Placement Groups.**
👉 Cannot span regions, capacity not guaranteed, and limited flexibility.

---

## 25. **EBS volume types and best use cases.**
👉  
- **gp3 / gp2** → General workloads  
- **io1 / io2** → High IOPS databases  
- **st1** → Big data, logs  
- **sc1** → Cold storage  

---

## 26. **What is Amazon EBS and how does it differ from S3?**
👉 **EBS** is block storage for EC2, while **S3** is object storage designed for unlimited scalability.

---

## 27. **Explain Provisioned IOPS (PIOPS).**
👉 **PIOPS** ensures consistent, high-performance I/O for **critical databases**.

---

## 28. **How do you resize an EBS volume safely?**
👉 Modify volume → Extend partition → Resize filesystem → Always take **snapshot backup first**.

---

## 29. **Difference between EBS volume type and size.**
👉 **Volume type** affects performance, while **size** affects capacity and throughput limits.

---

## 30. **What is an EBS snapshot and why is it important?**
👉 Snapshot is a **point-in-time backup** used for **disaster recovery and data durability**.

---

## 31. **How often should EBS snapshots be created?**
👉 Based on data criticality. Use **AWS Backup**, **lifecycle policies**, and **retention rules**.

---

## 32. **Best practices for encrypting EBS volumes.**
👉 Enable **encryption by default**, use **AWS KMS**, and enforce encryption using **IAM policies**.

---

## 33. **Difference between EBS-backed and instance-store-backed EC2.**
👉  
- **EBS-backed** → Persistent storage  
- **Instance-store** → Temporary storage  

---

## 34. **How can you monitor EBS performance and health?**
👉 Use **Amazon CloudWatch**, **CloudWatch Agent**, and **AWS Trusted Advisor**.

---

# ✅ **Additional Important EC2 Questions (Added)**

---

## 35. **What is an Elastic Network Interface (ENI)?**
👉 **ENI** is a virtual network card that allows multiple IPs and network interfaces per EC2.

---

## 36. **What is EC2 Hibernate?**
👉 **Hibernate** saves instance memory to disk and resumes quickly without losing application state.

---

## 37. **Difference between Stop and Terminate EC2 instance.**
👉 **Stop** preserves data, **Terminate** deletes the instance permanently.

---

## 38. **What is a key pair in EC2?**
👉 Used for **secure SSH access** to Linux EC2 instances.

---

## 39. **What is EC2 Spot Fleet?**
👉 A group of **Spot Instances** launched together to reduce costs.

---

## 40. **How do you secure EC2 instances?**
👉 Use **IAM roles**, **security groups**, **patching**, **encryption**, and **monitoring**.

---
