# Module 9 - Migration and Innovation

## Learning Objectives

- Understand migration and innovation in the AWS Cloud.
- Summarize the AWS Cloud Adoption Framework (AWS CAF). 
- Summarize the six key factors of a cloud migration strategy.
- Describe the benefits of AWS data migration solutions, such as AWS Snowcone, AWS Snowball, and AWS Snowmobile.
- Summarize the broad scope of innovative solutions that AWS offers.

## AWS Cloud Adoption Framework `AWS CAF`

**Six core perspectives of CAF**


***Business Perspective*** -> build a business model integrates IT strategy

ensures that IT aligns with business needs and that IT investments link to key business results.

Common roles in the Business Perspective include: 
- Business managers
- Finance managers
- Budget owners
- Strategy stakeholders

***People Perspective*** -> prepare organization / employees skills for cloud adopatation

evaluate organizational structures and roles, new skill and process requirements, and identify gaps. This helps prioritize training, staffing, and organizational changes.

Common roles in the People Perspective include: 
- Human resources
- Staffing
- People managers

***Governance Perspective*** 

understand how to update the staff skills and processes necessary to ensure that you maximize the business value and minimize risks.

Common roles in the Governance Perspective include: 

- Chief Information Officer (CIO)
- Program managers
- Enterprise architects
- Business analysts
- Portfolio managers

***Platform Perspective*** -> help design, implement, and optmize AWS infrastructure based on business goals

includes principles and patterns for implementing new solutions on the cloud, and migrating on-premises workloads to the cloud.

Common roles in the Platform Perspective include: 
- Chief Technology Officer (CTO)
- IT managers
- Solutions architects


***Security Perspective*** 

ensures that the organization meets security objectives for visibility, auditability, control, and agility. 

Common roles in the Security Perspective include: 

- Chief Information Security Officer (CISO)
- IT security managers
- IT security analysts

***Operations Perspective*** 

enable, run, use, operate, and recover IT workloads to the level agreed upon with your business stakeholders.

Common roles in the Operations Perspective include: 
- IT operations managers
- IT support managers

## Migration strategies

[More explanations in Chinese](https://aws.amazon.com/cn/blogs/china/6-strategies-for-migrating-applications-to-the-cloud/)

**6 R's***

Rehosting -> easy move with no change and more savings
-  `lift-and-shift` involves moving applications without changes. 
-  In the scenario of a large legacy migration, in which the company is looking to implement its migration and scale quickly to meet a business case, the majority of applications are rehosted.  

Replatforming -> optimize then move to Cloud (no code changes)
- `lift, tinker, and shift` involves making a few cloud optimizations to realize a tangible benefit. 
- Optimization is achieved without changing the core architecture of the application

Refactoring/re-architecting -> rebuild at highest cost (code changes)
- `re-architecting` involves re-imagining how an application is architected and developed by using **cloud-native features**. 
- Refactoring is driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the application’s existing environment.

Repurchasing -> replace with other different SaaS product
- moving from a traditional license to a software-as-a-service model. 
- For example, a business might choose to implement the repurchasing strategy by migrating from a customer relationship management (CRM) system to Salesforce.com.

Retaining -> nothing to do
- keeping applications that are critical for the business in the source environment. 
- This might include applications that require major refactoring before they can be migrated, or, work that can be postponed until a later time.

Retiring -> remove to save costs
- process of removing applications that are no longer needed.

## `AWS Snow Family`

a collection of physical devices that help to physically transport up to exabytes of data into and out of AWS. 

`AWS Snow Family` is composed of 3 categories.

1. `AWS Snowcone`
- small, rugged, and secure edge computing and data transfer device. 
- It features 2 CPUs, 4 GB of memory, and 8 TB of usable storage.

2. `AWS Snowball` offers two types of devices:

`Snowball Edge Storage Optimized` devices 
- are well suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs. 
- Storage: 80 TB of hard disk drive (HDD) capacity for block volumes and Amazon S3 compatible object storage, and 1 TB of SATA solid state drive (SSD) for block volumes. 
- Compute: 40 vCPUs, and 80 GiB of memory to support Amazon EC2 sbe1 instances (equivalent to C5).

`Snowball Edge Compute Optimized` 
- provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks. 
- Storage: 42-TB usable HDD capacity for Amazon S3 compatible object storage or Amazon EBS compatible block volumes and 7.68 TB of usable NVMe SSD capacity for Amazon EBS compatible block volumes. 
- Compute: 52 vCPUs, 208 GiB of memory, and an optional NVIDIA Tesla V100 GPU. Devices run Amazon EC2 sbe-c and sbe-g instances, which are equivalent to C5, M5a, G3, and P3 instances.

3. `AWS Snowmobile`
- an exabyte-scale data transfer service used to move large amounts of data to AWS. 
- You can transfer up to 100 petabytes of data per Snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi trailer truck.

### Innovation with AWS

`Serverless applications`
-  applications that don’t require you to provision, maintain, or administer servers. You don’t need to worry about fault tolerance or availability. AWS handles these capabilities for you.
- e.g. `AWS Lambda`

`Artificial intelligence`

you can perform the following tasks:
- Convert speech to text with `Amazon Transcribe`.
- Discover patterns in text with `Amazon Comprehend`.
- Identify potentially fraudulent online activities with `Amazon Fraud Detector`.
- Build voice and text chatbots with `Amazon Lex`.

`Machine learning`

`Amazon SageMaker` to remove the difficult work from the process and empower you to build, train, and deploy ML models quickly.

You can use ML to analyze data, solve complex problems, and predict outcomes before they happen.

## Additional Resouces

[Migration & Transfer on AWS](https://aws.amazon.com/products/migration-and-transfer)
[A Process for Mass Migrations to the Cloud](https://aws.amazon.com/blogs/enterprise-strategy/214-2/)
[6 Strategies for Migrating Applications to the Cloud](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/)
[AWS Cloud Adoption Framework](https://aws.amazon.com/professional-services/CAF/)
[AWS Fundamentals: Core Concepts](https://aws.amazon.com/getting-started/fundamentals-core-concepts/)
