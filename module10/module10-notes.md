# Module 9 - The Cloud Journey

## Learning Objectives

- Summarize the six pillars of the Well-Architected Framework.  
- Explain the six benefits of cloud computing.

## AWS Well-Architected Framework

can be implemented by a self-service tool, the Well-Architected Tool in the AWS Management Console. 

**Six Pillars**


***1) Operational excellence*** 

-> focus on running workloads effectively and gain insights into their operations

e.g automating changes with deployment pipelines, or responding to events that are triggered. 

the ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures.  

Design principles for operational excellence in the cloud include performing operations as code, annotating documentation, anticipating failure, and frequently making small, reversible changes.

***2) Security*** 

-> focus on protecting data, systems, and assets, and using cloud technologies to improve the security of your workloads.

e.g. checking integrity of data and, for example, protecting systems by using encryption. 

the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies. 

When considering the security of your architecture, apply these best practices:

- Automate security best practices when possible.
- Apply security at all layers.
- Protect data in transit and at rest.

***3) Reliability*** 

-> focuses on the ability of a workload to consistently and correctly perform its intended functions

the ability of a system to do the following:

- Recover from infrastructure or service disruptions
- Dynamically acquire computing resources to meet demand
- Mitigate disruptions such as misconfigurations or transient network issues

Reliability includes testing recovery procedures, scaling horizontally to increase aggregate system availability, and automatically recovering from failure.

***4) Performance efficiency*** 

-> focuses on using computing resources efficiently to meet system requirements

e.g. using the right Amazon EC2 type, based on workload and memory requirements


the ability to use computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve. 


Evaluating the performance efficiency of your architecture includes 
- experimenting more often
- using serverless architectures
- designing systems to be able to go global in minutes.


***5) Cost optimization*** 

the ability to run systems to deliver business value at the lowest price point. 

Cost optimization includes
- adopting a consumption model
- analyzing and attributing expenditure
- using managed services to reduce the cost of ownership.

***6) Sustainability*** 

the ability to continually improve sustainability impacts by reducing energy consumption and increasing efficiency across all components of a workload by maximizing the benefits from the provisioned resources and minimizing the total resources required.


To facilitate good design for sustainability:

- Understand your impact
- Establish sustainability goals
- Maximize utilization
- Anticipate and adopt new, more efficient hardware and software offerings
- Use managed services
- Reduce the downstream impact of your cloud workloads


## Benefits of AWS Cloud

On-premises data center costs:
- physical space
- hardware
- staff for racking and stacking
- overhead for running data center
- fixed cost


Save money with AWS
- turn off unused instances
- delete old resources
- optimize applications
- receive recommendations from AWS Trusted Advisor

### **6 Advantages**

1. **Trade upfront expense for variable expense.**

- **Upfront expenses** include data centers, physical servers, and other resources that you would need to invest in before using computing resources. 
- Instead of investing heavily in data centers and servers before you know how you’re going to use them, you can pay only when you consume computing resources.


2. **Benefit from massive economies of scale.**

- By using cloud computing, you can achieve a lower pay-as-you-go cost than you can get on your own. 
- Because usage from hundreds of thousands of customers aggregates in the cloud, providers such as AWS can achieve higher economies of scale. Economies of scale translate into lower pay-as-you-go prices.


3. **Stop guessing capacity.**

- don’t have to predict how much infrastructure capacity you will need before deploying an application. 


4. **Increase speed and agility.**

- makes it easier for you to develop and deploy applications.
- provides your development teams with more time to experiment and innovate.


5. **Stop spending money running and maintaining data centers.**


6. **Go global in minutes.**
- The AWS Cloud global footprint enables you to quickly deploy applications to customers around the world, while providing them with low latency.


## Additional Resouces

[AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)
