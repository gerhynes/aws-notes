# AWS Certified Cloud Developer Associate Notes
Sources
- [Ultimate AWS Certified Developer Associate 2023](https://www.udemy.com/course/aws-certified-developer-associate-dva-c01/)

AWS was launched internally in 2002. Their first public offering was SQS in 2004. In 2006 they re-launched, with SQS, S3 and EC2. In 2007 they expanded from offering services in the US to Europe.

AWS's annual revenue reached $80 billion in 2022, its market share is 34%, and has over 1 million active users.

AWS allows you to build sophisticated, scalable applications. Its use cases include enterprise IT, backup and storage, big data analytics, website hosting, mobile apps, gaming.

## AWS Global Infrastructure
### AWS Regions
A **Region** is a cluster of data centers. Most AWS services are scoped to a particular region.

AWS has regions all around the world. Region names are structured like us-east-1, eu-west-3.

How to choose an AWS region? 
- **Compliance** - data governance and legal requirements. Data never leaves a region without your explicit permission
- **Proximity** to customers to reduce latency
- **Available services** - new services and new features aren't available in every region
- **Pricing** - pricing varies region to region and is transparent in the service pricing page

### AWS Availability Zones
An **Availability Zone** (AZ) is one or more discrete data centers with redundant power, networking and connectivity. They are connected with high bandwidth, ultra low latency networking to form a region. They are physically separate from each other in case of disasters.

Each region has between 3 and 6 AZs. AZ names are region names plus a letter, such as ap-southeast-2a, ap-southeast-2b, ap-southeast-2c

### AWS Points of Presence (Edge Locations)
AWS has 400+ Points of Presence (~400 Edge Locations and ~10 Regional Caches) in 90+ cities across 40+ countries.

#### AWS Global Services
- Identity and Access Management (IAM)
- Route 53 (DNS service)
- CloudFront (Content Delivery Network)
- WAF (Web Application Firewall)

### Region-Scoped Services (most services)
- EC2 (Infrastructure as a service)
- Elastic Beanstalk (Platform as a service)
- Lambda (Function as a service)
- Rekognition (Software as a service)

## IAM and AWS CLI
**Identity and Access Management** (IAM) is a global service.

A root account is created by default. It shouldn't be shared, and usually shouldn't be used.

**Users** are people within your organization, and can be grouped. **Groups** can only contain users, not other groups. Users don't have to belong to a group and a user can belong to multiple groups.

Users or Groups can be assigned JSON documents called policies. These policies define the permissions of users.

In AWS, apply the **least privilege principle**: don't give a user more permissions than they need.

### IAM Policies
If you attach a policy at the group level it will get applied to every user in the group.

You can also create an inline policy that is only attached to a user.

IAM policy structure:
- Version - policy language version, usually "2012-10-17"
- Id - identifier for the policy (optional)
- Statement
	- Sid - identifier for the statement (optional)
	- Effect - whether the statement allows or denies access (Allow, Deny)
	- Principal - account/user/role to which this policy applies
	- Action - list of actions this policy allows/denies
	- Resource - list of resources which the actions will be applied to
	- Condition - conditions for when this policy is in effect (optional)

### IAM Password Policy
Stronger passwords provide higher security for your account.

In AWS you can set up a password policy:
- Set a minimum password length
- Require specific character types
- Allow all IAM users to change their own passwords
- Require users to change their password after some time (password expiration)
- Prevent password reuse

### Multi-Factor Authentication - MFA
Depending on their role, users can possibly change configurations or delete resources in your AWS account. You need to protect root accounts and IAM users.

MFA uses a combination of a password + a security device that you own. The main benefit of MFA is that if a password is stolen or hacked, the account is not compromised.

MFA device options in AWS:
- Virtual MFA device, such as Google Authenticator or Authy. Supports multiple token on a single device.
- Universal 2nd Factor (U2F) Security Key, such as YubiKey by Yubico. Supports multiple root and IAM users using a single security key.
- Hardware Key Fob MFA Device, such as provided by Gemalto
- Hardware Key Fob MFA Device for AWS GovCloud (US), such as provided by SurePassID

### AWS Access Keys, CLI and SDK
To access AWS, you have three options:
- AWS Management Console (protected by password + MFA)
- AWS Command Line Interface (CLI) - protected by access keys
- AWS Software Development Kit (SDK) - protected by access keys

Access keys are generated through the AWS console. Users manage their own access keys. Access keys should be treated like a username and password and kept secret.

The AWS CLI provides direct access to the public APIs of AWS services. You can develop scripts to manage your resources.

The AWS SDK is a set of libraries with language-specific APIs that you embed within your application. It allows you to access and manage AWS services programmatically. It supports several programming languages, including JavaScript, Python, Java, .NET, Go, C++, Ruby, PHP. 

There are also mobile SDKs, for Android and iOS, and IoT Device SDKs, for things like sensors or locks.

The AWS CLI is itself built on the AWS SDK for Python.

AWS CloudShell is an browser-based shell that gives you CLI access to your AWS resources. CloudShell provides a file system you can upload files to and download files from.

### IAM Roles for Services
Some AWS services will need to perform actions on your behalf. To do so, you assign permissions to AWS services using IAM Roles.

Common roles:
- EC2 Instance Roles
- Lambda Function Roles
- CloudFormation Roles

### IAM Security Tools
**IAM Credentials Report** (account-level)
- A report that lists all your account's users and the status of their various credentials

**IAM Access Advisor** (user-level)
- Shows the service permissions granted to a user and when those services were last accessed
- You can use this information to revise your policies

### IAM Guidelines and Best Practices
- Don't use root account except for AWS account setup
- One physical user = one AWS user (don't share credentials)
- Assign users to groups and assign permissions to groups
- Create a strong password policy
- Use and enforce the use of MFA
- Create and use Roles for giving permission to AWS services
- Use Access Keys for programmatic access (CLI / SDK)
- Audit permissions of your account using IAM Credentials Report and IAM Access Advisor
- Never share IAM users or Access Keys

### Shared Responsibility Model for IAM
AWS is responsible for:
- Infrastructure (global network security)
- Configuration and vulnerability analysis
- Compliance validation

You are responsible for:
- Users, Groups, Roles, Policies management and monitoring
- Enable MFA on all accounts
- Rotate all your keys often
- Use IAM tools to apply appropriate permissions
- Analyze access patterns and review permissions

### IAM Summary
- **Users** - mapped to a physical user, has a password for AWS Console
- **Groups** - contain users only
- **Policies** - JSON documents that outline permissions for users or groups
- **Roles** - for AWS services such as EC2 instances
- **Security** - MFA and Password Policy
- **AWS CLI** - manage your AWS services from the command line
- **AWS SDK** - manage your AWS services using a programming language
- **Access Keys** - access AWS using the CLI or SDK
- **Audit** - IAM Credentials Manager and IAM Access Manager

## EC2 Fundamentals
Elastic Compute Cloud (EC2) is one of the most popular AWS offerings. It is infrastructure as a service. Knowing EC2 is fundamental to understanding how the cloud works.

It mainly consists of:
- Renting virtual machines (EC2)
- Storing data on virtual drives (EBS)
- Distributing load across machines (ELB)
- Scaling services using auto-scaling groups (ASG)

### EC2 sizing and configuration options:
- Operating systems: Linux, Windows or MacOS
- How much compute power and cores (CPU)
- How much RAM
- How much storage space
	- Network-attached (EBS & EFS)
	- Hardware (EC2 Instance Store)
- Network - speed of the network card, public IP address
- Firewall rules - security group
- Bootstrap script (configure at first launch) - EC2 User Data

### EC2 User Data Script
It's possible to bootstrap instances using an EC2 User Data script. Bootstrapping means launching commands when the machine starts. The script is only run once when the instance starts. 

EC2 user data is used to automate boot tasks, such as:
- Installing updates
- Installing software
- Download common files
- Anything else required

The EC2 User Data script runs as the root user.

### Selected EC2 Instance Types 
|Instance |vCPU |Mem(GB) |Storage |Network performance |EBS Bandwidth (Mbps)|
|--|--|--|--|--|--|
|t2.micro|1|1|EBS-only|Low to moderate||
|t2.xlarge|4|16|EBS-only|Moderate||
|c5d.4xlarge|16|32|1 x 400 NVMe SSD|Up to 10 Gbps|4,750|
|r5.16xlarge|64|512|EBS only|20 Gbps|13,600|
|m5.8xlarge|32|128|EBS only|10 Gbps|6,800|

t2.micro is part of the AWS free tier (up to 750 hours per month)

There are different types of EC2 instances:
- General Purpose
- Compute Optimized
- Memory Optimized
- Accelerated Computing
- Storage Optimized

The naming convention (for example, m5.2xlarge) is 
- instance class
- generation
- size within instance class

#### General Purpose EC2 Instances
- Good for diversity of workloads, such as web servers or code repositories
- Balance between
	- Compute
	- Memory
	- Networking

#### Compute Optimized EC2 Instances
- Good for compute-intensive tasks that require high performance processors
	- Batch processing workloads
	- Media transcoding
	- High performance computing (HPC)
	- High performance web servers
	- Scientific modelling and machine learning
	- Dedicating gaming servers

#### Memory Optimized EC2 Instances
- Fast performance for workloads that process large data sets in memory
- Use cases
	- High performance relational/non-relational databases
	- Distributed web-scale cache stores
	- In-memory databases optimized for BI (Business Intelligence)
	- Applications performing real-time processing on big unstructured data

#### Storage Optimized EC2 Instances
- Good for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage
- Use cases:
	-  High-frequency online transaction processing (OLTP) systems
	- Relational and NoSQL databases
	- Cache for in-memory databases (such as Redis)
	- Data warehousing applications
	- Distributed file systems

### Security Groups
Security groups are fundamental to networking security in AWS. They control how traffic is allowed into or out of your EC2 instances.

Security groups only contain **allow** rules. Security group rules can reference by IP or by security group.

Security groups act as a "firewall" on your EC2 instances. They regulate:
- Access to ports
- Authorized IP ranges (IPv4 and IPv6)
- Control of inbound network
- Control of outbound network

Security groups can be attached to multiple instances and an instance can have multiple security groups. They are locked down to a region/VPC combination.

Security groups live "outside" the EC2 instance; if traffic is blocked, the instance won't see it.

It's good to maintain a separate security group for SSH access.

If your application is not accessible and you get a timeout it's a security group issue. If your application gives a "connection refused" error, then it's either an application error or it hasn't launched.
 
By default, all inbound traffic is blocked and all outbound traffic is authorised.

EC2 instances are authorized to communicate with each other by their security groups, regardless of their IP addresses.

### Classic Ports
- 22 - SSH (Secure Shell) - log into a Linux instance
- 21 - FTP (File Transfer Protocol) - upload files to a file share
- 22 - SFTP (Secure File Transfer Protocol) - upload files using SSH
- 80 - HTTP - access unsecured websites
- 443 - HTTPS - access secured websites
- 3389 - RDP (Remote Desktop Protocol) - log into a Windows instance

### SSH
SSH allows you to control a remote machine from your command line.

| . | SSH | Putty | EC2 Instance Connect |
| ---- | ---- | ---- | ---- |
| Mac | X |  | X |
| Linux | X |  | X |
| Windows < 10 |  | X | X |
| Windows >= 10 | X | X | X |
`ssh -i SECURITY_KEY ec2-user@PUBLIC_IP_ADDRESS`

#### EC2 Instance Connect
EC2 Instance Connect lets you create a browser-based SSH session into your EC2 instance. You can access this from your Instances dashboard and then have access to a command line on your instance.

#### EC2 Instance Purchasing Options
- **On-Demand Instances** - good for short workloads, predictable pricing, pay by second
- **Reserved** (1 and 3 years)
	- Reserved Instances - good for long workloads
	- Convertible Reserved Instances - long workloads with flexible instances
- **Savings Plans** (1 and 3 years) - commitment to a specific amount of usage in dollars, good long workloads
- **Spot Instances** - short workloads, very cheap, can lose instances at any time
- **Dedicated Hosts** - book an entire physical server, control instance placement
- **Dedicated Instances** - no other customers share your hardware
- **Capacity Reservations** - reserve capacity in a specific AZ for any duration

#### EC2 On Demand
Pay for what you use. For Linux or Windows, billed per second after the first minute. For other OSes, billed per hour.

Has the highest cost but no upfront payment and no long term commitment. Recommended for short-term and uninterrupted workloads, where you can't predict how the application will behave.

#### EC2 Reserved Instances
Give you a 72% discount compared to On-Demand. You reserve a specific instance attribute (Instance type, region, tenancy, OS).

You specify:
- reservation period (1 or 3 years)
- payment options (all upfront, partially upfront, not upfront)
- the instance scope - regional or zonal

Reserved Instances are recommended for steady-state usage applications (such as databases).

You can buy or sell reserved instances in the Reserved Instance Marketplace.

Convertible Reserved Instances let you change the instance type, instance family, OS, scope, and tenancy. You get a slightly lower discount, 66%.

#### EC2 Savings Plans
Get a discount based on long-term usage (up to 72%). You commit to a certain type of usage (such as $10/hour for 1 or 3 years).

Any usage beyond the plan is billed at the On-Demand price.

You are locked to a specific instance family and AWs region, such as M5 in us-east-1, but are flexible across:
- Instance size
- OS
- Tenancy

#### EC2 Spot Instance
Up to 90% discount compared to On-Demand but you can "lose" them at any time if your max price is less than the current spot price.

The most cost-efficient instances in AWs. Useful for workloads that are resilient to failure:
- Batch jobs
- Data analysis
- Image processing
- Any distributed workloads
- Workloads with a flexible start and end time

Spot Instances are not suitable for critical jobs or databases.

#### EC2 Dedicated Hosts
A physical server with EC2 instance capacity fully dedicated to your use. Allows you to address compliance requirements and use your existing server-bound licences (per-socket, per-core, per-VM software licences).

Purchasing options:
- On-Demand - pay per second for active dedicated host
- Reserved - 1 or 3 years

They are the most expensive option. Useful for software that has complicated licencing model (BYOL - Bring your own licence) or for companies that have strong regulator or compliance needs.

#### EC2 Dedicated Instances
Instances run on hardware that's dedicated to you. But you may share hardware with other instances in the same account. 

You have no control over instance placement. 

#### EC2 Capacity Reservations
Reserve On-Demand Instances capacity in a specific AZ for any duration. You always have access to EC2 capacity when you need it. 

There are no time commitments but also no billing discounts. Combine with Regional Reserved Instances and Savings Plans to benefit from billing discounts.

You are charged the On-Demand rate whether you run instances or not.

## EC2 Instance Storage
### Elastic Block Storage (EBS)
An Elastic Block Storage (EBS) volume is a network drive you can attach to your EC2 instances while they run.

It allows you to persist data even after the instance is terminated.

An EBS volume can usually only be bound to one instance at a time (though there are "multi-attach" features for some EBS).

An EBS volume is bound to a specific Availability Zone.

EBS volumes are network drives, not physical drives.
- They use the network to communicate with an instance, which means there might be some latency
- They can be detached from one EC2 instance and quickly attached to another one.
- They are locked to an AZ, for example an EBS volume in us-east-1a cannot be attached to an instance in us-east-1b. To move a volume, you first need to snapshot it
- They have a specific capacity provisioned in advance (size in GBs and IOPS), though this capacity can be increased over time

When you create an EBS volume you can set a Delete on Terminate attribute.
- By default, the root EBS volume is deleted when the EC2 instance terminates (attribute enabled)
- By default, any other attached EBS volume is not deleted (attribute disabled)

### EBS Snapshots
EBS snapshots allow you to make a backup of your EBS volume at a specific point in time. 

It's not necessary to detach a volume to perform a snapshot but is recommended.

You can copy and restore snapshots across AZs or Regions.

**EBS Snapshot Archive** - You can move a snapshot to an archive tier that is up to 75% cheaper. It takes from 24-72 hours to restore from an archive.

**Recycle Bin for EBS Snapshots** - You can set rules to retain deleted snapshots so you can recover them after an accidental deletion. You can specify a retention period from 24 hours to 1 year.

**Fast Snapshot Restore** - You can force full initialization of a snapshot to have no latency on its first use, but it is relatively expensive.

### Amazon Machine Image (AMI)
An Amazon Machine Image (AMI) is a customization of an EC2 image where you can add your own software, configuration, OS, monitoring, etc.

An AMI provides a faster boot/configuration time because all of your software is pre-packaged.

AMIs are built for a specific region, but can be copied across regions.

You can launch EC2 instances from:
- A public AMI provided by AWS
- Your own AMI, made and maintained by you
- An AMI from the AWS Marketplace, made and potentially sold by someone else

AMI Process:
- Start an EC2 instance and customize it
- Stop the instance and check for data integrity
- Build an AMI - this will also create EBS snapshots
- Launch instances from other AMIs


## AWS Accounts
AN AWS Account is a container for Identities (users) and Resources.

When creating an AWS Account you provide an account name (such as PROD), a unique email address, and a credit card.

Every account has a unique account Root User. The account Root User has full control over that specific AWS account and any resources created within it, and can't be restricted.

The credit card used at account setup is set as the Account Payment Method. Resources bill to the account payment method as they are consumed.

With Identity and Access Management (IAM), Users, Groups and Roles can be created and given full or limited permissions. Apart from the Root User, any IAM identity starts off with no permissions and needs to be explicitly granted them.

Accounts can contain the impact of admin errors, or exploits by bad actors. Use separate accounts for separate things (DEV, TEST, PROD) or teams or products or clients.

By default, all access to an account and its resources is denied expect for the Root User. External identities can be explicitly granted access.

### Multi-Factor Authentication (MFA)
Factors are pieces of evidence that prove identity. MFA uses multiple factors, or types of factors, to log into an application.

Types of factors:
- Knowledge - something you know: username, password
- Possession - something you have, bank card, MFA device
- Inherent - something you are: fingerprint, face, voice
- Location - A physical location or type of network (corporate or home)

More factors mean more security, making it harder to fake identity.

For an AWS account, AWS generates a secret key and additional information (user, service) and encodes this in a QR code. Your MFA application scans this code and transfers this information into the application.

An MFA app can hold different virtual MFA devices to be used for different accounts and services.

### Identity and Access Management (IAM)
The AWS account root user can be thought of as the same as the account itself. It's created with the account and can't be restricted in any way.

In real-world scenarios, you will want to give people, groups and applications limited access to the account.

Every AWS account comes with its own copy of IAM. IAM isa  globally-resilient service, any data is secured across all AWS regions.

The IAM you use in your account is your own dedicated instance of IAM, separate from other accounts. Your AWS account trusts your instance of IAM, it can do as much as the root user.

IAM can create multiple identities and allow them to do certain things.

IAM lets you create three different types of identity objects.

- Users - represent humans or applications that need access to your AWS account
- Groups - collections of related users (devs, finance, HR)
- Roles - can be used by AWS services or if you want to grant external access to your account. Can be granted to an uncertain number of entities, such as all of your EC2 instances

You will use Users when you can identify the specific person or thing that needs access. Roles are used when the number of things is uncertain.

IAM Policies are objects or documents which can be used to allow or deny access to AWS services, when and only when they are attached to IAM Users, Groups or Roles.

IAM has three main jobs:
- Manages identities (ID Provider - IDP)
- Authenticates identities
- Authorizes access to AWS resources based on policies

IAM is provided for free. Though there are limits on how many Users, Groups and Roles you can have.

IAM is a global service (has a globally resilient database).

IAM only controls what its local identities can do. It doesn't allow direct control over external accounts or users.

IAM lets you make use of identity federation (such as Active Directory) and MFA.

 It's best practice to only use the account Root User for account setup and then use an IAM admin user from then on.

https://ghynes-da-general.signin.aws.amazon.com/console

https://ghynes-da-production.signin.aws.amazon.com/console

#### IAM Access Keys
Access keys are long-term credentials available within AWS for IAM Users. They are long term in the sense that they don't change automatically or regularly.

You will use User and password when accessing the console UI and access keys when using the command line.

An IAM User has 1 username and 1 password. An IAM User can have two access keys. 

Access keys can be created, deleted, made inactive or made active.

Access keys are made of two parts:
- Access Key ID
- Secret Access Key

When you make a request to AWS from the CLI you use both of these parts.

## AWS Fundamentals
### Public vs Private Services
AWS services can be categorized into two main types: public services and private services. This refers to their networking only.

A public service, such as S3, can be accessed from public endpoints, basically anywhere there is an internet connection. A private service runs within a Virtual Private Cloud (VPC) and only things in or directly connected to the VPC can access it. For both, there are permissions as well as networking.

VPCs are isolated and can't communicate with each other unless you allow it. Nothing from the internet can reach these private networks unless you configure it. On-premise networks can only access VPCs if configured via VPN or Direct Connect.

There are actually three different network zones: the public internet, the AWS private zone and the AWS public zone. The AWS public zone runs between the public internet and the AWS private zone networks. It's a network connected to the public internet. AWS public services operate from the AWS public zone.

You can attach an Internet Gateway to a VPC. This provides additional functionality: It allows private zone resources to access the public internet as long as they have an allocated public IP address. It allows private services to access public services without touching the public internet. Private services can be given a public IP address which is translated by the IGW.

### AWS Global Infrastructure
While AWS is a global cloud platform, it is actually a collection of smaller groupings of infrastructure connected together by a global high speed network.

An AWS Region doesn't map onto a continent or country, it's a creation of AWS. Inside this region is a full deployment of AWS infrastructure: compute services, storage, database products, and more. Regions are geographically spread, which helps us to design systems that can withstand global-level disasters. 

When you're interacting with most AWS services, you are interacting with that service in a specific region. So EC2 in Virginia is separate from EC2 in Sydney.

AWS Edge Locations are much smaller than regions and generally only have content distribution services and some types of edge computing. They are useful for storing files as close to customers as possible, for example for video streaming.

Regions and Edge Locations are commonly used together in the same system. Service such as IAM and Route53 are global, while most others are region-specific.

Regions have three main benefits:
- Geographic separation - which creates an isolated fault domain 
- Geopolitical separation  - different governance/legislation. Data doesn't leave a region
- Location control - tune your architecture for performance

AWS Availability Zones (AZs) provide isolated infrastructure inside a region. An AZ could be one data centre or part of multiple data centres. Each AZ is isolated from the other AZs in the Region and connected with high-speed, redundant networking. Services can be placed across multiple AZs to make them resilient.

The resilience level of a service is described in one of three ways:
- Globally resilient - replicated across regions and can tolerate the failure of an entire region, such as IAM or Route 53
- Region resilient - operate within a single region, with one set of data per region, data is replicated to multiple AZs, can tolerate the failure of an AZ
- AZ resilient - services run from a single AZ, if that AZ fails the service fails

### Virtual Private Cloud (VPC)
VPC is the service you use to create private networks inside AWS, that other private services will run from. VPC lets you connect to on-premise solutions or other cloud platforms.

A VPC is a virtual network inside AWS. It is within one account and one region. By default a VPC is private and isolated.

There are two types of VPC available in a Region: the default VPC and custom VPCs. Default VPCs (one per region) come preconfigured by AWS.

The default VPC is assigned a range of IP addresses, the VPC CIDR `172.31.0.0/16`. Custom VPCs can have multiple CIDR ranges. 

VPCs can be subdivided into subnets. Each subnet is located in one AZ. The default VPC is configured to have a subnet in each AZ in the Region. The IP ranges the subnets are given also define the IP ranges for any services within that subnet.

The default VPC can be deleted and recreated. Some services assume that the default VPC will be present. You are provided with an Internet Gateway, Security Group and NACL. By default, anything placed in the default VPC subnets is assigned a public IPv4 address.

### Elastic Compute Cloud (EC2)
EC2 is essentially the default compute service in AWS. It provides access to virtual machines known as instances with resources you select and an OS of your choosing. 

EC2 is IaaS. It provides access to virtual machines known as EC2 instances. Your unit of consumption is the instance. An instance is just an OS, configured in a certain way, with a certain set of allocated resources.

EC2 is a private service by default. It uses VPC networking. An EC2 instance is configured to launch into a single VPC subnet. If you want public access for an EC2 instance, then the VPC it's running in needs to support that public access.

EC2 is AZ resilient, if the AZ fails then the instance will fail. 

When you launch an EC2 instance, you choose different sizes and capabilities for that instance. Some, but not all, of these can be updated afterwards.

EC2 offers on-demand billing, by second or by hour. You pay for the resources that are used while the instance is operational. There is a charge for running the instance (CPU and memory consumed), a charge for the storage used, and then extras for any commercial software the instance launches with.

There are various types of storage available. Storage can be on the local host, the EC2 host that the instance runs on, as well as on another AWS service, such as Elastic Block Store (EBS).

An instance has a state attribute. An instance can be running, stopped or terminated (as well as a few others in between). Terminated is a non-reversible action. State influences the charges for an instance. When an instance is running, you are being charged for CPU, memory, storage and networking. When stopped, you are still charged for any storage the instance has been allocated. A terminated instance has no further resource usage and so no further costs.

An Amazon Machine Image (AMI) is an image of an EC2 instance. An AMI can be used to create an EC2 instance, or can be created from an EC2 instance. An AMI is similar to a server image, used to create virtual machines. 

An AMI contains attached permissions. It can be public, so that everyone can create an instance based off it. The owner of the AMI is implicitly allowed to create EC2 instances from the AMI. You can add explicit permissions to an AMI to explicitly grant access to specific AWS accounts.

An AMI also contains the boot volume of the instance (C-drive / root volume). It can contain other volumes too. The AMI also provides a block device mapping, a configuration which links the volumes the AMI has and how they're presented to the OS. It links the volume to the device ID that the OS expects.

If the EC2 instance is running Windows, you connect using RDP (Remote Desktop Protocol). With Linux instances, you use the SSH protocol. When you create the instance, you generate a key pair. The public key is stored on the instance and you use the private key to authenticate and connect to the instance.

### Simple Storage Service (S3)
S3 is a global storage platform, and can be accessed from anywhere with an internet connection. It is regional based with your data stored in a specific AWS region at rest. It is regionally resilient; the data is replicated across AZs in that region. S3 can tolerate the failure of an AZ and has some ability to replicate data between regions.

S3 is a public service, running from the AWS public zone. It can cope with unlimited data amounts and is designed for multi-user usage of that data.

S3 is perfect for hosting large amounts of data, such as films, audio, photos, text, large data sets. It scales from nothing to near unlimited levels.

S3 is economical for storing and allowing access to data. It can be accessed via UI, CLI, API, HTTP.

Think of S3 as the default storage service in AWS. It delivers two main things:
- Objects - the data that S3 stores
- Buckets - containers for objects

Think about objects like files. An object in S3 is made up of the object key (similar to a filename), the value (the data or contents of the object) and some associated metadata. If you know the bucket and object key then you can uniquely access the object. The value of an object can range from 0 bytes to 5 terabytes. Objects also have a version ID, metadata, access control and sub-resources.

Buckets are created in a specific AWS region. The data never leaves that region unless you configure it to. That means that S3 has stable and controlled data sovereignty. By creating a bucket in a region you can control what laws and rules apply to that data. This also means that the blast radius of a failure is that region.

A bucket name needs to be globally unique. Most things in AWS only need to be unique per region or per account. As an object storage system, an S3 bucket has no complex structure. It has a flat structure. All objects stored within the bucket are at the same level. The UI presents information as folders based off naming conventions but this isn't accurate. There is no concept of filetype based on name. `/old/photo1.jpg`, `/old/photo2.jpg`, `/old/photo3.jpg` will be presented as being in a folder `/old`. Folders are often referred to as "prefixes" in S3 because they are part of the object names.

For the exam:
- bucket names are globally unique
- 3-63 characters, all lowercase, no underscores
- start with lowercase letter or number
- cannot be IP formatted, such as 1.1.1.1
- 100 bucket soft limit, 1,000 bucket hard limit per account
- Unlimited objects in a bucket, 0 bytes to 5TB
- key = name, value = data

You can take a single bucket and divide it using prefixes to have thousands of users using one bucket.

#### S3 Patterns and Anti-Patterns
- S3 is an object store, not file or block
- You cannot mount an S3 bucket (as `K:\` or `/images`)
- S3 is great for large-scale data storage , distribution or upload
- Great for offloading things (images, audio, video) from expensive compute instances to cheaper storage
- Input and output to many AWS products (most services that consume or output data can have S3 as an option)

### Cloud Formation (CFN)
CloudFormation is an IaaS product in AWS that allows you to automate creating, updating and deleting infrastructure in a consistent and repeatable way using templates.

You can create infrastructure using a a template as well as update a template and reapply, causing CloudFormation to update the infrastructure. A template is written in either YAML or JSON.

```
AWSTemplateFormatVersion:
Description:
Metadata:
Parameters:
Mappings:
Conditions:
Transform:
Resources:
Outputs:
```

All templates have a list of `Resources`, the only mandatory part. Adding, updating, or removing resources from this section will cause CloudFormation to create, update or delete AWS resources.

Templates usually include a `Description`, a free text field that lets the author add a description. Description needs to immediately follow `AWSTemplateFormatVersion` if both are present.  `AWSTemplateFormatVersion` is how AWS allows for extending the standards over time. 

`Metadata`, among other things, controls how the template's sections are presented through the console UI. `Parameters` lets you add fields which prompt the user for more information. `Mappings` lets you create lookup tables. `Conditions` allows for decision making in the template. `Outputs` let the template return outputs based on what was created, updated, or deleted.

CloudFormation creates infrastructure based off Resources. Individual resources are called logical resources, and have a type. They also have properties to define how they're configured.

```
Resources:
	Instance:
		Type: "AWS::EC2::Instance"
		Properties:
			ImageId: !Ref LatestAmiId
			InstanceType: !Ref InstanceType
			KeyName: !Ref KeyName
```

When you give a template to CloudFormation, it creates a Stack, containing all the logical resources that the template tells it to contain. For any logical resources in the stack, CloudFormation makes a corresponding physical resource in your AWS account. It is CloudFormation's job to keep the logical and physical resources in sync. If you delete a stack, its logical resources are deleted, which causes CloudFormation to delete the matching physical resources.

When you upload a template to CloudFormation, it uploads the template directly to an S3 bucket (prefixed with cf) that it creates automatically. CloudFormation functions, such as `!Ref` or `!GetAtt`, lets you reference other parts of the template.

### CloudWatch
CloudWatch is a core supporting service in AWS that provides metrics, logs and event management services. 

CloudWatch collects and manages operational data. It has three core components:
- **Metrics** - such as CPU usage from AWS products, apps, on-premises. CloudWatch is a public service and can gather metrics from inside or outside AWS. Some metrics are gathered natively by the product. Some types of metrics need a CloudWatch Agent, for example monitor things not otherwise exposed to AWS.
- **CloudWatch Logs** - almost anything which is logged can be ingested. Again, a CloudWatch Agent is needed for logs from outside AWS.
- **CloudWatch Events** - an event hub, for example generating events if an EC2 instance is created, started, or stopped, or generating an event to do something at a certain time. Events can, for example, be published to Simple Notification Service (SNS) or trigger auto-scaling.

CloudWatch gives you a UI, CLI and API to access the data it collects.

A Namespace is a container for monitoring data to keep things organized. All AWS data goes into an AWS namespace, `AWS/service-name`, such as `AWS/EC2`. This naming is reserved and you cannot use it.

A Metric is a collection of related data points in a time ordered structure, such as CPU usage, Network In/Out, Disk I/O. A metric is not for a specific server. A metric might be receiving CPU utilization data from lots of EC2 instances.

Datapoints are in simple terms a timestamp and a value. For example, every time a server measures its CPU utilization and sends it to CloudWatch, each measurement is a datapoint. 

Dimensions are used to separate datapoints for different things or perspectives within the same metric, such as which EC2 instance is sending CPU utilization metrics. 

```
Name = InstanceId, Value= 1-xxxxxxxxx
Name = InstanceType, Value = t3.small
```

CloudWatch lets you take actions based on metrics using Alarms. Alarms are created and linked to a specific metric. You configure the alarm so it will take an action based on that metric. The alarm can be in the OK state and can move to the ALARM state if specified criteria are met. Based on this, you can define an action to be taken, such as sending a notification to an SNS topic. Alarms can also exist in a third state, INSUFFICIENT_DATA, before they have collected enough data to know if they should be in an OK or ALARM state.

### Shared Responsibility Model
The Shared Responsibility Model is how AWS provide clarity around which areas of system security are theirs and which are owned by the customer.

AWS are responsible for the security **of** the cloud. You, as the customer, are responsible for security **in** the cloud. 

AWS are responsible for the hardware and global infrastructure; compute, storage, database and networking components; and any software that assists those services. You are responsible for the OS upwards: client-side data encryption, server-side encryption, networking traffic protection; OS, network and firewall configuration; applications, identity and access management, customer data.

### High-Availability vs Fault-Tolerance vs Disaster-Recovery
High Availability (HA) - "aims to ensure an agreed level of performance, usually uptime, for a higher than normal period". HA doesn't mean that a system never fails or that a user never experiences any outages.

A highly available system is one designed to be online and providing services as often as possible. It is designed so that when it fails, its components can be replaced or fixed as quickly as possible, often using automation to bring systems back into service. HA is about maximising a system's online time.

System availability is generally expressed in the form of a percentage of uptime. So 99.9% (3 nines) means you can only have 8.77 hours of downtime per year. 99.999% (5 nines) would only allow for 5.26 minutes of downtime.

If an application has to fail over to a standby server, there might be some small user disruption (such as, having to re-log in). Some user disruption is fine as long as outages are minimized.

HA has costs required to implement it. It needs some design decisions to be made in advance and it requires a certain level of automation.

Fault Tolerance (FT) - "is the property that enables a system to continue operating properly in the event of the failure of some (one or more) of its components". The system should continue to operate properly even while those faults are present and being fixed. Fault tolerant systems are designed to work through failure with no disruption.

A fault tolerant system might have two servers in an active-active configuration. If one fails, the system remains fully functional.

HA is about maximising uptime, FT is about operating through failure. FT is much more difficult, complex and expensive to be implemented. Mission or life critical systems need to be fault tolerant.

Disaster Recovery (DR) - "a set of policies, tools and procedures to enable the recovery or continuation of vital technology infrastructure and systems following a natural or human-induced disaster". DR is what happens when high availability or fault tolerance fail.

A good DR system involves regular backups stored at a second location from the main site as your systems. All your processes and logins need to be available at your standby site to minimize disruption. Ideally you want to run periodic DR testing.

High availability - minimize any outages
Fault tolerance - Operate through faults
Disaster Recovery - Used when these don't work

### Route53
Route53 is AWS's managed DNS product. It allows you to register domains and can host zone files for you on managed namespace servers.

Route53 is a global service with a single database. The data Route53 manages is distributed globally and replicated between regions, making it globally resilient.

Route53 has relationships with all of the main domain registries. When a  domain is registered, Route53 checks with the registry for that top level domain if the domain is available. Then Route53 creates a zone file for the domain being registered. Route53 also allocates (usually four) name servers for this zone. It then liaises with the registry and adds these name server records into the zone file for the top level domain, using name server records.

Route53 provides DNS zones as well as hosting for those zones. Basically, DNS as a service. It lets you create and manage zone files, called hosted zones because they're hosted on AWS managed name servers. From Route53's perspective, every hosted zone also has a number of allocated managed name servers.

A hosted zone can be public, with the data accessible on the public internet. The name servers for a public hosted zone live in the AWS public zone.

A hosted zone can also be private, linked to one or more VPCs and only accessible within those VPCs. You might use this if you want to host sensitive DNS records.

#### DNS Record Types
Nameserver Records (NS) allow delegation to happen in DNS.

A and AAAA Records map hostnames to IP addresses. An A record maps onto an IPv4 address. An AAAA maps onto an IPv6 address. You will normally create both with the same name.

CNAME Records let you create the equivalent of DNS shortcuts. For example, CNAMEs for mail, FTP and web services could all point to an A record. CNAMEs cannot point to an IP address, only to another names.

MX Records are how a server can find the mail server for a specific domain. They have two main parts: priority and value. The value can point to a host in the same zone (`mail`) or to a fully qualified domain (`mail.other.domain`). Lower values for the priority field mean higher priority.

TXT Records allow you to add arbitrary text to a domain, for example to prove domain ownership.

Time to Live (TTL) can be set on DNS records. It's a numerical value in seconds. DNS values are cached as non-authoritative answers. TTL means that updated records will get picked up when the cache expires. When planning on changing DNS records, it's advisable to lower the caching TTL well in advance to limit delays in the new DNS records getting picked up.

## IAM, Accounts, and AWS Organizations
### IAM Identity Policies
IAM policies are a type of policy which get attached to identities (users, groups and roles) inside AWS.

An IAM policy is just a set of security statements to AWS. It grants or denies access to AWS products and features to any identity which uses that policy.

At a high level, a policy document is one or more Statements, which grant or deny permissions to AWS services, in a JSON document. When an identity attempts to access AWS resources, that identity needs to prove who it is to AWS. Once authenticated, that identity is known as an authenticated identity.

An identity can have multiple policies and each policy can have multiple Statements in it. AWS has a collection of all of the statements which apply to a given identity.

A Statement is made up of:

- A Statement ID (Sid), an optional field, which lets you identify a statement and what it does, such as `"FullAccess"` or `"DenyCatGifsBucket"`. It's best practice to always use these.
- Action and Resource: a statement only applies if the interaction you're having with AWS match the Action and Resource. The format for action is `service:operation`, such as `["s3:*]"`. `*` can match any service operations. You can specify individual resources or lists of resources: `["arn:aws:s3::catgifs"]`
- Effect: either Allow or Deny. Statements can combine these. You can be allowed certain actions on a resource, but not others, or denied all actions on a resource, except specific exceptions. For example, allow any action on any S3 bucket and then deny access to a small portion of S3.

Priorities (Deny, Allow, Deny):
1. The first priority are explicit denies. It overrules anything else.
2. The second priority are explicit allows. Overruled by explicit deny.
3. If explicit allows or denies aren't defined then the default implicit deny takes effect.

With the exception of the account root user, AWS identities start off with no access to any AWS resources.

Multiple policies can apply to the same identity. An individual developer, the group they're in, and the resource they're trying to access may all have policies associated with them.

When a given identity accesses a resource, AWS collects all of the policy statements which apply and applies the Deny, Allow, Deny rule to them.

There are two main types of policies: inline and managed policies. They are the same thing, the difference is how they're managed. Designing a policy and assigning that JSON individually on separate accounts is an inline policy. The policy becomes isolated bits of JSON. This is not best practice. Managed policies are created as their own object and then attached to any identities that you want to have those access rights.

Managed policies are reusable and have lower management overhead. They should be used for the default operational rights in your business. If you change the JSON in a managed policy, it immediately impacts all of the identities it's attached to.

There are two main types of managed policies: AWS managed policies, created and managed by AWS, and customer managed policies, which you can define to match your requirements.

Inline policies are used for exceptions to normal rights for special circumstances.

### IAM Users and ARNs
IAM Users are an identity used for anything requiring long-term AWS access, such as humans, applications, or service accounts.

If you can picture one named thing that needs to access AWS, then 99% of the time the correct identity to select is an IAM user.

A Principal is an entity trying to access an AWS account. Principals can be individual people, computers services, or a group of any of those things. For a principal to be able to do anything, it needs to authenticate and be authorized.

A principal makes requests to IAM to interact with resources. To be able to interact with resources, it needs to authenticate against an identity within IAM. Authentication for IAM users is done using either username and password, or access keys.

Once the principal goes through the authentication process, the principal is now known as an authenticated identity. AWS then knows which policies apply to this identity. Once an authenticated identity tries to access an AWS service, AWS checks that that identity is authorized to do so.

Amazon Resource Names (ARN) uniquely identify resources within any AWS accounts. ARNs let you unambiguously refer to a single resource, or if needed a group of resources using wildcards.

ARNs are used in IAM policies, which are generally attached to identities. The format is usually:

```
arn:partition:service:region:account-id:resource-id
arn:partition:service:region:account-id:resource-type/resource-id
arn:partition:service:region:account-id:resource-type:resource-id
```

ARNs are collections of fields split y colons. If you see a double colon, it means that nothing is between it. For example, S3 buckets need to be globally unique, so `region` isn't included.

The first example ARN below references an actual S3 bucket. Use this to allow or deny access to a bucket and any actions on this bucket.

The second ARN below references anything in the bucket, but not the bucket itself.

Actions that operate at a bucket level, or that create buckets, would need the first ARN. Actions that work on objects would need the second ARN.

Sometimes, creating a policy that allows a set of actions will require both ARNs.

```
arn:aws:s3:::catgifs
arn:aws:s3:::catgifs/*
```

For the exam:
- you can only have 5,000 IAM Users per account
- IAM user can be a member of at most 10 groups
- This has system design impacts

If you have a system that requires more than 5,000 identities, then you can't use one IAM user for each identity. This might be a limit for large organizations, or internet-scale applications. You can use IAM roles or Identity Federation to get around this.

### IAM Groups
IAM Groups are containers for IAM Users. You can't log into IAM groups and they have no credentials of their own. They exist to make organizing large sets of IAM users easier.

An IAM user can be a member of multiple IAM groups.

Groups provide two main benefits:
- They allow for effective administration-style management of users
- Groups can have policies (both inline and managed) attached to them.

Users in groups receive the policies of all groups they are in. They can also have their own inline or managed policies. AWS will merge them into a set of permissions.

There's no explicit limit on the number of users in a single IAM group. You could have all 5,000 of an account's users be in a single group. There isn't a built-in all-users group in IAM, you would need to create and manage one yourself.

Groups do not nest. You can't have groups within groups. IAM groups contain users and can have permissions attached. That's it.

There is a limit of 300 groups per account but this can be increased with a support ticket.

Groups are not a true identity. They cannot be referenced as a principal in a policy. They cannot be referenced using an ARN, unlike users or resources. A Resource Policy cannot grant access to IAM groups. It can grant access to users, but not the group they're in.

Groups just exist to collect users and allow permissions to be assigned to those groups, which the users then inherit

### IAM Roles
A Role is one type of identity which exists inside an AWS account. The other type are IAM Users.

A Role is generally best suited to be used by an unknown number or multiple principals. This could be multiple users inside the same AWS account. Or it could be humans, applications, or services inside or outside your AWS account who make use of that role. If you can't identify the number of principals which use an identity, it could be a candidate for an IAM Role. Or if you have more than 5,000 principals.

Roles are generally used on a temporary basis. Something becomes that role for a short period of time and then stops.

A Role represents a level of access inside an AWS account. It is something that can be used, short term, by other identities. Identities assume a role for a short time, use the permissions that role has, and then they stop being that role.

IAM Roles have two types of policies, which can be attached:
- Trust Policy
- Permissions Policy

The Trust Policy controls which identities can assume that role. The trust policy can reference identities in the same account and in other AWS accounts.  It can even allow anonymous usage of that role, or other types of identities, such as Facebook or Google.

If a role gets assumed by something that is allowed to assume it, then AWS generates temporary security credentials and these are made available to the identity which assumed the role. Temporary credentials are like access keys, but instead of being long-term, they are time-limited. Once they expire, the identity will need to renew them by re-assuming the role. At that point, new credentials are generated and given to the identity again. 

These temporary credentials will be able to access whatever AWS resources are specified within the permission's policy. Every time the temporary credentials are sued, the access is checked against this permissions policy. If you change the permissions policy, the permissions of those temporary credentials also change.

Roles are real identities, and, just like IAM users, roles can be referenced within resource policies.

Roles are used within AWS organizations to allow us to login to one account in the organization and access different accounts without having to login again.

The role's temporary credentials are created by Secure Token Service (STS) using the operation `sts:AssumeRole`.

#### When to use IAM Roles
One of the most common uses of roles within the same AWS account are **for AWS services themselves**. AWS services operate on your behalf and they need access rights to perform certain actions.

For example, you can create an IAM role, known as a Lambda execution role, with a trust policy that trusts the Lambda service. This means that Lambda is allowed to assume that role whenever a function is executed. This role has a permissions policy which grants access to AWS products and services. 

When the function runs, it uses the `sts:AssumeRole` operation and then the Secure Token Service generates temporary security credentials. The runtime environment that the Lambda function runs in can use these temporary credentials to access AWS resources based on whatever permissions the role's permissions policy has.

If you didn't use a role, you would need to hardcode permissions into the Lambda function by explicitly providing access keys. This would be a security risk and would also cause problems if you ever need to change/rotate those keys.

Roles are also useful for **emergency or out-of-the-usual situations**. For example a support team might have read-only access to a customer's AWS resources, while anything more risky is handled by a more senior technical team. In an emergency, the support team might be able to assume an emergency role if absolutely required. This access will be logged.

Roles are also useful when adding AWS **into an existing corporate environment**. There might be an existing identity provider, such as Microsoft Active Directory. Roles can be used to re-use existing identities inside AWS. External accounts or external identities cannot access AWS resources directly. Instead, you allow the external account to assume an IAM role. If a business has more than 5,000 accounts then they can't simply create an IAM user for each account.

You might also use roles if **designing the architecture for a popular web/mobile application**, that is one with millions of users. Most mobile applications allow you to sign in using a web identity, such as Google or Facebook. Through Web Identity Federation, users of the app can use roles to access AWS resources, such as saving their data to DynamoDB.

This has advantages:
- There are no AWS credentials stored in the app
- It uses existing accounts that customers probably already have
- It can scale to hundreds of millions of users

Roles can be used cross-account to give access to individual resources, such as S3, or to a whole account. In a scenario where you are working with a partner account, need to access resources in that account, and have thousands of identities in your account, a role in the partner account is the best approach.

#### Service-linked Roles and PassRole
A Service-linked Role is an IAM role linked to a specific AWS service. They provide a set of permissions predefined by the service, providing permissions that a service needs in order to interact with other AWs services on your behalf.

Service-linked Roles might be created by the service itself, or the service might allow you to create the role during setup or within IAM.

The key difference with normal roles is that you can't delete a service-linked role until it's no longer required by that AWS service.

In the policy the resource is identified by `RESOURCE_NAME.amazonaws.com`. The formatting of this differs by service and is case sensitive.

Role separation is where you might give one group of people the ability to create roles and another group of people the ability to use them. PassRole permissions allow you to pass an existing role into an AWS service. For example, you could configure a service with a role that has already been created by the security team. This is the same type of architecture as when you use a pre-created role, for example with a CloudFormation stack.

### Security Token Service (STS)
Security Token Service (STS) generates temporary credentials whenever the `sts:AssumeRole` operation is used.

When you assume an IAM Role, you use the STS AssumeRole call and in doing so gain access to temporary credentials which can be used by the identity which assumes the role.

When you role switch in the console UI, you're assuming a role in another AWS account and using STS to gain access to these temporary credentials.

The temporary credentials generated by STS are similar in many ways to long-term access keys. They contain an access key ID (the public part) and a secret access key (the private part). Importantly, these credentials expire and they don't belong to the identity which assumes the role.

The access that these credentials provide can be limited. By default, the authorization is based on the permissions policy of the role, but a subset of that can be granted to the temporary credentials. So they don't need to have the full range of permissions that the permissions policy on a role provides.

The credentials can be used to access AWS resources, just like with long-term credentials.

Temporary credentials are requested by another identity, either an AWS identity such as an IAM user via an IAM role, or an external identity such as a Google login (web identity federation).

The trust policy controls who can assume the role. Conceptually it is like a wall around the role, only allowing certain people access to that role. If an identity isn't allowed to assume a role, based on the trust policy, `AssumeRole` fails.

`sts:AssumeRole` calls are made by an existing identity, either AWS or external (through federation). `AssumeRole` calls are made via the STS service. STS checks the role's trust policy. If the identity is allowed then it reads the permissions policy, which is also attached to the role. The permissions policy controls what is allowed or denied inside AWS.

STS generates temporary credentials which can access AWS resources until expiration. They authorize access based on the permissions policy. If the permissions policy changes, the permissions that the credentials have access to also change.

Temporary credentials include:
- AccessKeyId - unique id of credentials
- Expiration - date and time of credential expiration
- SecretAccessKey - used to sign requests
- SessionToken - unique token which must be passed with all requests

Credentials are returned to the identity requesting them. Another `sts:AssumeRole` call is required when the credentials expire.

You are using STS if you:
- assume a role within an AWS account
- role switch between accounts using the console UI
- perform cross-account access using a role

### AWS Organizations
AWS Organizations is a product which allows larger businesses to manage AWS accounts in cost effective way with little to no management overhead.

Without AWS Organizations each of the hundreds of AWS accounts a large business has would have their own pool of IAM users and their own payment method.

You use a standard AWS account to create an AWS Organization. The organization doesn't exists **in** this account. The account used to create the organization then becomes the **Management Account** for the organization. Using this management account you can invite other existing standard AWS accounts into the organization. The other accounts need to approve the invites to join the organization. When standard accounts join an organization they become **Member Accounts** of that organization.

The structure within AWS Organizations is hierarchical. At the top of the tree is the Organization Root, a container for AWS accounts. As well as containing accounts, the Organizational Root can also contain other containers, known as Organizational Units (OUs). OUs can contain member accounts or other OUs.

One important feature of AWS Organizations is consolidated billing. The individual billing methods are removed from the member accounts in the organization. Billing is passed though to the management account, sometimes referred to in this context as the Payer Account. You get a single monthly bill contained within the management account that covers all member accounts of the organization.

Consolidated billing removed financial admin overhead for larger businesses. Also, certain AWS services get cheaper the more usage you have and for certain services you can pay in advance in exchange for cheaper rates. When using organizations these benefits are pooled. 

AWS organizations also feature a service called service control policies (SCPs) and this lets you restrict what AWS accounts within the organization can do.

As well as being able to invite existing accounts into an organization, you can also create new accounts directly within it. You just need a valid unique email address for this account you want to create within the organization.

Using an AWS Organization changes what is best practice in terms of user logins and permissions. With organizations you don't need to have IAM users inside every dingle AWS account. Instead, IAM roles can be used to allow IAM users to access other AWS accounts.

Larger businesses will often keep the management account of the organization clean and have a separate account dedicated to handling logins. They might also use Identity Federation to integrate their existing identities with this single login/identities account.

From the identities account you can role switch into other accounts within the organization. Behind the scenes, this is assuming a role which is inside these other AWS accounts.

### Service Control Policies
Service Control Policies (SCPs) are a feature of AWS organizations which can be used to restrict AWS accounts. 

They are JOSN documents that can be attached to the organization as a whole, by attaching them to the root container, or they can be attached to one or more organizational units. They can even be attached to individual AWS accounts.

SCPs inherit down the organization tree. If they're attached to the organization as a whole, then they attach all accounts in the organization. If they're attached to an organizational unit, they impact all accounts inside that unit. If they are attached directly to one or more accounts, then they only affect those specific accounts. 

The management account is unaffected by any SCPs. Since the management account can't be restricted by SCPs, it's good to avoid using the management account for any AWS resources.

Service Control Policies are account permissions boundaries. They limit what the account (including, by extension, what the account root user) can do. You might apply a SCP to prevent any usage of an account outside of a known region, such as us-east-1. SCPs don't grant any permissions, they just limit what permissions can be assigned.

You can use Service Control Policies in two ways: you can block by default and then allow certain service via an allow list. Or you can allow by default and then block certain services via a deny list. The default is a deny list meaning that in the default implementation SCPs have no effect until you add restrictions.

Service Control Policies follow the Deny-Allow-Deny priority rules. Explicit denies always win over allows. A benefit of using a deny list is that as AWS adds products and services, the list constantly expands to cover these new services without much admin overhead.

Implementing allow lists is a two part process: first removing the AWS full access policy and then adding any services which you want to allow into the new policy. Allow lists require more admin overhead since you need to explicitly add every service you want to grant access to.

Only permissions which are allowed within identity policies in the account and are allowed by a service control policy are actually active. Your effective permissions for identities within an account are the overlap between any Identity Policies and any applicable SCPs.

### CloudWatch Logs
CloudWatch Logs is a public service (usable from AWS or on-prem) which allows you to store, monitor and access logging data. 

It has built-in integrations with other AWS services such as EC2, VPC Flow Logs, Lambda, CloudTrail, and Route53. These services can store data directly inside the product with security provided by IAM roles or services roles. Outside AWS, or for logging custom application or OS logs, you can use the Unified CloudWatch Agent. You can also use the development kits for AWS and implement logging to CloudWatch Logs directly in your application.

CloudWatch Logs can generate metrics based on logs. This is known as metric filters.

Data is injected into CloudWatch Logs as log events (timestamp and message). Log events are stored inside log streams. Log streams are a sequence of log events from the same source. Log groups are containers for multiple log streams for the same type of logging. Log groups are also where configuration settings (such as permissions and retention settings) are stored. 

Metric filters are also defined on log groups. They watch log streams for specific events. When triggered these filters increment metrics which can have associated alarms.

### CloudTrail
CloudTrail is a product which logs API actions that affect AWS accounts. Almost anything which can be done to an AWS account is logged by this product. 

API calls / account activities are logged as CloudTrail Events. By default, the last 90 days of activity is stored in Event History. To customize the service you create one or more Trails.

CloudTrail Events can be Management Events, Data Events, or Insight Events. Management Events provide information about management operations performed on resources in your AWS account. Data Events contain information about resource operations performed on or in a resource. By default, CloudTrail only logs management events because data events are often of a much higher volume. 

A CloudTrail trail is the unit of configuration within CloudTrail. A trail logs events for the AWS region it's created in. You can create a trail that is one-region or a trail can be set to all regions. If AWS adds any new regions, an all-region trail will be automatically updated.

Most services log events in the region where the event occurred. A small number of global services (such as IAM, STS, or CloudFront) log events globally to one region, us-east-1. These are called global service events and a trail needs to have this enabled in order to log these events.

A trail by default can store events in a definable S3 bucket, and the logs can be stored there indefinitely. The logs are stored as a set of compressed JSON log files so they consume little space but with the benefit of being able to be parsed by any tooling that can read these standard format files. CloudTrail can also be integrated with CloudWatch Logs and store its data there in addition to S3.

You can create an organizational trail. If you create a trail from the management account of an organization, it can store all of the information for all of the accounts inside that organization.

CloudTrail is enabled by default on AWS accounts, but only for 90 days event history. S3 storage needs to be configured for a trail. Trails are how you configure S3 and CloudWatch Logs storage. By default, only management events are stored. Data events need to be specifically enabled and come at an extra cost. IAM, STS, CloudFront generate global service events, which are logged to us-east-1 and a trail needs to be created to log that data.

One limitation of CloudTrail is that it is not real-time; there is a delay. CloudTrail typically delivers log files within 15 minutes of the account activity occurring. It generally publishes log files multiple times per hour.


## Simple Storage Service (S3)
### S3 Security
S3 is private by default. The only identity which has any initial access to an S3 bucket is the account root user of the account which owns that bucket. Any other permissions have to be explicitly granted.

S3 Bucket Policies are a type of resource policy, like an identity policy but attached to a bucket. They provide a resource perspective on permissions. With identity policies you are controlling what that identity can access, with resource policies you're controlling who can access that resource.

Identity policies cannot give an identity in another account access to a resource in your account. With resource policies you can allow or deny access from different accounts. Resource policies can reference any other identities inside that policy. Resource policies are good for controlling access to a particular resource, no matter what the source of that access is.

Resource policies can allow or deny anonymous principals. Identity policies, by contrast have to be attached to a valid identity in AWS. Resource policies can open a resource, like an S3 bucket, to anyone by referencing all principals. The Principal part of a resource policy defines which principals are affected by the policy. 

Bucket policies should be your default thought for granting anonymous access to objects in buckets, and are one way of granting access to external accounts.

Bucket policies can be used to control who can access objects, even allowing conditions which can block specific IP addresses. Bucket policies can be much more complex, for example one specific prefix can be protected by MFA.

```
"Resource": "arn:aws:s3::secretproject/boris/*",
"Condition": { "Null": { "aws:MultiFactorAuthAge"L true } }
```

There can only be one bucket policy on a bucket, but it can have multiple statements. If an identity inside one AWS account is accessing a bucket, also in that same account, then the effective access is a combination of all of the applicable identity policies plus the resource policy (the bucket policy. For access by an anonymous principal, then only the bucket policy applies. If an identity in an external AWS account attempts to access a bucket in your account, your bucket policy applies, as well as anything that's in their identity policies.

Access Control Lists (ACLs) are ways to apply security to objects or buckets. They are a sub-resource of that object or bucket. They are legacy and no longer recommended, with bucket policies or identity policies preferred. They are inflexible and only allow simple permissions, such as read or write. You can either configure ACLs on the bucket, or you configure the ACL on an object, but you can't have a single ACL that affects a group of objects. 

S3 permissions have **Block Public Access** settings. This was added to prevent buckets being configured incorrectly and left open to the world. Block Public Access settings apply no matter what the bucket policies say, but they apply to just the public access. These settings can be set when you create a bucket and adjusted afterwards.

You can:
- Block public access entirely no matter what the resource policy says.
- Allow any public access granted by any existing ACLs but blocks any new ones
- Block any public access granted by ACLs, no matter if it was enabled before or after
- Allow any existing public access granted by bucket policies or access point policies, but block any new ones
- Block both existing and new bucket policies from granting any public access

Exam power up
Use Identity or Resource Policies based on the following:
- Identity - controlling different resources across an account
- Identity - you have a preference for managing permissions in one place - use IAM
- Identity - same account, no external access
- Bucket - just controlling S3
- Bucket - anonymous or cross account
- ACLs - never, unless you must

### S3 Static Website Hosting
Access to S3 is normally via the AWS APIs. S3 static website hosting allows access via HTTP, meaning you can host almost any kind of static website.

When you enable static website hosting you have to set an index document (for the index page) and an error document (for handing errors). You need to point to a specific object (a HTML document) in the S3 bucket. When you enable this feature on a bucket, AWS creates a static website hosting endpoint, a specific address that can be accessed via HTTP. The name of this endpoint is determined by the bucket name and region.

You can set up a custom domain using Route53 but your bucket name still matters. You can only use a custom domain with a bucket if the name of the bucket matches the domain.

There are two scenarios particularly suited to static hosting on S3: offloading and out-of-band pages. Static assets, such as images, can be offloaded to S3, saving on more expensive compute. S3 is custom designed for storing large data at scale. Out of band pages could include maintenance pages while the main server is down.

S3 has per gigabyte monthly costs for storage and data transfer out of S3. Transferring data into S3 is always free. You are charged for requesting data, so every time you get, list etc. Different operations have different costs per 1,000 operations.

### Object Versioning and MFA Delete
Object versioning lets you store multiple versions of an object within a bucket. It is a feature which is controlled at a bucket level. It starts out disabled. Once enabled, you cannot disable it again. You can suspend it on an enabled bucket and, if desired, re-enable it later.

Without versioning enabled on a bucket, each object is identified solely by the object key (its name), which is unique inside the bucket. With versioning, any operations which would modify an object, generate a new version of the object and leave the original in place.

When versioning is disabled, the ids of the objects in that bucket are set to null. With versioning enabled, S3 allocates an id to the object. If an operation modifies the object, S3 allocates a new id to the newer version and retains the old version.

The newest version of any object in versioned bucket is known as the "current version" of that object. If an object is accessed without explicitly specifying which version is required, the current version will always eb returned. You can request an object with a specific id to get that version back.

Versioning also impacts deletions. If you delete an object without providing an id, S3 will create a new special version of that object known as a delete marker. You can delete the delete marker to un-delete the object. 

Even with versioning enabled, you can fully delete a version of an object. You delete an object and specify the particular version id you want to remove. If you delete the current version, then the next most recent version becomes the current version.

Object versioning cannot be switched off, it can only be suspended. Space is consumed by all versions of the objects in the bucket. You are billed for storing all of these versions. The only way to zero those costs out is to delete the bucket and then re-upload all those objects to a bucket without versioning enabled.

MFA delete is enabled within the versioning configuration on a bucket. When enabled, it means that MFA is required to change the bucket's versioning state. MFA would also be required to delete any versions of an object. You need to provide the serial number of your MFA token as well as the code that it generates when making API calls to delete versions or change the versioning state of a bucket.

### S3 Performance Optimization
By default, when you upload an object to S3 it's uploaded as a single blob of data in a single stream. A file becomes an object and it's uploaded using the PutObject API call and placed in a bucket. This all happens as a single stream. If a stream fails, the whole upload fails and the only recovery is a full restart of the entire upload. Speed and reliability is limited by this single stream of data, which is limited to 5GB of data.

Multipart upload improves the speed and reliability of uploads to S3. It does this by breaking data up into individual parts. The minimum size for using multipart upload is 100MB. Most AWS tooling will automatically use it as soon as it becomes available. An upload can be split into a maximum of 10,000 parts with each part between 5MB and 5GB. The last part can be smaller than 5MB. Each individual part is treated as its own isolated upload, and can fail in isolation and be restarted in isolation. The transfer rate of the whole upload is the sum of the individual parts.

S3 Transfer Acceleration uses the network of AWS edge locations to ensure data is transferred to S3 through the AWS global network, spending less time on normal networks. To enable it, the bucket name cannot contain periods and it needs to be DNS-compatible in its naming. 

Data immediately enters the closest, best-performing AWS edge location, and . The edge locations transfer the data over the AWS global network, which is purpose built to link regions to other regions in the AWS network with lower consistent latency. The benefits of transfer acceleration improve the larger the distance between the upload location and the S3 bucket.

### Key Management Service (KMS)
Key Management Service makes is easy to create, store and manage cryptographic keys and control their use across a wide range of AWS services. KMS is a regional and public service. Every region is isolated when using KMS. 

KMS is capable of handling both symmetric and asymmetric keys. It is also capable of performing cryptographic operations, including encryption and decryption. Cryptographic keys never leave KMS and it provides a FIPS 140-2 (Level 2) compliant service.

The main type of keys that KMS manages are known as KMS keys. You might also see them as CMKs (Customer Master Keys) but this naming scheme has been superseded. Think of them as a container for the actual physical key material, the data that makes up the key.

A KMS key contains a key id, a creation date, a key policy (which is a resource policy), a description, and a state of the key. Every KMS key is backed by physical key material. This data is held by KMS and is what is actually used to encrypt and decrypt things that you give to KMS. The physical key material can be generated by KMS or imported into KMS. KMS keys can be used to encrypt or decrypt data up to 4KB in size.

Nothing in KMS is every persisted in plaintext form. Permissions to decrypt are separate from permissions to encrypt and also from permissions which allow for the generation of keys. KMS is very granular with permissions. You need individual permissions for various operations, including encryption and decryption. You need permissions on given KMs keys in order to use those keys.

Data Encryption Keys (DEKs) are another type of key which KMS can generate. They're generated using a KMS key, using the GenerateDataKey operation. This generates a DEK which can be used to encrypt and decrypt data that is more than 4KB in size. DEKs are linked to the KMS key which created them. Importantly, KMS doesn't store the Data Encryption Key in any way. It provides it to you or the service using KMS and then it discards it.

When a Data Encryption Key is generated, KMS provides you with two versions: a plaintext version of that key, which can be used immediately to perform cryptographic operations, and a ciphertext or encrypted version. The DEK is encrypted using the KMS key that generated it. This encrypted key can be given back to KMS for it to be decrypted. 

Usually, you would generate a Data Encryption Key immediately before you want to encrypt something. You would encrypt the data using the plaintext version of the key, and once finished with that process, discard the plaintext version. You would then store the encrypted DEK along with the encrypted data. When you want to decrypt the data, you would pass the encrypted DEK to KMS, decrypt it, and then use the plaintext version to decrypt your data. You would then discard the decrypted DEK.

S3, when using KMS, generates a data encryption key for every single object.

By default, KMS keys are stored within the KMS service in a specific region. They never leave the region or the KMS service. KMS does support multi-region keys if required. Within KMS, keys are either AWS owned or customer owned. With customer owned keys, there are two types: AWS managed and customer managed. AWS managed keys are created automatically by AWS when you use a service like S3. Customer managed keys are created explicitly by the customer to use directly in an application or within an AWS service. Customer managed keys are more configurable, for example you can edit the key policy. Both types of keys support rotation, indeed with AWS managed keys this can't be disabled.

A KMS key contains the backing key, the physical key material, and all previous backing keys caused by rotation. You can create aliases to serve as shortcuts to keys. Aliases are per region, since neither aliases nor keys are global by default.

Many services default to trusting the account they are contained in. KMS is different. This account trust is explicitly added on a key policy or not. Every KMS key has a key policy (a type of resource policy) and for customer managed keys you can change it. Permissions are very granular and can be split based on function. You might be granted rights to create and manage keys but not have permissions to perform cryptographic operations. This way administrators aren't given permission to decrypt data encrypted via KMS.

### S3 Object Encryption CSE/SSE
Buckets aren't encrypted, objects are. You don't define encryption at the bucket level. Each object in a bucket might be using different encryption settings.

With both client side encryption and sever side encryption HTTPS means that data is encrypted in transit. 

With Client Side Encryption, the objects being uploaded are encrypted by the client before they leave for S3. The data is cyphertext the entire time, from client to S3 endpoint to S3 storage.

With Server Side Encryption, the objects themselves aren't initially encrypted. The data reaches S3 in its original form. The data is then encrypted by the S3 servers.

AWS has recently made server side encryption mandatory. You can no longer store objects in an unencrypted form in S3.

There are three types of server side encryption available for S3 objects:
- Server-Side Encryption with Customer-Provided Keys (SSE-C)
- Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3). This is the default.
- Server-Side Encryption with KMS Keys stored in AWS Key Management Service (SSE-KMS)

With SSE-C, the customer is responsible for the keys and S3 manages the encryption and decryption processes and the compute required for these processes. You have to manage the keys but you retain greater control, which is good in some highly regulated environments.

With SSE-S3 (AES256), AWS handles both the encryption processes as well as key generation and management. S3 generates a key for every uploaded object. For extra safety, S3 has a key which it manages as part of the service, which you have no control over. This key is used to encrypt the per-object key and then the original key is discarded. The cyphertext object and cyphertext key are persistently stored on disk.

SSE-S3 presents three major problems:
- it isn't suitable for strongly regulated environments, where you need to control keys and their access
- it doesn't allow you to control the rotation of keys
- it doesn't support role separation (an S3 full administrator can decrypt and view data)

With SSE-KMS, KMS manages keys instead of S3. You create a (usually customer managed) KMS key. This key is fully configurable. When S3 wants to encrypt an object it has to request a new data encryption key from KMS. KMS delivers a plaintext and cyphertext version of the DEK. S3 uses the plaintext DEK to encrypt the object and then stores the encrypted object and cyphertext DEK. You would need access to the KMS key to decrypt the objects stored in S3, providing role separation.


| Method                 | Key Management | Encryption Processing | Extras                                     |
| ---------------------- | -------------- | --------------------- | ------------------------------------------ |
| Client-Side Encryption | You            | You                   | S3 never sees plaintext                    |
| SSE-C                  | You            | S3                    | -                                          |
| SSE-S3                 | S3             | S3                    | AES256. No Key control. No role separation |
| SSE-KMS                | S3 and KMS     | S3                    | Key rotation control. Role separation      |

### S3 Bucket Keys
S3 bucket keys are way to help S3 scale and reduce costs when using KMS encryption.

Normally, the creation of each object's data encryption key in S3 is an API call to KMS. Calls to KMS have a cost and levels where throttling occurs (5,000, 10,000, 50,000 per second across regions).

With bucket keys, instead of the KMS key being used to generate each individual DEK, it is used to generate a time-limited bucket key which is then used to generate DEKs within S3. This offloads the work from KMS to S3. This process is not retroactive. It only affects objects after it has been enabled on a bucket.

After you enable an S3 bucket key, CloudTrail KMS events now show the bucket arn instead of the object arn. Bucket keys work with replication, meaning the object encryption is maintained when an object is replicated. If you are replicating plaintext to a bucket using bucket keys, the object is encrypted at the destination side (the ETAG changes).

### S3 Object Storage Classes
The default object storage class in S3 is **S3 Standard**. Objects are stored across at least 3 Availability Zones in the region. S3 Standard provides 11 9s of durability (for 10,000,000 objects, 1 object would be lost per 10,000 years). The replication uses MD5 checksums and Cyclic Redundancy Checks (CRCs) to detect and fix any data corruption. 

When objects are stored durably, S3 responds with a HTTP/1.1 200 OK status. You are billed a GB/month fee for data stored. A $1 per GB charge for transfer OUT (IN is free) and a price per 1,000 requests. There is no specific retrieval fee, no minimum duration and no maximum size.

S3 Standard is the most balanced class of storage. You don't get any discounts but you also aren't penalized in any way.

S3 Standard makes data available immediately. It has a first byte latency of milliseconds and objects can be made publicly available. 

S3 Standard should be used for frequently accessed data, which is important and non-replaceable. It should be your default and you should only move to other storage classes when you have a specific reason to do so.

**S3 Standard-IA** (Infrequent Access) shares most of the architecture and characteristics of S3-Standard. Data is still replicated over at least three AZs in the region. Availability, durability and first byte latency are the same. 

The basic cost model is the same but the storage costs for this model are much cheaper. It has a new cost component, a retrieval fee where for every GB of data retrieved there is a cost in addition to the transfer fees. Overall cost increases with frequent data access.

There is minimum duration charge of 30+ days for objects. Objects can be stored for less time, but the minimum billing always applies. There is a minimum capacity charge of 128KB per object.

For the exam: S3 Standard-IA should be used for long-lived data which is important but where access is infrequent.

**S3 One Zone-IA** is similar to Standard-IA. It is cheaper but with a significant compromise: data is only stored in one Az within the region. It does not provide the multi-AZ resilience model of Standard or Standard-IA. You still get 11 9s of durability, assuming the AZ never fails.

One Zone-IA has a per GB data retrieval fee and overall cost increase with frequent data access. There is still a minimum 30 day billed storage duration and a 128KB minimum capacity charge per object.

For the exam: S3 One Zone-IA should be used for long-lived data, which is non-critical and replaceable and where access is infrequent.

S3 Glacier - Instant Is like S3 Standard-IA except it offers cheaper storage, more expensive retrieval and a longer minimum duration.


### TODO Other sections

### S3 Events
The S3 event notification feature lets you configure event notifications on a bucket. A notification is generated when a certain thing occurs in a bucket. These notifications can be delivered to different destinations, including SNS, SQS, and Lambda functions. This means you can have event-driven processes that occur as a result of things happening in S3.

Notifications can be sent when objects are created (Put, Post, Copy, CompleteMultiPartUpload), deleted (\*, Delete, DeleteMarkerCreated), restored (Post initiated or completed), replicated (OperationMissedThreshold, OperationReplicatedAfterThreshold, OperationNotTracked, OperationFailedReplication).

You define an event notification config on a bucket. These events, when triggered by changes in the bucket, are sent to Lambdas, SNS Topics, or SQS queues. You need to add resource policies onto each destination service to allow S3 principal access. The events themselves are JSON objects.

S3 event notifications are an older feature and can only support a limited number of things occurring on objects in buckets and can only interact with a limited number of AWS services. EventBridge is an alternative which supports more types of events and integrates with more services.

### S3 Access Logs
Server access logging provides detailed records for the requests that are made to a bucket. Access logging can be enabled via the console UI or via a PUT Bucket logging operation using the CLI or API. It connects a source bucket, on which bucket and object access is logged, and a target bucket, where these logs are stored.

Logging is managed by a system, the S3 Log Delivery Group. This is a best efforts process. Accesses to the source bucket are usually logged in the target bucket within a few hours. You also need to give the S3 Log Delivery Group write access to the target bucket via a bucket ACL.

Logs are delivered as log files with each file consisting of log records. Records are newline-delimited. Each record's attributes, such as date and time or status codes, are space-delimited. A single target bucket can be used for many source buckets. These are separated using prefixes in the target bucket.

Access logging provides detailed information about the requests made to the source bucket. They are helpful for security functions and access audits. You need to manage the lifecycle and deletion of the log files.