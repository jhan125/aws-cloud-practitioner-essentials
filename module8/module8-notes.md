# Module 8 - Pricing and Support

## Learning Objectives

- Describe AWS pricing and support models.
- Describe the AWS Free Tier.
- Describe key benefits of AWS Organizations and consolidated billing.
- Explain the benefits of AWS Budgets.
- Explain the benefits of AWS Cost Explorer.
- Explain the primary benefits of the AWS Pricing Calculator.
- Distinguish between the various AWS Support Plans.
- Describe the benefits of AWS Marketplace.

## AWS Free Tier

3 types of offers are available: 

Always Free
e.g. `AWS Lambda` allows 1 million free requests and up to 3.2 million seconds of compute time per month. 
`Amazon DynamoDB` allows 25 GB of free storage per month.
`Amazon SageMaker`, `Amazon Comprehend Medical`, `Amazon SNS`, `Amazon Cognito`...

12 Months Free
e.g. `Amazon S3` is free for 12 months for up to 5GB of standard storage. 

Trials
e.g. `AWS Lightsail` offers 1 month trial of up to 750 hours of usage.
`Amazon Inspector` offers a 90-day free trial. 

### AWS Pricing Concepts

- pay for what you use
- pay less when you reserve (e.g. EC2 instance savings plan -> up to 72%)
- pay less with volume-basesd discounts when you use more (more S3 storage use, less to pay)

***`Pricing Calculator`*** 

`AWS Lambda`
- charged based on the number of requests for your functions and the time that it takes for them to run.
- allows 1 million free requests and up to 3.2 million seconds of compute time per month.
- **Compute Savings Plan** offers lower compute costs in exchange for committing to a consistent amount of usage over a 1-year or 3-year term (PAY LESS WHEN YOU RESERVE)


`Amazon EC2`
- pay for only the compute time that you use while your instances are running.
- if running a batch processing job that is able to withstand interruptions, using a **Spot Instance** would provide you with up to 90% cost savings


`Amazon S3`
cost components:
- **Storage** You pay for only the storage that you use. You are charged the rate to store objects in your Amazon S3 buckets based on your objects’ sizes, storage classes, and how long you have stored each object during the month.
- **Requests and data retrievals** You pay for requests made to your Amazon S3 objects and buckets. For example, suppose that you are storing photo files in Amazon S3 buckets and hosting them on a website. Every time a visitor requests the website that includes these photo files, this counts towards requests you must pay for.
- **Data transfe** There is no cost to transfer data between different Amazon S3 buckets or from Amazon S3 to other services within the same AWS Region. However, you pay for data that you transfer into and out of Amazon S3, with a few exceptions. There is no cost for data transferred into Amazon S3 from the internet or out to Amazon CloudFront. There is also no cost for data transferred out to an Amazon EC2 instance in the same AWS Region as the Amazon S3 bucket.
- **Management and replication** You pay for the storage management features that you have enabled on your account’s Amazon S3 buckets. These features include Amazon S3 inventory, analytics, and object tagging.

### `Billing dashboard`

- Compare your current month-to-date balance with the previous month, and get a forecast of the next month based on current usage.
- View month-to-date spend by service.
- View Free Tier usage by service.
- Access Cost Explorer and create budgets.
- Purchase and manage Savings Plans.
- Publish [AWS Cost and Usage Reports](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html).

### `Consolidate billing`

`AWS Organizations` also provides the option for `consolidated billing` (a single bill for all AWS accounts in your organization.)
`AWS Organizations` is a service that enables you to manage multiple AWS accounts from a central location

>  The default maximum number of accounts allowed for an organization is `4`, but you can contact AWS Support to increase your quota, if needed.

Benefits:
- ave greater transparency into your organization’s accounts while still maintaining the convenience of receiving a single monthly bill.
- share bulk discount pricing, Savings Plans, and Reserved Instances across the accounts in your organization. 

### `AWS Budgets`

The information in AWS Budgets updates three times a day. This helps you to accurately determine how close your usage is to your budgeted amounts or to the AWS Free Tier limits.

- create budgets to plan your service usage, service costs, and instance reservations.
- set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.

### `AWS Cost Explorer`

a tool that enables you to visualize, understand, and manage your AWS costs and usage over time.

- includes a default report of the costs and usage for your top five cost-accruing AWS services. 
- You can apply custom filters and groups to analyze your data. For example, you can view resource usage at the hourly level.

## AWS Support plans

**Basic support** -> free tier for all
- 24/7 customer service
- documentation
- whitepapers
- support forums
- AWS Trusted Advisor
- AWS personal health dashboard

**Developer support** -> lower cost tier
- basic support
- email access to customer support

**Business support** -> higher cost tier
- basic support & developer support
- AWS Trusted Advisor provides full set of best practice checks
- direct phone access to cloud support engineers (4-hour response SLA)
- infrastructure event management

**Enterprise support** -> highest cost tier
- basic & developer & business support
- 15-min SLA for business critical workloads
- Technical Account Manager (TAM) work with design solutions, architecture

***5 pillars of well-architectured framework***
- Operational Excellence
- Security
- Reliability
- Performance Efficiency
- Cost Optimization

> Only the Business, Enterprise On-Ramp, and Enterprise Support plans include `all AWS Trusted Advisor checks`. Of these three Support plans, the Business Support plan has a lower cost.


### AWS Marketplace

a digital catalog that includes thousands of software listings from independent software vendors. 

- access detailed information on pricing options, available support, and reviews from other AWS customers.
- explore software solutions by industry and use case. 

offers products in several categories, such as 
- Infrastructure Software
- DevOps (App development, monitoring, testing)
- Data Products
- Professional Services
- Business Applications
- Machine Learning
- Industries
- Internet of Things (IoT)


## Summary
- Three types of offers included in the AWS Free Tier: 12 months free, Always free, and Trials
- Benefits of consolidated billing in AWS Organizations
- Tools for planning, estimating, and reviewing AWS costs
- Differences between the five AWS Support plans: Basic, Developer, Business, Enterprise On-Ramp, and Enterprise
- How to discover software in AWS Marketplace
