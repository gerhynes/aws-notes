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