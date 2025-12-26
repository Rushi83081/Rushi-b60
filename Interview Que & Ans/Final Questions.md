# Final Exam Questions
# IAM
```
1. How do you control access to AWS services and resources using IAM?
2. Explain the difference between an AWS user, group, role, and policy.
3. What are the best practices for creating and managing IAM users in AWS?
4. How do you enable multi-factor authentication (MFA) for AWS IAM users?
5. Explain the differences between IAM policies and resource-based policies in AWS.
6. Explain the concept of AWS Security Token Service (STS) and how it relates to temporary credentials in IAM.
7. Limit to attach max no of policies to IAM roles
8. What is trusted entity in aws
9. Describe the process of setting up cross-account access in AWS IAM.
10. How do you rotate access keys for IAM users, and why is key rotation important?
```

# S3
```
1. What is Amazon S3, and what is its primary purpose within the AWS ecosystem?
2. Explain the structure of an S3 object's URL (Uniform Resource Locator).
3. What are the different storage classes available in Amazon S3, and when would you use each one?
4. Describe the difference between an S3 bucket and an S3 object.
5. What is S3 data consistency, and how does it work in different scenarios (e.g., read-after-write consistency, eventual consistency)?
6. How do you secure data stored in an S3 bucket, and what are the key access control mechanisms in S3?
7. Explain the use of S3 bucket policies and IAM policies in controlling access to S3 resources.
8. How can you encrypt data in S3, and what are the encryption options available?
9. What is versioning in S3, and what are its benefits and use cases?
10. Explain the concept of S3 Lifecycle policies and provide examples of when they might be useful.
11. How do you transfer large data into and out of an S3 bucket?
12. How can you replicate data between S3 buckets in different AWS regions or accounts?
13. What is the Amazon S3 Transfer Acceleration feature, and when might you use it?
14. Explain the purpose of Amazon S3 event notifications, and provide examples of use cases.
15. Discuss the advantages and considerations of using Amazon S3 as a content delivery solution (S3 as a static website host or through Amazon CloudFront).
```

# EC2 
```
1. What is an EC2 instance type, and how do you choose the right one for your application?
2. What is an EC2 instance family, and when would you use one family over another?
3. Describe the typical steps involved in launching an EC2 instance.
4. What is an EC2 user data script, and how can it be used during instance launch?
5. Explain the purpose of EC2 instance metadata and how you can access it from within an instance.
6. How can you create custom AMIs, and why might you want to do so?
7. What are security groups, and how do they control inbound and outbound traffic to EC2 instances?
8. Explain the use of Network Access Control Lists (NACLs) and how they differ from security groups.
9. What is Auto Scaling, and how can it be used to ensure high availability and scalability of EC2 instances?
10. Explain the purpose of Amazon Elastic Load Balancing (ELB) and its integration with EC2 instances.
11. What is status check in EC2 instance?
12. How to changes instance types for running application without downtime of application?
13. What is difference between AMI and Snapshot
14. Describe different types of purchasing options available in aws?
15. What are the different types of AWS Placement Groups, and how do they differ?
16. What is the difference between an Availability Zone and a Placement Group?
17. What is Amazon Elastic Block Store (EBS), and how does it differ from Amazon S3
18. What are the different types of EBS volumes available, and when would you use each type (e.g., gp2, io1, st1, sc1, gp3)?
19. Explain the concept of Provisioned IOPS (PIOPS) and when it's necessary for achieving consistent performance.
20. What is an EBS snapshot, and why is it important for data durability and disaster recovery?
21. Describe the difference between EBS-backed and instance-store-backed EC2 instances and their respective advantages and limitations.
```

# Auto Scaling 
```
1. Explain the primary components of AWS Auto Scaling.

2. What is the difference between horizontal and vertical scaling, and how does Auto Scaling facilitate horizontal scaling?

3. How do you determine the desired capacity and minimum capacity for an Auto Scaling group?

4. What is difference between Launch Template and Launch configuration?

5. Explain how scaling policies work in Auto Scaling. What are the different types of scaling policies?

6. How do you configure triggers and alarms for Auto Scaling policies using Amazon CloudWatch?

7. What is a cooldown period in Auto Scaling, and why is it important to configure it correctly?

8. What are lifecycle hooks in Auto Scaling, and how can they be used for advanced customization of instance scaling actions?

9. Explain the concept of mixed instances in an Auto Scaling group and its benefits.
```

# Load Balancing
```
1. When would you choose an Application Load Balancer (ALB) over a Network Load Balancer (NLB), and vice versa?

2. What is a target group in the context of ALB, and how is it used for routing traffic to instances?

3. Explain the concept of listeners and rules in load balancer configuration.

4. What are the health checks performed by AWS load balancers, and how do they impact instance health?

5. How can you ensure session persistence or stickiness for clients using a load balancer in AWS?

6. Explain the use of cross-zone load balancing in AWS, and when would you enable or disable it?

7. What is AWS Web Application Firewall (WAF), and how can it be integrated with a load balancer for application security?

8. What are blue-green deployments, and how can AWS load balancers be used to facilitate this deployment strategy?
```

# VPC 
```
1. What is Amazon Virtual Private Cloud (Amazon VPC), and why is it important in AWS networking?

2. What is the primary difference between a public subnet and a private subnet in a VPC?

3. How do you connect a VPC to an on-premises data center, and what are the options available for this connection?

4. Explain the purpose of Amazon VPC peering and its use cases.

5. What is the significance of route tables in a VPC, and how do you control traffic routing between subnets?

6. What are VPC Endpoints, and how do they enhance security and reduce data transfer costs for certain AWS services?

7. Explain the use of a Bastion Host (Jump Host) in a VPC for secure remote access to instances.

8. Describe the concept of VPC Flow Logs and their benefits for network monitoring and troubleshooting.

9. What is AWS Transit Gateway, and how does it simplify network connectivity and management in complex VPC architectures?

10. Explain the use of AWS PrivateLink for securely accessing AWS services over private connections within a VPC.
```

# Route 53 
```
1. Explain the primary services provided by Amazon Route 53.

2. Walk me through the process of registering a domain name with Amazon Route 53.

3. What are the differences between domain registration and DNS hosting, and how does Route 53 handle both?

4. Explain the various routing policies supported by Route 53, including Simple, Weighted, Latency-Based, Geolocation, and Failover policies.

5. What is the purpose of a weighted routing policy, and when would you use it?

6. How does the latency-based routing policy work, and when is it beneficial for optimizing user experience?

7. What are health checks in Amazon Route 53, and how can they be used to monitor the health of resources?

8. How can you configure a failover routing policy with Route 53, and what role do health checks play in this scenario?

9. Explain different types of records in RT53(Like A, AAAA, NS, SOA, etc.)
```

# RDS 
```
1. Explain the primary database engines supported by Amazon RDS.

2. What are the benefits of using Amazon RDS for database management in AWS?

3. What is a DB instance class, and how do you choose the appropriate instance class for your database?

4. Explain the purpose of the parameter group and security group in RDS configurations.

5. How can you secure data in Amazon RDS, and what encryption options are available?

6. Explain the concepts of Read Replicas and Multi-AZ deployments in Amazon RDS.

7. How do you create and manage automated backups for an Amazon RDS instance?

8. What is the difference between automated backups and database snapshots in RDS?

9. Explain the process of restoring an RDS instance from a snapshot or point-in-time recovery.
```

# Lambda 
```
1. What programming languages are supported for writing Lambda functions, and how can you package and deploy them?

2. Describe the benefits of using AWS Lambda for application development and architecture.

3. What are event sources in Lambda, and how do they enable serverless event-driven applications?

4. Explain the use of Amazon EventBridge (formerly CloudWatch Events) in connecting event sources to Lambda functions.

5. What is concurrency in AWS Lambda, and how is it managed?

6. How does AWS Lambda automatically scale to accommodate high traffic or a large number of requests?

7. Explain the concept of "statelessness" in AWS Lambda, and how can you manage application state when necessary?
```
