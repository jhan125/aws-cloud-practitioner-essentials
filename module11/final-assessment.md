## 1. Which component or service enables you to establish a dedicated private connection between your data center and virtual private cloud (VPC)?

Virtual private gateway -> VPN connection between VPC and private network

Amazon CloudFront -> content delivery service using edge locations

Internet gateway -> connection between VPC and internet

`AWS Direct Connect`

> Answer: `D` 


## 2. You want to store data in a key-value database. Which service should you use?

`Amazon DynamoDB`

Amazon Aurora -> for query data

Amazon DocumentDB -> supports MangoDB workloads

Amazon RDS -> for query data

> Answer: `A`



## 3. Which Perspective of the AWS Cloud Adoption Framework focuses on recovering IT workloads to meet the requirements of your business stakeholders?

Business Perspective 

`Operations Perspective` 

Governance Perspective

People Perspective

> Answer: `B`



## 4. You are running an Amazon EC2 instance and want to store data in an attached resource. Your data is temporary and will not be kept long term. Which resource should you use?

`Instance store`

Amazon Elastic Block Store (Amazon EBS) volume -> data needs to be retained

Amazon S3 bucket -> can't be attached to EC2 instances

Subnet -> section of VPC


> Answer: `A`


## 5. Which service enables you to review details for user activities and API calls that have occurred within your AWS environment?

AWS Trusted Advisor

Amazon CloudWatch

Amazon Inspector

`AWS CloudTrail` 


> Answer: `D`


## 6. Which Support plans include access to all AWS Trusted Advisor checks? (Select TWO.)

`Business` 

Developer

AWS Free Tier

Basic

`Enterprise` 


> Answer: `A` and `E`



## 7. Which service is used to transfer up to 100 PB of data to AWS?

Amazon CloudFront -> content delivery service

`AWS Snowmobile` 

AWS DeepRacer -> test reinforcement learning models

Amazon Neptune -> graph database service


> Answer: `B`



## 8. Which service is used to quickly deploy and scale applications on AWS?

`AWS Elastic Beanstalk` 

AWS Snowball -> transfer data into / out of AWS

AWS Outposts -> run infrastructure in a hybrid cloud approach

Amazon CloudFront -> content delivery service

> Answer: `A`



## 9. Which statement best describes an `Availability Zone`?

`A fully isolated portion of the AWS global infrastructure` 

A separate geographical location with multiple locations that are isolated from each other -> `Region`

A site that Amazon CloudFront uses to cache copies of content for faster delivery to users at any location -> `Edge location`

The server from which Amazon CloudFront gets your files -> `origin`


> Answer: `A`



## 10. Which statement best describes Elastic Load Balancing?

`A service that distributes incoming traffic across multiple targets, such as Amazon EC2 instances`

A service that monitors your applications and automatically adds or removes capacity from your resource groups in response to changing demand -> `AWS Auto Scaling`

A service that provides data that you can use to monitor your applications, optimize resource utilization, and respond to system-wide performance changes -> `Amazon CloudWatch`

A service that enables you to set up, manage, and scale a distributed in-memory or cache environment in the cloud -> `Amazon ElasticCache`

> Answer: `A`



## 11. You want to send and receive messages between distributed application components. Which service should you use?

`Amazon Simple Queue Service (Amazon SQS)`

Amazon ElastiCache

Amazon Route 53

AWS Snowball

> Answer: `A`



## 12. Which actions can you perform in Amazon Route 53? (Select TWO.)

Monitor your applications and respond to system-wide performance changes. -> Amazon CloudWatch

`Connect user requests to infrastructure in AWS and outside of AWS.`

Automate the deployment of workloads into your AWS environment. -> AWS Quick Starts

`Manage DNS records for domain names. `

Access AWS security and compliance reports and select online agreements. -> AWS Artifact

> Answer: `B` and `D`



## 13. Which compute option reduces costs when you commit to a consistent amount of compute usage for a 1-year or 3-year term?

Dedicated Hosts -> your own physical service with EC2 instance capacity

Reserved Instances -> no commitment to consistent compute usage over duration of contract

`Savings Plans` 

Spot Instances -> for workloads with flexible start and end times

> Answer: `C`



## 14. Which tasks are the responsibilities of AWS? (Select TWO.)

Training company employees on how to use AWS services

`Configuring AWS infrastructure devices` 

Configuring security groups on Amazon EC2 instances

Creating IAM users and groups

`Maintaining virtualization infrastructure`

> Answer: `B` and `E`



## 15. Which migration strategy involves changing how an application is architected and developed, typically by using cloud-native features?

Replatforming -> selectively optmize

`Refactoring` 

Repurchasing -> replace with AWS software

Rehosting -> move to cloud with no code change

> Answer: `B`


## 16. Which AWS Trusted Advisor category includes checks for high-utilization EC2 instances?

Cost Optimization -> check unused/idle resources

`Performance`

Security -> review permissions

Fault Tolerance -> improve app's availability and redundancy


> Answer: `B`


## 17. Which service is used to run containerized applications on AWS?

Amazon Aurora -> enterprise-class relational database

Amazon Redshift -> data warehousing service for big data analytics

Amazon SageMaker -> build, train, deploy ML models

`Amazon Elastic Kubernetes Service (Amazon EKS)`

> Answer: `D`



## 18. Which tool is used to automate actions for AWS services and applications through scripts?

AWS Snowball -> transfer data in / out of AWS

Amazon QLDB -> ledger database for data change history

`AWS Command Line Interface`

Amazon Redshift -> data warehousing for big analytics

> Answer: `C`



## 19. Which action can you perform in Amazon CloudFront?

Provision resources by using programming languages or a text file. -> `CloudFormation`

Provision an isolated section of the AWS Cloud to launch resources in a virtual network that you define. -> `VPC`

Run infrastructure in a hybrid cloud approach. -> `AWS Outposts`

`Deliver content to customers through a global network of edge locations.` 

> Answer: `D`



## 20. Which statement best describes AWS Marketplace?

A resource that can answer questions about best practices and assist with troubleshooting issues -> `AWS Support`

`A digital catalog that includes thousands of software listings from independent software vendors` 

An online tool that inspects your AWS environment and provides real-time guidance in accordance with AWS best practices -> `AWS Trusted Advisor`

A resource that provides guidance, architectural reviews, and ongoing communication with your company as you plan, deploy, and optimize your applications -> `TAM`


> Answer: `B`



## 21. You want to store data in a volume that is attached to an Amazon EC2 instance. Which service should you use?

AWS Lambda

Amazon ElastiCache -> add caching layers on top of database

`Amazon Elastic Block Store (Amazon EBS)`

Amazon Simple Storage Service (Amazon S3) -> object-level storage


> Answer: `C`



## 22. Which pillar of the AWS Well-Architected Framework focuses on using computing resources in ways that meet system requirements?

Operational Excellence

`Performance Efficiency` 

Security

Reliability

> Answer: `B`



## 23. Which statement is TRUE for AWS Lambda?

Before using AWS Lambda, you must prepay for your estimated compute time.

To use AWS Lambda, you must configure the servers that run your code.

`You pay only for compute time while your code is running.` 

The first step in using AWS Lambda is provisioning a server.

> Answer: `C`



## 24. Which service enables you to consolidate and manage multiple AWS accounts from a central location?

`AWS Organizations` 

AWS Key Management Service (AWS KMS) -> create, manage, use cryptographic keys

AWS Identity and Access Management (IAM) -> manage access

AWS Artifact -> access security and compliance reports / agreements

> Answer: `A`



## 25. Which service enables you to build the workflows that are required for human review of machine learning predictions?

Amazon Lex -> conversational interface

Amazon Aurora -> enterprise-class relational database

`Amazon Augmented AI` 

Amazon Textract -> extract text and data from scanned docs

> Answer: `C`



## 26. Which statement best describes Amazon GuardDuty?

A service that lets you monitor network requests that come into your web applications -> `AWS WAF`

`A service that provides intelligent threat detection for your AWS infrastructure and resources`

A service that helps protect your applications against distributed denial-of-service (DDoS) attacks -> `Amazon Shield`

A service that checks applications for security vulnerabilities and deviations from security best practices -> `Amazon Inspector`


> Answer: `B`



## 27. Which tool enables you to visualize, understand, and manage your AWS costs and usage over time?

AWS Pricing Calculator -> estimate cost of user cases

AWS Artifact -> access security and compliance reports & agreements

AWS Budgets -> set alerts when usage exceeds

`AWS Cost Explorer`

> Answer: `D`



## 28. Which virtual private cloud (VPC) component controls inbound and outbound traffic for Amazon EC2 instances?

`Security group` -> virtual firewall

Subnet -> section of VPC

Network access control list -> firewall at subnet level

Internet gateway -> allow public traffic from internet to VPC

> Answer: `A`



## 29. In the S3 Intelligent-Tiering storage class, Amazon S3 moves objects between a frequent access tier and an infrequent access tier. Which storage classes are used for these tiers? (Select TWO.)

`Amazon S3 Standard-IA`

Amazon S3 Glacier Flexible Retrieval

`Amazon S3 Standard`

Amazon S3 Glacier Deep Archive

Amazon S3 One Zone-IA

> Answer: `A` and `C`


## 30. You want Amazon S3 to monitor your objects’ access patterns. Which storage class should you use?

Amazon S3 Glacier Flexible Retrieval -> data archiving

Amazon S3 Standard-IA -> infrequently accessed data with high availability

Amazon S3 One Zone-IA -> infrequently accessed data with NO high availability

`Amazon S3 Intelligent-Tiering`


> Answer: `D`
