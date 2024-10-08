# AWS Database Services Comparison

## Amazon RDS

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon RDS                                                   |
| **Category**                | Relational Database                                           |
| **Description**             | Managed relational database service supporting multiple engines.|
| **Key Features**            | Supports MySQL, PostgreSQL, Oracle, SQL Server, MariaDB. Automatic backups, multi-AZ deployment. |
| **Use Cases**               | OLTP, web and mobile apps, ERP systems.                       |
| **Pricing Model**           | Pay-as-you-go, reserved instances.                            |
| **Scalability**             | Vertical scaling by resizing instances.                       |
| **Integration**             | AWS Management Console, Lambda, EC2, CloudFormation.          |
| **Security Features**       | Encryption, IAM, VPC, security groups.                        |
| **Region Availability**     | Available in most AWS regions.                                |
| **Management Tools**        | AWS Management Console, CLI, CloudFormation.                 |
| **Performance Metrics**     | Latency, IOPS, connections.                                   |
| **Service Limits**          | Instance types, max storage size.                             |
| **Data Transfer Costs**     | Charges for cross-region and outbound transfers.              |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                     |
| **Limitations**             | Limited to RDS engine capabilities.                           |
| **Related Services**        | Amazon Aurora, DynamoDB, Redshift.                            |
| **Getting Started**         | [RDS Getting Started](https://aws.amazon.com/rds/getting-started/) |
| **Example**                 | Deploy a MySQL database with automatic backups.               |

---

## Amazon Aurora

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon Aurora                                                |
| **Category**                | Relational Database (MySQL/PostgreSQL compatible)             |
| **Description**             | High-performance, MySQL/PostgreSQL-compatible relational database.|
| **Key Features**            | Auto-scaling, highly available, compatible with MySQL and PostgreSQL. |
| **Use Cases**               | Enterprise applications, SaaS applications.                  |
| **Pricing Model**           | Pay-as-you-go, reserved instances.                            |
| **Scalability**             | Automatic horizontal scaling with Aurora Serverless.          |
| **Integration**             | AWS Lambda, CloudWatch, CloudFormation.                      |
| **Security Features**       | Encryption, IAM, VPC, SSL/TLS.                               |
| **Region Availability**     | Available in most AWS regions.                                |
| **Management Tools**        | AWS Management Console, CLI, CloudFormation.                 |
| **Performance Metrics**     | Low-latency reads and writes, IOPS.                           |
| **Service Limits**          | Max cluster size, instance limits.                            |
| **Data Transfer Costs**     | Charges for cross-region and outbound transfers.              |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                     |
| **Limitations**             | Limited to MySQL/PostgreSQL compatibility.                    |
| **Related Services**        | Amazon RDS, DynamoDB, Redshift.                               |
| **Getting Started**         | [Aurora Getting Started](https://aws.amazon.com/rds/aurora/getting-started/) |
| **Example**                 | Deploy a highly available PostgreSQL database.               |

---

## Amazon DynamoDB

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon DynamoDB                                              |
| **Category**                | NoSQL (Key-Value/Document)                                    |
| **Description**             | Fully managed, serverless NoSQL database for high-scale apps. |
| **Key Features**            | Key-value and document store, auto-scaling, global tables.    |
| **Use Cases**               | Web apps, gaming, IoT, mobile backends.                      |
| **Pricing Model**           | Pay-as-you-go based on read/write capacity.                   |
| **Scalability**             | Auto-scaling for throughput and storage.                      |
| **Integration**             | AWS Lambda, S3, CloudWatch, Kinesis.                         |
| **Security Features**       | Encryption, IAM, VPC, security groups, DDoS protection.       |
| **Region Availability**     | Available in all AWS regions.                                 |
| **Management Tools**        | DynamoDB console, CLI, CloudFormation.                       |
| **Performance Metrics**     | Latency, read/write capacity units, DynamoDB Accelerator (DAX).|
| **Service Limits**          | Max item size, partition key limits, read/write capacity.      |
| **Data Transfer Costs**     | Charges for cross-region and outbound transfers.              |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                     |
| **Limitations**             | No complex queries, indexing limited.                         |
| **Related Services**        | Amazon RDS, S3, Lambda, ElastiCache.                          |
| **Getting Started**         | [DynamoDB Getting Started](https://aws.amazon.com/dynamodb/getting-started/) |
| **Example**                 | Deploy a global key-value store for a gaming app.             |

---

## Amazon DocumentDB

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon DocumentDB                                            |
| **Category**                | NoSQL (Document)                                              |
| **Description**             | Managed NoSQL document database, MongoDB-compatible.          |
| **Key Features**            | MongoDB API compatibility, fully managed, scalable.          |
| **Use Cases**               | MongoDB applications, content management, catalogs.          |
| **Pricing Model**           | Pay-as-you-go, provisioned throughput.                        |
| **Scalability**             | Vertical scaling by resizing instances.                      |
| **Integration**             | AWS CloudWatch, Lambda, VPC.                                 |
| **Security Features**       | Encryption, IAM, VPC, SSL/TLS.                               |
| **Region Availability**     | Available in selected regions.                               |
| **Management Tools**        | AWS Management Console, CLI, CloudFormation.                 |
| **Performance Metrics**     | Latency, read/write throughput.                              |
| **Service Limits**          | Max document size, instance types.                           |
| **Data Transfer Costs**     | Charges for cross-region and outbound transfers.             |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                    |
| **Limitations**             | Limited to MongoDB API capabilities.                         |
| **Related Services**        | Amazon RDS, DynamoDB, Lambda.                                |
| **Getting Started**         | [DocumentDB Getting Started](https://aws.amazon.com/documentdb/getting-started/) |
| **Example**                 | Create a content management system using MongoDB.            |

---

## Amazon ElastiCache

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon ElastiCache                                            |
| **Category**                | In-Memory Cache/NoSQL                                         |
| **Description**             | Managed in-memory data store for caching or NoSQL data store. |
| **Key Features**            | Supports Redis and Memcached, low-latency caching.            |
| **Use Cases**               | Real-time applications, caching, gaming.                     |
| **Pricing Model**           | Pay-as-you-go, based on instance type and hours used.         |
| **Scalability**             | Horizontal scaling for reads and writes.                     |
| **Integration**             | AWS Lambda, CloudWatch, EC2.                                 |
| **Security Features**       | Encryption, VPC, security groups.                            |
| **Region Availability**     | Available in most AWS regions.                               |
| **Management Tools**        | AWS Management Console, CLI, CloudFormation.                 |
| **Performance Metrics**     | Latency, cache hits/misses, throughput.                      |
| **Service Limits**          | Max node size, data persistence limits.                      |
| **Data Transfer Costs**     | Charges for cross-region and outbound transfers.             |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                    |
| **Limitations**             | Limited memory storage, volatile data.                       |
| **Related Services**        | Amazon DynamoDB, Lambda, CloudWatch.                         |
| **Getting Started**         | [ElastiCache Getting Started](https://aws.amazon.com/elasticache/getting-started/) |
| **Example**                 | Cache frequently accessed data for a web application.        |

---

## Amazon MemoryDB

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon MemoryDB                                               |
| **Category**                | In-Memory Cache/Database                                      |
| **Description**             | Redis-compatible managed database for in-memory data storage. |
| **Key Features**            | Redis-compatible, durable in-memory storage.                 |
| **Use Cases**               | Real-time leaderboards, session management.                  |
| **Pricing Model**           | Pay-as-you-go, based on instance type and usage.             |
| **Scalability**             | Horizontal scaling with Redis clustering.                    |
| **Integration**             | AWS Lambda, CloudWatch, CloudFormation.                      |
| **Security Features**       | Encryption, IAM, VPC, Redis Auth.                            |
| **Region Availability**     | Available in most AWS regions.                               |
| **Management Tools**        | AWS Management Console, CLI, CloudFormation.                |
| **Performance Metrics**     | Latency, throughput, in-memory performance.                  |
| **Service Limits**          | Max cluster size, Redis persistence.                        |
| **Data Transfer Costs**     | Charges for cross-region and outbound transfers.            |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                    |
| **Limitations**             | Redis-specific limitations, primarily in-memory.             |
| **Related Services**        | Amazon ElastiCache, DynamoDB.                                |
| **Getting Started**         | [MemoryDB Getting Started](https://aws.amazon.com/memorydb/getting-started/) |
| **Example**                 | Manage a leaderboard with fast in-memory access.            |

---

## Amazon Redshift

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon Redshift                                             |
| **Category**                | Data Warehouse                                               |
| **Description**             | Fully managed, petabyte-scale data warehouse service.        |
| **Key Features**            | Columnar storage, SQL interface, data compression.           |
| **Use Cases**               | Business intelligence, analytics, reporting.                 |
| **Pricing Model**           | Pay-as-you-go, reserved instances.                            |
| **Scalability**             | Elastic resize, data distribution.                           |
| **Integration**             | AWS Glue, S3, EMR, QuickSight.                             |
| **Security Features**       | Encryption, IAM, VPC, auditing.                             |
| **Region Availability**     | Available in most AWS regions.                              |
| **Management Tools**        | AWS Management Console, CLI, CloudFormation.                |
| **Performance Metrics**     | Query performance, concurrency, IOPS.                       |
| **Service Limits**          | Cluster size limits, max number of nodes.                   |
| **Data Transfer Costs**     | Charges for data transfer out of Redshift.                  |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                   |
| **Limitations**             | Limited to data warehouse workloads.                         |
| **Related Services**        | Amazon S3, EMR, Redshift Spectrum.                          |
| **Getting Started**         | [Redshift Getting Started](https://aws.amazon.com/redshift/getting-started/) |
| **Example**                 | Analyze petabytes of data for business intelligence.        |

---

## Amazon Neptune

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon Neptune                                              |
| **Category**                | Graph Database                                              |
| **Description**             | Fully managed graph database service optimized for storing and querying graph data. |
| **Key Features**            | Supports both property graph and RDF models, built-in graph analytics. |
| **Use Cases**               | Social networking, recommendation engines, fraud detection. |
| **Pricing Model**           | Pay-as-you-go based on instance type and storage.          |
| **Scalability**             | Horizontally scalable across multiple instances.            |
| **Integration**             | AWS Lambda, S3, CloudFormation, IAM.                       |
| **Security Features**       | Encryption, IAM, VPC, fine-grained access control.         |
| **Region Availability**     | Available in most AWS regions.                             |
| **Management Tools**        | AWS Management Console, CLI, CloudFormation.               |
| **Performance Metrics**     | Query performance, latency, throughput.                    |
| **Service Limits**          | Max instance limits, storage limits.                       |
| **Data Transfer Costs**     | Charges for data transfer out of Neptune.                  |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                   |
| **Limitations**             | Limited to graph data use cases.                           |
| **Related Services**        | Amazon RDS, DynamoDB, S3.                                  |
| **Getting Started**         | [Neptune Getting Started](https://aws.amazon.com/neptune/getting-started/) |
| **Example**                 | Create a fraud detection system with graph queries.       |

---

## Amazon Timestream

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon Timestream                                           |
| **Category**                | Time Series Database                                        |
| **Description**             | Fully managed time series database for IoT and operational applications. |
| **Key Features**            | Automated scaling, time series-specific queries, data retention policies. |
| **Use Cases**               | IoT telemetry, operational metrics, monitoring.            |
| **Pricing Model**           | Pay-as-you-go based on data ingested and stored.           |
| **Scalability**             | Automatically scales to handle variable workloads.         |
| **Integration**             | AWS IoT Core, Lambda, S3, CloudWatch.                     |
| **Security Features**       | Encryption, IAM, VPC, data access control.                 |
| **Region Availability**     | Available in select AWS regions.                            |
| **Management Tools**        | AWS Management Console, CLI, SDKs.                        |
| **Performance Metrics**     | Query performance, data ingestion rate.                    |
| **Service Limits**          | Limits on retention, ingestion rates, and concurrent queries.|
| **Data Transfer Costs**     | Charges for data transfer out of Timestream.               |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                   |
| **Limitations**             | Limited to time series data use cases.                     |
| **Related Services**        | Amazon Kinesis, DynamoDB, S3.                             |
| **Getting Started**         | [Timestream Getting Started](https://aws.amazon.com/timestream/getting-started/) |
| **Example**                 | Store and analyze IoT sensor data.                         |

---

## Amazon QLDB

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon QLDB                                                |
| **Category**                | Ledger Database                                            |
| **Description**             | Fully managed ledger database with a transparent, immutable, cryptographically verifiable transaction log. |
| **Key Features**            | ACID transactions, built-in cryptographic verification, automatic scaling. |
| **Use Cases**               | Financial transactions, supply chain tracking, asset management. |
| **Pricing Model**           | Pay-as-you-go based on data written and stored.            |
| **Scalability**             | Automatically scales based on workload.                    |
| **Integration**             | AWS Lambda, Kinesis, CloudWatch.                           |
| **Security Features**       | Encryption, IAM, VPC, access control.                      |
| **Region Availability**     | Available in selected regions.                             |
| **Management Tools**        | AWS Management Console, CLI, SDKs.                        |
| **Performance Metrics**     | Transaction performance, latency.                          |
| **Service Limits**          | Limits on data size, transaction throughput.               |
| **Data Transfer Costs**     | Charges for data transfer out of QLDB.                    |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                  |
| **Limitations**             | Limited to ledger database use cases.                      |
| **Related Services**        | Amazon S3, DynamoDB, Kinesis.                             |
| **Getting Started**         | [QLDB Getting Started](https://aws.amazon.com/qldb/getting-started/) |
| **Example**                 | Create an immutable financial ledger for a trading system. |

---

## Amazon Keyspaces

| **Column Name**            | **Description**                                               |
|----------------------------|---------------------------------------------------------------|
| **Service Name**            | Amazon Keyspaces                                            |
| **Category**                | NoSQL (Wide-Column)                                         |
| **Description**             | Managed Cassandra-compatible database service.               |
| **Key Features**            | Scalability, high availability, Cassandra API compatibility. |
| **Use Cases**               | IoT applications, time-series data, user profiles.         |
| **Pricing Model**           | Pay-as-you-go based on read/write requests and storage.     |
| **Scalability**             | Automatic scaling based on workload.                        |
| **Integration**             | AWS Lambda, S3, Kinesis, CloudWatch.                       |
| **Security Features**       | Encryption, IAM, VPC, security groups.                      |
| **Region Availability**     | Available in most AWS regions.                              |
| **Management Tools**        | AWS Management Console, CLI, SDKs.                        |
| **Performance Metrics**     | Latency, read/write throughput, request metrics.            |
| **Service Limits**          | Limits on tables, partitions, and requests.                 |
| **Data Transfer Costs**     | Charges for data transfer out of Keyspaces.                 |
| **Compliance**              | HIPAA, GDPR, SOC 1, 2, 3.                                   |
| **Limitations**             | Limited to Cassandra-compatible queries.                    |
| **Related Services**        | Amazon DynamoDB, ElastiCache, Lambda.                      |
| **Getting Started**         | [Keyspaces Getting Started](https://aws.amazon.com/keyspaces/getting-started/) |
| **Example**                 | Migrate from Apache Cassandra to a managed service.         |


---
