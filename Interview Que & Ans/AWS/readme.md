### 1️⃣ What is Cloud Computing?

### 💡 Answer:
Cloud computing delivers on-demand computing resources like servers, storage, databases, and applications over the internet. It provides scalability, flexibility, and pay-as-you-go pricing, eliminating the need for upfront hardware investment.

### 2️⃣ Explain Cloud Service Models

### 💡 Answer: 
Cloud has three main service models:

IaaS (Infrastructure as a Service): Provides virtualized computing resources like EC2.

PaaS (Platform as a Service): Offers a platform for building apps without managing infrastructure.

SaaS (Software as a Service): Fully managed software accessed via browser or API, like Gmail or Salesforce.

3️⃣ Explain Deployment Models in Cloud

💡 Answer:

Public Cloud: Resources are shared and managed by a cloud provider.

Private Cloud: Resources are dedicated to a single organization.

Hybrid Cloud: Combines public and private for flexibility.

Multi-Cloud: Uses multiple providers to avoid vendor lock-in.

4️⃣ Explain IAM Service

💡 Answer: AWS Identity and Access Management (IAM) controls access to AWS resources securely. It allows creating users, groups, and roles, assigning permissions, and enforcing security policies.

5️⃣ Explain Policies in IAM

💡 Answer: Policies are JSON documents that define what actions are allowed or denied on AWS resources. They can be attached to users, groups, or roles to manage permissions effectively.

6️⃣ Explain Roles in IAM

💡 Answer: Roles grant temporary access to AWS resources for users, applications, or services without sharing permanent credentials. They are ideal for cross-account access or services like EC2.

7️⃣ Difference between Roles and Policies

💡 Answer:

Roles: Assign temporary permissions to entities.

Policies: Define what actions are allowed or denied.
Roles use policies to specify permissions.

8️⃣ Explain EC2 Service

💡 Answer: Amazon EC2 provides resizable virtual servers in the cloud for running applications. You can scale capacity, choose operating systems, and pay only for what you use.

9️⃣ Explain Instance Types and Purchasing Options

💡 Answer:

Instance Types: Optimized for CPU, memory, storage, or GPU workloads.

Purchasing Options:

On-Demand: Pay per hour/second.

Reserved: Lower cost for long-term use.

Spot: Use spare capacity at discounted rates.

Savings Plans: Flexible pricing for consistent workloads.

🔟 Difference between AMI and Snapshot

💡 Answer:

AMI (Amazon Machine Image): Template for launching instances with preconfigured OS and apps.

Snapshot: Backup of an EBS volume, used for recovery or creating new volumes.

1️⃣1️⃣ Explain EBS Volume Types

💡 Answer:

General Purpose SSD (gp3/gp2): Balanced performance.

Provisioned IOPS SSD (io2/io1): High-performance workloads.

Throughput Optimized HDD (st1): Big data/streaming.

Cold HDD (sc1): Low-cost, infrequent access.

1️⃣2️⃣ Explain Concept of Load Balancing

💡 Answer: Load balancing distributes incoming traffic across multiple servers to improve availability, reliability, and performance, preventing single-server overload.

1️⃣3️⃣ Difference between ALB and NLB

💡 Answer:

ALB (Application Load Balancer): Operates at Layer 7, supports HTTP/HTTPS, advanced routing, and host/path-based rules.

NLB (Network Load Balancer): Operates at Layer 4, handles TCP traffic, ultra-low latency, ideal for performance-critical apps.

1️⃣4️⃣ Explain Auto Scaling

💡 Answer: Auto Scaling automatically adjusts EC2 instances based on traffic demand. It ensures high availability and cost efficiency by adding or removing instances dynamically.

1️⃣5️⃣ Explain S3 Service and Its Advantages

💡 Answer: Amazon S3 is object storage offering high durability, scalability, and availability. Advantages include easy data retrieval, security, cost-effectiveness, and global accessibility.

1️⃣6️⃣ Difference between S3, EFS, and EBS

💡 Answer:

S3: Object storage, highly scalable.

EFS: Shared file storage, NFS protocol, elastic and scalable.

EBS: Block storage for EC2, persistent and high-performance.

1️⃣7️⃣ Explain S3 Storage Classes

💡 Answer:

Standard: Frequent access.

Intelligent-Tiering: Auto-optimizes cost.

Infrequent Access: Rarely accessed.

Glacier / Deep Archive: Long-term, low-cost storage.

1️⃣8️⃣ What is Lifecycle Policy in S3

💡 Answer: Lifecycle policies automate object management in S3, like moving objects between storage classes or deleting old data to optimize cost.

1️⃣9️⃣ Explain VPC Service

💡 Answer: Amazon VPC lets you create a private network in AWS, controlling subnets, IP ranges, routing, and security for resources.

2️⃣0️⃣ Difference between Public and Private Subnet

💡 Answer:

Public Subnet: Has internet gateway access.

Private Subnet: No direct internet access; used for sensitive workloads.

2️⃣1️⃣ Explain NAT

💡 Answer: NAT (Network Address Translation) allows instances in private subnets to access the internet securely without exposing them directly.

2️⃣2️⃣ Explain Peering Connection

💡 Answer: VPC Peering allows secure private communication between two VPCs without traversing the public internet.

2️⃣3️⃣ Difference between NACL and SG

💡 Answer:

NACL: Subnet-level firewall, stateless, controls inbound/outbound traffic.

SG: Instance-level firewall, stateful, tracks connections automatically.

2️⃣4️⃣ What is Domain Name

💡 Answer: A human-readable web address mapped to an IP using DNS, making websites accessible without memorizing IPs.

2️⃣5️⃣ What is Hosted Zone

💡 Answer: A container in Route 53 that holds DNS records for a domain and manages how traffic is routed.

2️⃣6️⃣ Explain Records in Route 53

💡 Answer: DNS records like A, CNAME, MX, TXT define how domain traffic is routed to servers or services.

2️⃣7️⃣ Explain Routing Policies

💡 Answer: Route 53 uses routing policies like Simple, Weighted, Latency, Failover, and Geolocation to control traffic flow for domains.

2️⃣8️⃣ Explain Concept of SSL

💡 Answer: SSL encrypts data between client and server, ensuring secure communication and protecting sensitive information online.

2️⃣9️⃣ Explain CDN

💡 Answer: A Content Delivery Network caches and delivers content closer to users, reducing latency and improving performance globally.

3️⃣0️⃣ What is Edge Location

💡 Answer: Edge locations are CDN points of presence worldwide that serve cached content to reduce latency.

3️⃣1️⃣ Explain OAC/OAI in CloudFront

💡 Answer: Origin Access Identity (OAI) / Origin Access Control (OAC) restricts S3 bucket access so only CloudFront can serve the content securely.

3️⃣2️⃣ What is Latency

💡 Answer: Latency is the delay between sending a request and receiving a response in a network, impacting performance.
