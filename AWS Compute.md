# AWS Compute

- Amazon EC2
- AWS Lambda
- AWS Elastic Beanstalk

### Amazon EC2 (Elastic Compute Cloud)

| **Column Name**          | **Description**                                                                 |
|--------------------------|---------------------------------------------------------------------------------|
| **Service Name**          | Amazon EC2 (Elastic Compute Cloud)                                              |
| **Category**              | Compute                                                                        |
| **Description**           | Scalable virtual server instances in the cloud.                                |
| **Key Features**          | Broad instance types, Auto Scaling, Elastic IPs, AMIs (Amazon Machine Images), placement groups, dedicated hosts. |
| **Use Cases**             | Web applications, batch processing, dev/test environments, machine learning workloads, databases. |
| **Types**                 | On-Demand Instances, Reserved Instances, Spot Instances, Dedicated Hosts      |
| **Pricing Model**         | Pay-as-you-go, Reserved Instances, Spot Instances, Savings Plans.               |
| **Scalability**           | Auto Scaling for dynamic workloads, can scale vertically by choosing larger instance types. |
| **Integration**           | EBS, S3, RDS, Lambda, CloudWatch, VPC, Elastic Load Balancer, and many more AWS services. |
| **Security Features**     | IAM, VPC, Security Groups, encryption at rest and in-transit, key pair authentication, dedicated hosts. |
| **Region Availability**   | Available in all AWS regions.                                                   |
| **Components**            | Instances, AMIs (Amazon Machine Images), EBS (Elastic Block Store), Security Groups, Key Pairs, Elastic IPs, Load Balancers, Auto Scaling groups, Instance Types. |
| **Management Tools**      | AWS Management Console, SDKs, CLI, Systems Manager, EC2 Instance Connect.       |
| **Performance Metrics**   | CPU utilization, disk I/O, network throughput, instance status checks.          |
| **Service Limits**        | Limits on the number of instances per region (can be increased upon request), max EBS volume size of 64TiB. |
| **Data Transfer Costs**   | Free data transfer within the same region, charges apply for cross-region and internet-bound transfers. |
| **Compliance**            | HIPAA, PCI-DSS, SOC compliance, FedRAMP.                                        |
| **Limitations**           | Limited to instance types available in the region, requires management of instance lifecycle (launch, stop, terminate). |
| **Related Services**      | Amazon EBS, Elastic Load Balancing, Amazon RDS, AWS Auto Scaling, AWS Lambda.   |
| **Getting Started**       | [Amazon EC2 Getting Started](https://aws.amazon.com/ec2/getting-started/)       |
| **Example**               | Running a scalable web server, hosting a database, or performing real-time data processing. |

---
---

### Explanation of EC2 Types and Components:

#### Types of EC2 Instances:

- On-Demand Instances: Pay for compute capacity by the hour or second, with no long-term commitments. Ideal for unpredictable workloads.
- Reserved Instances: Reserve instances for a one- or three-year term, offering significant savings compared to On-Demand pricing. Best for steady-state usage.
- Spot Instances: Purchase unused EC2 capacity at reduced prices, which can change based on supply and demand. Suitable for flexible and fault-tolerant workloads.
- Dedicated Hosts: Physical servers dedicated to your use, allowing you to use your existing server-bound software licenses. Useful for regulatory compliance.

#### Components of EC2:

- Instances: Virtual servers that run applications in the cloud, available in various sizes and types to meet different needs.
- AMIs (Amazon Machine Images): Pre-configured templates for instances that contain the operating system and application server.
- EBS (Elastic Block Store): Durable storage volumes that can be attached to EC2 instances for data storage.
- Security Groups: Virtual firewalls for controlling inbound and outbound traffic to instances.
- Key Pairs: Used for secure login information to access EC2 instances.
- Elastic IPs: Static public IP addresses that can be associated with instances for easy reallocation.
- Load Balancers: Distribute incoming traffic across multiple instances to ensure reliability and performance.
- Auto Scaling Groups: Automatically scale the number of EC2 instances based on demand, ensuring optimal resource allocation.

---

---
---

### AWS Lambda

| **Column Name**          | **Description**                                                                 |
|--------------------------|---------------------------------------------------------------------------------|
| **Service Name**          | AWS Lambda                                                                     |
| **Category**              | Compute/Serverless                                                             |
| **Description**           | Serverless compute service that lets you run code without provisioning or managing servers. |
| **Key Features**          | Event-driven execution, automatic scaling, support for multiple languages (Node.js, Python, Java, Go, etc.), pay-per-execution. |
| **Use Cases**             | Real-time file processing, event-driven applications, backend services for mobile/web apps, microservices, data transformation. |
| **Types**                 | Event-driven computing, Serverless functions                                   |
| **Pricing Model**         | Pay-as-you-go, based on the number of requests and execution time (charged per millisecond). |
| **Scalability**           | Automatically scales to handle the incoming request volume. No need to provision capacity. |
| **Integration**           | API Gateway, S3, DynamoDB, CloudWatch, Step Functions, SNS, SQS, RDS, Kinesis.  |
| **Security Features**     | IAM roles, VPC support, encryption (in-transit and at-rest), Lambda execution roles, resource-based policies. |
| **Region Availability**   | Available in most AWS regions.                                                  |
| **Components**            | Lambda Functions, Event Sources, Triggers, Layers (for shared code), Execution Role, VPC Configuration, AWS SDKs. |
| **Management Tools**      | AWS Management Console, SDKs, CLI, AWS CloudFormation, AWS SAM (Serverless Application Model). |
| **Performance Metrics**   | Invocation count, error rate, duration, throttles, and concurrent executions (monitored through CloudWatch). |
| **Service Limits**        | 15-minute max execution time, 10GB max memory allocation, 1,000 concurrent executions (soft limit). |
| **Data Transfer Costs**   | Charges for data transfer to other AWS services and the internet. Free for transfers within the same region. |
| **Compliance**            | HIPAA, PCI-DSS, SOC compliance, FedRAMP.                                        |
| **Limitations**           | Limited runtime duration (15 minutes max per invocation), limited control over the underlying environment. |
| **Related Services**      | Amazon API Gateway, Amazon S3, AWS Step Functions, Amazon CloudWatch, DynamoDB. |
| **Getting Started**       | [AWS Lambda Getting Started](https://aws.amazon.com/lambda/getting-started/)    |
| **Example**               | Running a function in response to an S3 file upload or processing real-time data streams from Kinesis. |

### Explanation of AWS Lambda Types and Components:
* **Types of AWS Lambda**:
  * **Event-driven Computing**: Lambda functions that are triggered by events from various AWS services, such as changes in data, HTTP requests, or system events.
  * **Serverless Functions**: Functions that run without the need for managing servers, automatically scaling to accommodate incoming requests.
* **Components of AWS Lambda**:
  * **Lambda Functions**: The core unit of execution, containing the code and configuration for the tasks to be performed.
  * **Event Sources**: AWS services that can trigger Lambda functions, such as S3 (for file uploads), DynamoDB (for database changes), or API Gateway (for HTTP requests).
  * **Triggers**: Configurations that specify which events invoke the Lambda function.
  * **Layers**: A way to manage common code or dependencies that can be shared across multiple Lambda functions.
  * **Execution Role**: An IAM role that grants permissions for the Lambda function to access AWS services and resources.
  * **VPC Configuration**: Allows Lambda functions to connect to resources in a Virtual Private Cloud (VPC) for enhanced security.

 ---



### AWS Elastic Beanstalk

| **Column Name**          | **Description**                                                                 |
|--------------------------|---------------------------------------------------------------------------------|
| **Service Name**          | AWS Elastic Beanstalk                                                           |
| **Category**              | Compute/Platform-as-a-Service (PaaS)                                            |
| **Description**           | Managed service for deploying and scaling web applications and services.        |
| **Key Features**          | Automatic scaling, monitoring, managed environment, support for multiple programming languages (Java, Python, PHP, Node.js, etc.). |
| **Use Cases**             | Web applications, APIs, microservices, backend processing.                      |
| **Pricing Model**         | Pay only for the AWS resources (EC2, S3, RDS, etc.) used by your application.    |
| **Scalability**           | Auto Scaling, Elastic Load Balancing, supports multiple availability zones.      |
| **Integration**           | EC2, RDS, S3, CloudWatch, CodePipeline, CodeDeploy, IAM.                        |
| **Security Features**     | IAM roles, VPC integration, Security Groups, encryption at-rest (for storage) and in-transit. |
| **Region Availability**   | Available in most AWS regions.                                                  |
| **Management Tools**      | AWS Management Console, SDKs, CLI, Elastic Beanstalk CLI, CloudFormation.        |
| **Performance Metrics**   | CPU utilization, memory usage, latency, request count (via CloudWatch).         |
| **Service Limits**        | Limited to supported platforms and instance types, limits on environment resources. |
| **Data Transfer Costs**   | Charges apply for outbound data transfers (e.g., to the internet).               |
| **Compliance**            | HIPAA, PCI-DSS, SOC compliance, FedRAMP.                                        |
| **Limitations**           | Platform-specific constraints, less control over the underlying infrastructure. |
| **Related Services**      | Amazon RDS, Amazon S3, AWS Lambda, AWS CloudFormation, Elastic Load Balancing.  |
| **Getting Started**       | [AWS Elastic Beanstalk Getting Started](https://aws.amazon.com/elasticbeanstalk/getting-started/) |
| **Example**               | Deploying a Node.js web application or scaling a Ruby on Rails API.             |

---

