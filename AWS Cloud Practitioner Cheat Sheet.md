The AWS Certified Cloud Practitioner validates foundational, high-level understanding of AWS Cloud, services, and terminology. This is a good starting point on the AWS Certification journey for individuals with no prior IT or cloud experience switching to a cloud career or for line-of-business employees looking for foundational cloud literacy.

<a href="https://aws.amazon.com/certification/certified-cloud-practitioner/ ">AWS Cloud Practitioner<a/>

# Domains
 - 34% Core AWS services
 - 30% Security and compliance in the AWS Cloud
 - 24% AWS Cloud concepts
 - 12% Economics of AWS Cloud

## Introduction to Cloud Computing
* **Infrastructure as a Service (IaaS)** - Provides access to networking features, computers (virtual or on dedicated hardware), and data storage space.
* **Platform as a Service (PaaS)** - Provides supporting infrastructure, usually hardware and operating systems, to allow users to focus on deploying and managing applications.
* **Software as a Service** - The service provider runs and manages a completed product for end users.
* **Public Cloud** - Fully deploys all parts of an application in the cloud, e.g., AWS, Microsoft Azure, and Google Cloud Platform. (GCP).
* **Hybrid** - Connects infrastructure and applications using cloud-based and local resources.
* **Private Cloud/On-Premises** - Dedicates resources for specific deployment aims through virtualization and resource management tools.
* **AWS Availability Zone AZ)** - Consists of one or more discrete data centers, each with redundant power, networking, and connectivity, housed in separate facilities.
* **AWS Region** - A physical location in the world where AWS hosts multiple AZs.

## Identity and Access Management (IAM)
* Root User - A single sign-in identity with complete access to every AWS service and resource in an AWS account.
* IAM User - Individuals granted access to an AWS account. Each IAM user has three components:
  * A username
  * A password
  * Access permissions to various resources. (Default: none)
* Group - A collection of users with policies attached to it.
* Role - A created identity assumed by trusted entities defines a set of permissions for making AWS service requests.
* Policy - A JSON document defining permissions that apply to users, groups, and roles. (Default: implicit deny).
* AWS Security Token Service (AWS STS) - A web service that enables you to request temporary, limited-privilege credentials for IAM users or for external users that you authenticate.

## Virtual Private Clouds
AWS Virtual Private Clouds are logically isolated virtual networks hosted on AWS cloud servers. 

* Subnet - A segment of a VPC's IP address range where you can place groups of isolated resources (maps to an AZ, 1:1).
* Internet Gateway - The Amazon VPC side of a connection to the public Internet.
* NAT Gateway - A highly available, managed Network Address Translation (NAT) service for your resources in a private subnet to access the Internet.
* Virtual Private Gateway - The Amazon VPC side of a VPN connection.
* Customer Gateway - Your side of a VPN connection.
* Router - Routers interconnect subnets and direct traffic between Internet gateways, virtual private gateways, NAT gateways, and subnets.
* Peering Connection - A peering connection enables you to route traffic between two peered VPCs via private IP addresses.
* VPC Endpoint - Enables private connectivity to services hosted in AWS from within your VPC without using an Internet Gateway, VPN, Network Address Translation (NAT) devices, or firewall proxies.
* Egress-Only Internet Gateway - A stateful gateway to provide egress-only access for IPv6 traffic from the VPC to the Internet.

## Elastic Compute Cloud (EC2)
AWS EC2 is a web service that resizes with computational load in the cloud. Launch virtual servers on the AWS cloud called "instances".

* Amazon Machine Images (AMIs) - Preconfigured templates for instances. Each AMI includes the information needed to launch your EC2 instance, such as the operating system and included software packages.
* EC2 Compute Units (ECUs) - Provide the relative measure of the integer processing power of an Amazon EC2 instance.
* Public IP Address
    * Lost when the instance terminates
    * Used in Public Subnets
    * No charge
    * Associated with a private IP address on the instance
    * You can't move them between instances
* Private IP Address - Retained when the instance terminates. Used in Public and Private Subnets
* Elastic IP Address
  * Static Public IP address
  * If unused, you must pay
  * Associated with a private IP address on the instance
  * You can move them between instances and Elastic Network Adapters.
* Elastic Network Interface - A logical networking component in a VPC that represents a virtual network card.
* Elastic Network Adapter (ENA) - Enhances networking capabilities such as bandwidth, packet-per-second (PPS) performance, and inter-instance latencies.

## Amazon Storage
AWS contains many cloud storage services, including S3, EBS, EFS, FSx, and Storage Gateway.

* Persistent Data Store - Data is durable and sticks around after restarts or power cycles. (Examples: S3, Glacier, EBS, EFS)
* Transient Data Store - Temporarily stored data gets passed along to another process or persistent store. (Examples: SQS, SNS)
* Ephemeral Data Store - System stoping causes data loss. (Examples: EC2 Instance Store, Memcached [Elasticache])
* Bucket
  * Contains files (objects)
  * Does not provide a hierarchy of objects
  * Can use an object key name (prefix) to mimic folders
* Object - A unique key (ID or name) helps one store and retrieve objects in a bucket
* Sub-Resources - Data subordinated to objects and buckets. Including:
  * Lifecycle
  * Website configuration for hosting static websites
  * Versioning
  * Access Control Lists (ACLs) to control permissions access to the bucket/object
  * Bucket Policies
  * Cross-Origin Resource Sharing (CORS)
  * Logging
  * Restoring an archive of objects
* Cross-Origin Resource Sharing (CORS) - (Applies to S3 buckets) Used to allow requests

## Fault Tolerance and Elasticity
<image src="https://www.stationx.net/wp-content/uploads/2024/01/high-availability-and-fault-tolrence.png" />

* Auto Scaling - Automates launches (scaling out) and terminating (scaling in) EC2 instances based on the traffic demand for your application.
* Auto Scaling Group (ASG) - Collections of EC2 instances defining their Auto Scaling capacity.
* Elastic Load Balancing (ELB) Automatically distributes incoming application traffic across multiple targets, such as EC2 instances, containers, and IP addresses.
* Application Load Balancer (ALB) - Operates at OSI Layer 7, for load balancing of HTTP and HTTPS traffic. Provides advanced request routing targeted at delivering modern application architectures, including micro-services and containers.
* Network Load Balancer (NLB) - Operates at OSI Layer 4, for load balncing of extreme TCP traffic.

## DNS and Content Delivery Networks
<image src="https://www.stationx.net/wp-content/uploads/2024/01/amazon-cloudfront.png" />

* Route 53 - AWS Domain Name Service. It performs three main functions:
  * Domain registration
  * Domain Name Service (DNS)
  * Health checking: Route 53 sends automated requests to your application to verify that it's reachable, available, and functional.
* CloudFront - A content delivery network (CDN) that allows you to store (cache) your content at edge locations located around the world. It has built-in Distributed Denial of Service (DDoS) attack protection.
* Edge Location - The location where AWS caches content but is seperate from AWS Regions or Availability Zones.
* Regional Edge Cache - A large cache server between origin web servers and global edge locations that bring content closer to users.

## Moitoring, Auditing, and Alerts
AWS provides several tools to monitor running services and alert you when they fail: Amazon CloudWatch, AWS CloudTrail, Amazon Simple Notification Service (SNS), and Amazon Config.

* Amazon CloudWatch - For performance monitoring, it collects and tracks metrics, creates log files, and sets alarms.
* AWS CloudTrail - For auditing, it records activity made on your account and delivers log files to an Amazon S3 bucket.
* Amazon Simple Notification Service (SNS) - For sending messages to different devices and platforms.
* Amazon Config - A tool for assessing, auditing, and evaluating the configurations and relationships of your resources.

## Databases
* Database on EC2 - Full control over instance and database. Preferred DB not available under RDS
* RDS
  * Need a traditional relational database for online transaction processing (OLTP)
  * Your data is well-formed and structured
  * Existing applications requiring RDBMS
* DynamoDB
  * Name/value pair data
  * Unpreditable data structure
  * In-memory performance with perisistence
  * High I/O needs
  * Require dynamic scaling
* RedShift - Data warehouse for large volumes of aggregated data. Primarily, online analytical processing (OLAP) workloads
* Neptune - Relationships between objects are of high-value
* ElastiCache - Fast temporary storage for small amounts of data. Highly volatile data (non-persistent)
* S3 - Binary large objects (BLOBs). Static websites

## Serverless Computing
Focuses on the AWS Lambda service

* Lambda - You run code on this platform as functions without provisioning or managing servers.
* Synchronous Invocation - You wait for the Lambda function to process the event and return a response.
* Asynchronous Invocaion - Lambda places the event in a queue and returns a "success" response without additional information.
* Event Source - An AWS service or developer-created application that produces events that trigger an AWS Lambda function to run.
* Versioning - Having multiple versions of your function.
* Aliases - Pointers to a specific Lambda version.

## Security and Compliance
*  Shared Responsibility Model - Name of the shared responsibility between AWS and the customer in security and compliance.
*  Security of the Cloud - AWS is responsible for protecting the infrastructure that runs all the services offered in the AWS Cloud.
*  Security in the Cloud - The AWS Cloud services you choose determines the amount of configuration work you must perform as part of your security responsibilties.
*  Key Management Service (KMS) - For easy data encryption, to centrally manage and securely store your keys.
*  KMS Key
  * Alias
  * Creation date
  * Description
  * Key state
  * Key material (either provided by you or AWS)
* AWS-Managed KMS keys - Used by AWS services that interact with KMS to encrypt data.
* Customer-Managed KMS Keys - You have full control over these KMS keys.

## AWS Pricing, Billing, and Support Services
* Organizations - Consolidation of multiple AWS accounts into an organization for central management
* Pricing Model
  * On-demand
  * Dedicated hosts
  * Dedicated instances
* Pricing Calculator - Gets cost estimates
