# Module 5 - Storage and Databases

## Learning Objectives

- Summarize the basic concept of storage and databases.
- Describe the benefits of Amazon Elastic Block Store (Amazon EBS).
- Describe the benefits of Amazon Simple Storage Service (Amazon S3).
- Describe the benefits of Amazon Elastic File System (Amazon EFS).
- Summarize various storage solutions.
- Describe the benefits of Amazon Relational Database Service (Amazon RDS).
- Describe the benefits of Amazon DynamoDB.
- Summarize various database services.

## Instances Stores and Amazon Elastic Block Store (Amazon EBS)

- When you're using Amazon EC2 to run your business applications, those applications need access to CPU, memory, network, and storage. 
- EC2 instances give you access to all those different components. As applications run, they will often need access to block-level storage.
- You can think of block-level storage as a place to store files. A file being a series of bytes that are stored in blocks on disc. 
- When a file is updated, the whole series of blocks aren't all overwritten. 
- **Instead, it updates just the pieces that change.** 
- This makes it an **efficient storage type when working with applications like databases, enterprise software, or file systems**.
- When you launch an EC2 instance, depending on the type of the EC2 instance you launched, it might provide you with local storage called instance store volumes. 
- These volumes are physically attached to the host, your EC2 instances running on top of. And you can write to it just like a normal hard drive. 
- Since this volume is attached to the underlying physical host, if you stop or terminate your EC2 instance, **all data written to the instance store volume will be deleted**.

### Instance Stores --> for temporary data

Block-level storage volumes behave like physical hard drives

- An `instance store` provides temporary block-level storage for an Amazon EC2 instance.  An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance.  When the instance is terminated, you lose any data in the instance store.

`Amazon Elastic Block Store (Amazon EBS)` --> for data you want to keep
- is a service that provides block-level storage volumes that you can use with EC2 instances.  If an EC2 instance is stopped or terminated, data will persist on an EBS volume.
- To create an EBS volume, you define the configuration (such as volume size and type) and provision it.  
- After you create an EBS volume, it can attach to an EC2 instance
- Because EBS volumes are for data that needs to persist, it's important to back up the data.  
- You can take incremental backups of EBS volumes by creating Amazon EBS snapshots

`Amazon EBS Snapshots` --> incremental backups.  
- This means that the first backup taken of a volume copies all the data.  
- For subsequence backups, only the blocks of data that have changed since the most recent snapshot are saved.
- Incremental backups are different from full backups, in which all the data in a storage volume copies each time a backup occurs.  
- The full backup includes data that has not changed since the most recent backup

## `Amazon Simple Storage Service` `S3` -> high durability

'Object storage' -> good for documents, images, video files
- Each ``object`` consist of `data`, `metadata`, and a `key`
- The data might be an image, video, text document, or any other type of file. 
- Metadata contains information about what the data is, how it is used, the object size, and so on. 
- An object’s key is its unique identifier.

> Recall that when you modify a file in block storage, only the pieces that are changed are updated. When a file in object storage is modified, the *entire object* is updated.

Vs. `Bloack storage` -> can break up to blocks

``Amazon S3``
- a data store that allows you to store and retrieve an unlimited amount of data at any scale.
- Store data as objects / Provides ``object-level storage``
- Store objects in buckets / Data is stored as ``Objects`` and put inside of ``Buckets``
  - An Object is like a file and a Bucket is like a directory
- Upload a maximum object size of 5 TB
- Version objects / Has Object versioning to protect from accidental deletion of an Object
- Can create permissions on who can access your Buckets and Objects

``Amazon S3 storage class``
- consider these two factors:
How often you plan to retrieve your data
How available you need your data to be

`S3 Standard` -> for frequently accessed data
- e.g. websites, content distribution, data analytics
- Stores data in a minimum of three Availability Zones
- for infrequently accessed data and archival storage -> higher cost


`S3 standard-IA(Infrequent Access)` -> for infrequently accessed data but high availability 
- high availability means immediately available when needed. 
- Similar to Amazon S3 Standard but has a lower storage price and higher retrieval price
- store data in a minimum of three Availability Zones

`S3 One Zone-IA` -> for cost-saving or easily repoduced data when AZ fails
- Stores data in a single Availability Zone
- Has a lower storage price than Amazon S3 Standard-IA

`S3 intelligent-tiering` -> for data with unknown or changing access patterns
- Requires a small monthly monitoring and automation fee per object
 
> If you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier

> If you access an object in the infrequent access tier, Amazon S3 automatically moves it to the frequent access tier, Amazon S3 Standard.
 

`S3 glacier instant retrieval` -> for archived data that requires immediate access

- Can retrieve objects within a few milliseconds ( same performance as Amazon S3 Standard)


`S3 glacier flexible retrieval` -> for Low-cost storage data archiving

- e.g. old photos, video files, customer records

- Able to retrieve objects within a few minutes to hours

`S3 glacier deep archive` -> Lowest-cost object storage class for archiving

- for data that will be accessed once or twice in a year.
- Able to retrieve objects within 12 hours 
- stored across at least three geographically dispersed Availability Zones.

`S3 outposts` -> delivers object storage to on-premises AWS Outposts environment
- Creates S3 buckets on Amazon S3 Outposts

- Makes it easier to retrieve, store, and access data on AWS Outposts




### `EBS` Vs. `S3`

`S3` -> good for complete objects
- unlimited storage
- individual objects up to 5 TBs
- write once/read many
- 11 9's of durability

- Web Enabled (URL)
- Regionally Distributed (no backup needed)
- Offers cost savings
- Serverless
- use object storage
- store data in a single AZ

`EBS` -> good for complex read, right, change functions
- size up to 16 TiB
- survive termination of EC2 instances
- solid state by default
- HDD option
- use block storage 
- Micro-edits on videos and other data
- Complex read/write/update functions



## `Amazon Elastic File System (EFS)` 

### `file storage`

- multiple instances(users, applications, servers, ...) can access data that is stored in shared file folders.  
- In this approach, a storage server uses block storage with a local file system to organize files.  Clients access data through file paths.
- Compared to **block storage** or **object storage**, file storage is ideal for use cases in which a large number of services or resources need access to the same data at the same time


### `Amazon EFS` 
- a scalable file system used with AWS Cloud services and on-premises resources.  
- As you add or remove files, EFS grows and shrinks automatically. It can scale on demand to petabytes without disrupting applications

## Comparing `EBS` and `EFS`

`EBS`
- volume attach to EC2 instances
- stores data in a **single Availability Zone**
- need to be in the same AZ to attach EC2 instancess

`EFS` 
- can have multiple instances reading & writing simultaneously
- Linux file system
- Regional resource.  It stores data in and across **multiple Availability Zones**
- The duplicate storage enables you to access data concurrently from all the AZ's in a region where a file system is located.
- Automatically scales
- Additionally, on-premises servers can access `Amazon EFS` using `AWS Direct Connect`

## `Amazon Relational Database Service` `RDS` -> for relational database

`relational database`
- data is stored in a way that related it to other pieces of data
- use `structured query language (SQL)` to store and query data.  This allows data to be stored in an easily understandable, consistent, and scalable way
- like a standard MySQL Database, require a well defined schema, in place. That might consist of one, or many tables that might relate to each other. You then use SQL to query the data.

`Amazon RDS` 
an RDBMS (Relational Database Management System) that allows you to run relational databases in the Cloud

**Benefits**:
  - Automated Patching
  - Backups
  - Redundancy
  - Failover
  - Disaster Recovery
 
- Automates tasks such as provisioning, database setup, patching, and backups.
- Can be paired up with other services such as **Lambda**
- Provides a number of different security options.  Many Amazon RDS database engines offer encryption at rest (protecting data while it is stored) and encryption in transit (protecting data while it is being sent and received)

`*Amazon RDS` 
is available on 6 database engines, which optimize for memory, performance, or input/output (I/O).  
Supported engines include:
  - `Amazon Aurora`
  - `PostreSQL`
  - `MySQL`
  - `MariaDB`
  - `Oracle Database`
  - `Microsoft SQL Server`

### `Amazon Aurora` -> for relational(SQL) database

- An enterprise-class relational database.  
- It is compatible with MySQL and PostgreSQL relational databases.  
- 1/10 cost of commercial databases
- It is up to **5 times** faster than standard MySQL databases and up to **3 times** faster than standard PostgreSQL databases
- Amazon Aurora helps to reduce your database costs by reducing unnecessary Input/Output (I/O) operations, while ensuring that your database resources remain reliable and available
- Consider Amazon Aurora if your workloads require high availability.  
- It replicates 6 copies of your data across three AZ's and continuously backs up your data to `Amazon S3`

## `Amazon DynamoDB` -> for nonrelational(NoSQL) database

`Nonrelational databases`

- “NoSQL databases” because they use structures other than rows and columns to organize data. 
- One type of structural approach for nonrelational databases is key-value pairs. 
- With key-value pairs, data is organized into items (keys), and items have attributes (values). 
- You can think of attributes as being different features of your data.
- have simple flexible schemas, not complex rigid schemas, laying out multiple tables that all relate to each other.

`DynamoDB`
- A serverless (no need to install/maintain/operate) key-value database service
- You create **tables**, a place where you can store and query data.
  - Data is organized into **items** that have **attributes** (different features of data)
- If you have one item in your table, or 2 million items in your table, DynamoDB manages the underlying storage for you. And you don't need to worry about the scaling of the system, up or down.
  
- DynamoDB stores this data redundantly across availability zones and mirrors the data across multiple drives under the hood for you. This makes the burden of operating a highly available database, much lower.
- DynamoDB, beyond being massively scalable, is also highly performant. DynamoDB has a **millisecond response time**. And when you have applications with potentially million of users, having scalability and reliable lightning fast response times is important.
  
- With DynamoDB, you can **add and remove attributes from items in the table, at any time**. Not every item in the table has to have the same attributes. This is great for datasets that have some variation from item to item. Because of this flexibility, you cannot run complex SQL queries on it. Instead, you would write queries based on a small subset of attributes that are designated as keys.
- Because of this, the queries that you run are non-relational databases tend to be simpler, and focus on a collection of items from one table, not queries than span multiple tables. This query pattern, along with other factors, including the way that the underlying system is designed, allows DynamoDB to be **very quick in response time**, and **highly scalable**
  
- NoSQL DB, purpose built with specific use cases, and not the best fit for **every** workload out there.  Has a 1ms response time.  
- Fully managed, highly scalable.

## Comparing `RDS` and `DynamoDB`

`RDS` -> complex relationships between data 
- automatic high availability, recovery provided
- customer ownership of data
- customer ownership of schema
- customer control of network

`DynamoDB` -> simple data / look up
- use key-value pair requires no schema
- massive throughput capabilities
- PB size potential
- Granular API access


## `Amazon Redshift` -> can be started with simple API call

- `Amazon Redshift` is a data warehousing service that you can use for big data analytics
- Offers the ability to collect data from many sources and helps you to understand relationships and trends across data

## `AWS Database Migration Service``DMS`

- Enables you to migrate relational databases, nonrelational databases, and other types of data stores.
- You move data between **source database** and **target database**
- The source and target databases can be of the **same type or different types.**
- During the migration, your source database remains operational, reducing downtime for any applications that rely on the database.

- **Homogenous Databases** are databases of the **same type**

- **Heterogeneous Databases** are databases of **different types**
  - You will utilize the **AWS Schema Conversion Tool** to create a new schema


Can also be used for:
1. Development and testing database migrations 
 - Enabling developers to test applications against production data without affecting production users

2. Database consolidation
- Combining several databases into a single database

3. Continuous database replication 
- Sending ongoing copies of your data to other target sources instead of doing a one-time migration



## Additional Database Services

- There is no one-size-fits-all database for all purposes:
  - `Amazon DocumentDB` -> content management, catalog, user profiles
    - A **document** database service that supports MongoDB workloads. (MongoDB is a document database program.)
  - `Amazon Neptune` -> social network, recommendation engine, fraud detection
    - A **graph** database service. You can use Amazon Neptune to build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.
  - `Amazon Quantum Ledger Database (Amazon QLDB)` -> immutable records
    - A **ledger** database service. You can use Amazon QLDB to review a complete history of all the changes that have been made to your application data.
  - `Amazon Managed Blockchain` -> financial records, blockchain
    - A service that you can use to create and manage **blockchain** networks with open-source frameworks. Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.
  - `Amazon ElastiCache` -> for heavy launch, uplift, maintenance
    - A service that adds **caching layers** on top of your databases to help improve the read times of common requests. It supports two types of data stores: **Redis** and **Memcached**.
  - `Amazon DynamoDB Accelerator (DAX)` -> has native caching layer 
    - An **n-memory cache** for DynamoDB. It helps improve response times from single-digit milliseconds to microseconds.

## Additional Resources

- [Instance Stores](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html)
- [Amazon Elastic Block Store (Amazon EBS)](https://aws.amazon.com/ebs)
- [Cloud Storage on AWS](https://aws.amazon.com/products/storage)
- [AWS Storage Blog](https://aws.amazon.com/blogs/storage/)
- [Hands-On Tutorial: Storage](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23storage&awsf.getting-started-content-type=content-type%23hands-on)
- [AWS Customer Stories: Storage](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23storage)
- [AWS Database Migration Service](https://aws.amazon.com/dms/)
- [Databases on AWS](https://aws.amazon.com/products/databases)
- [Category Deep Dive: Databases](https://aws.amazon.com/getting-started/deep-dive-databases/)
- [AWS Database Blog](https://aws.amazon.com/blogs/database/)
- [AWS Customer Stories: Databases](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23databases)
