# Module 6 - Security

## Learning Objectives

- Explain the benefits of the shared responsibility model.
- Describe multi-factor authentication (MFA).
- Differentiate between the AWS Identity and Access Management (IAM) security levels.
- Explain the main benefits of AWS Organizations.
- Describe security policies at a basic level.
- Summarize the benefits of compliance with AWS.
- Explain additional AWS security services at a basic level.

## Shared responsibility model

(similar to the division of responsibilities between a homeowner and a homebuilder. The builder (AWS) is responsible for constructing your house and ensuring that it is solidly built. As the homeowner (the customer), it is your responsibility to secure everything in the house by ensuring that the doors are closed and locked. )

Shared responsibility model divides into:

### Customer responsibilities (commonly referred to as `security in the cloud`) 

> You are responsible for managing security requirements for your content, including which content you choose to store on AWS, which AWS services you use, and who has access to that content. You also control how access rights are granted, managed, and revoked.

> Steps include selecting, configuring, and patching the operating systems that will run on Amazon EC2 instances, configuring security groups, and managing user accounts. 


### AWS responsibilities (commonly referred to as `security of the cloud`).

AWS manages the security of the cloud, specifically the physical infrastructure that hosts your resources, which include:

- Physical security of data centers
- Hardware and software infrastructure
- Network infrastructure
- Virtualization infrastructure


## User permissions and access

### AWS Identity and Access Management (IAM)

IAM users, groups, and roles
IAM policies
Multi-factor authentication

`Amazon account root user` --> by default has access to everything

Best practice:

- Do not use the root user for everyday tasks. 

- Instead, use the root user to create your first IAM user and assign it permissions to create other users.

- Then, continue to create other IAM users, and access those identities for performing regular tasks throughout AWS. 
- Only use the root user when you need to perform a limited number of tasks that are only available to the root user. 
- Examples of these tasks include changing your root user email address and changing your AWS support plan.

`IAM users` --> by default has no permission

- consists of a name and credential
- must grant the IAM user the necessary permissions.


Best practice:

- create individual IAM users for each person who needs to access AWS.
- provides additional security by allowing each IAM user to have a unique set of security credentials.  

`IAM policies` --> customize users' level of access

- a document that allows or denies permissions to AWS services and resources.  
- must grant the IAM user the necessary permissions.


Best practice:

- Follow the security principle of LEAST privilege when granting permissions. 
- prevent users or roles from having more permissions than needed to perform their tasks. 


`IAM groups` --> give all users in the group permission

-  a collection of IAM users. 
- must grant the IAM user the necessary permissions.


`IAM roles` --> temporary access to permission

-  a collection of IAM users. 
- must grant the IAM user the necessary permissions.


Best practice:

-  ideal for situations in which access to services or resources needs to be granted temporarily, instead of long-term.  


`Multi-factor authentication` --> extra layer of security


## AWS Organizations

In AWS Organizations, you can centrally control permissions for the accounts in your organization by using service control policies (SCPs). SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.


### Organizational units (OU)

- manage accounts with similar business or security requirements. 
- When you apply a policy to an OU, all the accounts in the OU automatically inherit the permissions specified in the policy.  

You are configuring service control policies (SCPs) in AWS Organizations. Which identities and resources can SCPs be applied to? 
- An individual member account
- An organizational unit (OU)


## Compliance

- a scalable file system used with AWS Cloud services and on-premises resources.  
- As you add or remove files, EFS grows and shrinks automatically. It can scale on demand to petabytes without disrupting applications

#### `AWS Artifact`

a service that provides on-demand access to AWS security and compliance reports and select online agreements. 
AWS Artifact consists of two main sections: 

1) AWS Artifact Agreements

2) AWS Artifact Reports.
- provide compliance reports from third-party auditors. 

#### Customer Compliance Center

contains resources to help you learn more about AWS compliance & includes an auditor learning path.

You can also access compliance whitepapers and documentation on topics such as:

AWS answers to key compliance questions
An overview of AWS risk and compliance
An auditing security checklist

## `Denial-of-service attacks`

`(DoS) attack` is a deliberate attempt to make a website or application unavailable to users.
 
 
### `DDOS` Distrituted denial-of-service
- an attack on your enterprise's infrastructure, 
- objective of a DDoS attack is to shut down your application's ability to function by overwhelming the system to the point it can no longer operate. 
- the distributed part is that the attack leverages other machines around the internet to unknowingly attack your infrastructure

`Slowloris attack` pretends to have a terribly slow connection. can exhaust the capacity of your entire front end with almost no effort at all.

Solution:
- low level network attacks like the UDP floods -> security group
- `Slowloris attack` ->elastic load balancer 
- sharpest, most sophisticated attacks -> AWS Shield with AWS WAF (WAF uses a web application firewall to filter incoming traffic for the signatures of bad actors)

### `AWS Shield`
a service that protects applications against DDoS attacks. 

AWS Shield provides two levels of protection: 
- Standard: automatically protects all AWS customers at no cost.
- Advanced: 
   - paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks. 
   - It also integrates with other services such as Amazon CloudFront, Amazon Route 53, and Elastic Load Balancing. Additionally, you can integrate AWS Shield with AWS WAF by writing custom rules to mitigate complex DDoS attacks.


## Additional security services

encryption: securing a message or data in a way that can only be accessed by authorized parties. 

#### Encryption at rest
By at rest, we mean when your data is idle. It's just being stored and not moving.
For example, server-side encryption at rest is enabled on all DynamoDB table data. And that helps prevent unauthorized access. DynamoDB's encryption at rest also integrates with AWS KMS, or Key Management Service, for managing the encryption key that is used to encrypt your tables. 

#### Encryption in transit
in-transit means that the data is traveling between A and B, where A is the AWS service, and B could be a client accessing the service or another AWS service. 

### `AWS Key Management Service (AWS KMS)`

- enables you to perform encryption operations through the use of cryptographic keys. 
- A cryptographic key is a random string of digits used for locking (encrypting) and unlocking (decrypting) data.
- You can use AWS KMS to create, manage, and use cryptographic keys. You can also control the use of keys across a wide range of services and in your applications.


### `AWS WAF` web application firewall
- web application firewall that lets you monitor network requests that come into your web applications. 
- works together with Amazon CloudFront and an Application Load Balancer.
- by using a web access control list (ACL) to protect your AWS resources. 
- e.g.  if a request came from one of the blocked IP addresses that you have specified in the web ACL, it is denied access.

### `Amazon Inspector`

- improve the security and compliance of applications by running automated security assessments.
- provides you with a list of security findings. The list prioritizes by severity level, including a detailed description of each security issue and a recommendation for how to fix it.
- However, AWS does not guarantee that following the provided recommendations resolves every potential security issue. Under the shared responsibility model, customers are responsible for the security of their applications, processes, and tools that run on AWS services. 


### `Amazon GuardDuty`

- a service that provides intelligent threat detection for your AWS infrastructure and resources. 
- It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment.


## Additional Resources

- [Security, Identity, and Compliance on AWS](https://aws.amazon.com/products/security)
- [Whitepaper: Introduction to AWS Security](https://docs.aws.amazon.com/whitepapers/latest/introduction-aws-security/welcome.html)
- [Whitepaper: Amazon Web Services - Overview of Security Processes](https://aws.amazon.com/blogs/security/)
- [AWS Compliance](https://aws.amazon.com/compliance)
- [AWS Customer Stories: Security, Identity, and Compliance](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23security-identity-compliance)
