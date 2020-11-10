
https://www.youtube.com/watch?v=9IyMDLPTmlI

Memcached
cdn


============= Amazon RDS =================
Setup operate and scale a relational database

=> AWS RDS vs Aurora
https://medium.com/@crishantha/aws-aurora-why-is-it-better-6faae33a0ed0


===== Bastion host ===========
  to connect private n/w in private subnets
  no need of vpn

We have bastion hosting through external ip address to our app in vpc
Bastion host instance has external as well as internal ip address but instances in vpc has only internal ip address
Two-step ssh connection
Here bastion host is a public instance whereas app is a private instance
instead of storing the target machine's private key on the bastion host, we must use the ssh-agent forwarding even if you are using the same key-pair for both bastion and target instances.


=========== AWS EBS ================
 high performance, low latency block storage that works with AWS ec2

  ###  SSD Volume types, 
    low latency, 
    for boot volumes and transactional workloads like  enterprise applications
    and Relational and nosql databases
  ###  HDD ……, 
    high throughput
    for apps producing streaming i/o
    For Big Data App, Data warehousing app, Log processing app, Staging level     app before snapshot to AWS S3


======== AWS opswork ====================
A way to manage operations via chef scripts
automate deploy and update your app, package installation, software configuration such as storage, db and load balancers, automate scaling.
Model app as stack consisting of various layers.
Chef recipes to configure layers.
pulls code from repo and put it in layers
Protects app from failure and downtime
Helps take your app to user faster
No extra charges


======= AWS kinesis ===========
Easily collect, process, and analyze video and data streams in real time (Similar to Kafka)

========= AWS SES ===============
SES(simple emails service) is a cost-effective, flexible, and scalable email service that enables developers to send mail from within any application. 
You can configure Amazon SES quickly to support several email use cases, including transactional, marketing, or mass email communications. 

======== AWS Lambda ==========
Serverless computing service
Runs backend code in response to events such as uploads to S3 buckets, updates to dynamoDB table, in app-activity, data in amazon kinesis
handles capacity, Scaling, Patching and administration.

Steps - 
  Load function
  Select event source such as S3 or dynamoDB
  Makes use of HTTP gateway service like API gateway


Use cases -
Scalable APIs  : Different parts of the API can be routed to different Lambda functions via Amazon API Gateway. 
Data processing
task automation

Each Lambda function runs in its own container. When a function is created, Lambda packages it into a new container and then executes that container
on a multi-tenant cluster of machines managed by AWS. Before the functions start running, each function’s container is allocated its necessary RAM
and CPU capacity. Once the functions finish running, the RAM allocated at the beginning is multiplied by the amount of time the function spent 
running. The customers then get charged based on the allocated memory and the amount of run time the function took to complete.


_________________________________________

EBS - traditional disk storage

EC2 - a server VM that can use EBS volumes for its disks.. you can install a DB on this and administer it completely yourself.

RDS - AWS will spin up the required EC2 instances and attach EBS volumes etc and do most of the low level DB management for you
Hands-off RDBMS, Manually Scalable
Automated backups, Real-time snapshots

_________________________________________

==== S3 ===
Object Storage, Great for Static Assets
no limit on the No. of objects, cheapest option

===== Dynamodb =====
Deals awesome with 3V's of big data
hands-off and very simple to scale
“Column family” key-value store


- Store images, CSS, Javascript, HTML in s3
- Store orders, customers, “ad hoc” & reporting type data in RDS
- Pull “hot” tables (site likes, social interactions) out into DynamoDB
  Use a unique key like “user-id” for the primary key in Dynamo


============ AWS cloudtrail ============= 
logs collection

=========== AWS CloudWatch ==============
Provides monitoring for AWS cloud resources and applications, starting with EC2.

==========  AWS CloudFormation ===========
Provides a file-based interface for provisioning other resources.

========== AWS CloudFront ===============
A content delivery network (CDN) for distributing objects to locations near the requester.

========= Amazon CloudSearch ============
Amazon CloudSearch is a managed service in the AWS Cloud that makes it simple and cost-effective to set up, manage, and scale a search solution for your website or application.


========= Amazon Elastic Beanstalk =============
Elastic Beanstalk is one layer of abstraction away from the EC2 layer. Elastic Beanstalk will setup an "environment" for you that can contain a number of EC2 instances, an optional database,
as well as a few other AWS components such as a Elastic Load Balancer, Auto-Scaling Group, Security Group. Then Elastic Beanstalk will manage these items for you whenever you want to update your software running in AWS.
Used as Single Container Docker.

========= Amazon ECS =============
ECS, a fully-managed container orchestration service


========== AWS Elastic Block Store (EBS) =========
Provides persistent block-level storage volumes for EC2.

========== AWS Elastic File System (EFS) =========
A file storage service for EC2 instances.

========== AWS IAM(Identity and Access Management) ===================
An implicit service, the authentication infrastructure used to authenticate access to the various services.

========== AWS Certificate Manager =====================
Lets you easily provision, manage, and deploy SSL/TLS certificates for use with AWS services.


========= AWS Virtual Private Cloud (VPC) ===========
lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. 
You have complete control over your virtual networking environment, including selection of your own IP address range, creation of subnets, and configuration of route tables and network gateways. You can use both IPv4 and IPv6 in your VPC for secure and easy access to resources and applications.


============ AWS Route 53 ==============
Amazon Route 53 is a highly available and scalable cloud Domain Name System (DNS) web service. 
Amazon Route 53 effectively connects user requests to infrastructure running in AWS – such as Amazon EC2 instances, Elastic Load Balancing load balancers, or Amazon S3 buckets – and can also be used to route users to infrastructure outside of AWS. 


EC2 instance types - 
>>>> On Demand - Pay for compute capacity by hour or second without long term commitments. Predictable pricing
                 For shorter workload. 
                 No upfront payment but comparatively costly
                 To handle workload spikes


>>>>> Reserved - discount upto 75% on on demand instance. Flexibility to change OS.
            Upfront payment. For long term workload.
            To handle workload spikes. sell it to reserve instance market if we don't need it anymore
 

>>>>> Spot - Let you take advantage of unused EC2 capacity in AWS cloud. Upto 90% discount on on-demand. We need to bid for it. 
             Can lose your instance if someone bids more.
             Spot Instances run until you stop or terminate them, or until Amazon EC2 must interrupt them if someone bids for higher price.

Dedicated host - physical server. Save money on licensing costs

dedicated instance - instances that run in a VPC on hardware dedicated to single customer.


=========== AWS EMR ==========
  is a managed Hadoop framework for processing massive amounts of data across the EC2 instances. 


