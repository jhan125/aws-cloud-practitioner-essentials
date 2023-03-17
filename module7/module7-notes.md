# Module 7 - Monitoring and Analytics

## Learning Objectives

- Summarize approaches to monitoring your AWS environment.
- Describe the benefits of Amazon CloudWatch.
- Describe the benefits of AWS CloudTrail.
- Describe the benefits of AWS Trusted Advisor.

## `Amazon CloudWatch`

a web service that enables you to monitor and manage various metrics and configure alarm actions based on data from those metrics.

### CloudWatch alarms

With CloudWatch, you can create alarms that automatically perform actions if the value of your metric has gone above or below a predefined threshold. 
- access all your metrics from a central location
- gain visibility into applications, infrastructures, services
- redume MTTR and improve TCO (free up important resources)
- drive insights to optimize applications operational resources

For example, you can use a ***CloudWatch dashboard*** to monitor the CPU utilization of an Amazon EC2 instance, the total number of requests made to an Amazon S3 bucket, and more. You can even customize separate dashboards for different business purposes, applications, or resources.

## `Amazon CloudTrail`
Track user activities and API requests throughout your AWS infrastructure. 
Filter logs to assist with operational analysis and troubleshooting

Events are typically updated in CloudTrail within 15 minutes after an API call.
with tamper-proof methods like Vault Lock, you then can show absolute provenance of all of these critical security audit logs.

The recorded information includes 
- the identity of the API caller, 
- the time of the API call, 
- the source IP address of the API caller, and more. 

You can think of CloudTrail as a “trail” of breadcrumbs (or a log of actions) that someone has left behind them.

optional feature **CloudTrail Insights** allows CloudTrail to automatically detect unusual API activities in your AWS account. 

## Amazon Trusted Advisor

a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices.

compares its findings to AWS best practices in five categories: 
- cost optimization, 
- performance, 
- security, 
- fault tolerance
- service limits. 

For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices. 

For each category:

- The green check indicates the number of items for which it detected **no problems**.
- The orange triangle represents the number of recommended **investigations**.
- The red circle represents the number of recommended **actions**.


## Additional Resources

- [Management and Governance on AWS](https://aws.amazon.com/products/management-tools)
- [Monitoring and Observability](https://aws.amazon.com/products/management-tools/use-cases/monitoring-and-observability/)
- [Configuration, Compliance, and Auditing](https://aws.amazon.com/products/management-tools/use-cases/configuration-compliance-and-auditing/)
