1️⃣ What is Cloud Computing?
💡 Answer:

Cloud computing delivers on-demand computing resources like servers, storage, databases, and applications over the internet.
It offers scalability, flexibility, and pay-as-you-go pricing, removing the need for upfront hardware investment.

2️⃣ Explain Cloud Service Models
💡 Answer:

Cloud has three main service models:

IaaS (Infrastructure as a Service): Provides virtualized resources like EC2

PaaS (Platform as a Service): Platform to build apps without managing infrastructure

SaaS (Software as a Service): Fully managed software via browser/API (e.g., Gmail, Salesforce)

3️⃣ Explain Deployment Models in Cloud
💡 Answer:

Public Cloud: Shared resources managed by cloud provider

Private Cloud: Dedicated resources for a single organization

Hybrid Cloud: Combination of public & private cloud

Multi-Cloud: Uses multiple providers to avoid vendor lock-in

4️⃣ Explain IAM Service
💡 Answer:

AWS IAM (Identity and Access Management) securely controls access to AWS resources by managing users, groups, roles, and permissions.

5️⃣ Explain Policies in IAM
💡 Answer:

IAM Policies are JSON documents that define allowed or denied actions on AWS resources.
They are attached to users, groups, or roles.

6️⃣ Explain Roles in IAM
💡 Answer:

IAM Roles provide temporary access to AWS resources without sharing credentials.
Used for EC2 services and cross-account access.

7️⃣ Difference between Roles and Policies
💡 Answer:

Roles: Grant temporary permissions

Policies: Define what actions are allowed or denied
➡️ Roles use policies to get permissions

8️⃣ Explain EC2 Service
💡 Answer:

Amazon EC2 provides resizable virtual servers to run applications with flexible OS selection and pay-as-you-go pricing.

9️⃣ Explain Instance Types and Purchasing Options
💡 Answer:

Instance Types: Optimized for CPU, memory, storage, or GPU

Purchasing Options:

On-Demand: Pay per second/hour

Reserved: Lower cost for long-term use

Spot: Unused capacity at discount

Savings Plans: Flexible long-term pricing

🔟 Difference between AMI and Snapshot
💡 Answer:

AMI: Template to launch EC2 with OS & software

Snapshot: Backup of an EBS volume

1️⃣1️⃣ Explain EBS Volume Types
💡 Answer:

gp3 / gp2: General purpose SSD

io2 / io1: High IOPS workloads

st1: Throughput-optimized HDD

sc1: Cold HDD for infrequent access

1️⃣2️⃣ Explain Concept of Load Balancing
💡 Answer:

Load Balancing distributes traffic across multiple servers to ensure high availability, reliability, and performance.

1️⃣3️⃣ Difference between ALB and NLB
💡 Answer:

ALB: Layer 7, HTTP/HTTPS, path-based routing

NLB: Layer 4, TCP traffic, ultra-low latency

1️⃣4️⃣ Explain Auto Scaling
💡 Answer:

Auto Scaling automatically adds or removes EC2 instances based on traffic, ensuring cost efficiency and high availability.

1️⃣5️⃣ Explain S3 Service and Its Advantages
💡 Answer:

Amazon S3 is object storage offering high durability, scalability, security, and global access.

1️⃣6️⃣ Difference between S3, EFS, and EBS
💡 Answer:

S3: Object storage

EFS: Shared file system (NFS)

EBS: Block storage for EC2

1️⃣7️⃣ Explain S3 Storage Classes
💡 Answer:

Standard: Frequent access

Intelligent-Tiering: Automatic cost optimization

IA: Infrequent access

Glacier / Deep Archive: Long-term storage

1️⃣8️⃣ What is Lifecycle Policy in S3
💡 Answer:

Lifecycle policies automate data movement and deletion to reduce storage cost.

1️⃣9️⃣ Explain VPC Service
💡 Answer:

Amazon VPC allows you to create a private network with full control over IP ranges, subnets, routing, and security.

2️⃣0️⃣ Difference between Public and Private Subnet
💡 Answer:

Public Subnet: Internet accessible

Private Subnet: No direct internet access

2️⃣1️⃣ Explain NAT
💡 Answer:

NAT enables private subnet instances to access the internet without being publicly exposed.

2️⃣2️⃣ Explain Peering Connection
💡 Answer:

VPC Peering enables private communication between two VPCs securely.

2️⃣3️⃣ Difference between NACL and SG
💡 Answer:

NACL: Subnet-level, stateless

Security Group: Instance-level, stateful

2️⃣4️⃣ What is Domain Name
💡 Answer:

A domain name is a human-readable address mapped to an IP using DNS.

2️⃣5️⃣ What is Hosted Zone
💡 Answer:

A Hosted Zone stores DNS records and manages traffic routing in Route 53.

2️⃣6️⃣ Explain Records in Route 53
💡 Answer:

Records like A, CNAME, MX, TXT control how traffic reaches AWS services.

2️⃣7️⃣ Explain Routing Policies
💡 Answer:

Route 53 routing policies include Simple, Weighted, Latency, Failover, and Geolocation.

2️⃣8️⃣ Explain Concept of SSL
💡 Answer:

SSL encrypts data between client and server for secure communication.

2️⃣9️⃣ Explain CDN
💡 Answer:

A CDN delivers content from nearby locations to reduce latency and improve speed.

3️⃣0️⃣ What is Edge Location
💡 Answer:

Edge locations cache content close to users to reduce response time.

3️⃣1️⃣ Explain OAC / OAI in CloudFront
💡 Answer:

OAI / OAC restricts S3 access so only CloudFront can serve content.

3️⃣2️⃣ What is Latency
💡 Answer:

Latency is the time delay between request and response in a network.
