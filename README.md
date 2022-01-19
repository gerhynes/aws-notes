# AWS Notes

Notes from Exampro's [AWS Certified Cloud Practitioner Certification Course](https://www.exampro.co/clf-c01).

The Cloud Practitioner Exam has 4 domains:

- Domain 1: Cloud Concepts - 26% - 13 questions
- Domain 2: Security and Compliance - 25% - 16-17 questions
- Domain 3: Technology - 33% - 21-22 questions
- Domain 4: Billing and Pricing - 16% - 10-11 questions

You need to know a wide range of AWS services as well as knowing core services in more depth.

A passing grade is approximately 700/1000. AWS uses scaled scoring so aim for higher.

The exam contains 65 questions: 50 scored and 15 unsocred. You can afford to get 15 questions wrong and there is no penalty for wrong questions.

The unscored questions are used to evaluate new questions and determine the appropriate difficulty level.

The exam lasts 90 minutes. The seat time is 120 minutes to give you time to review instructions, let the proctor see your workspace, and read and accept the NDA.

The exam is valid for 36 months before recertification.

## Cloud Concepts

### What is Cloud Computing?

Cloud computing is the practice of using a network of remote servers hosted on the internet to store, manage, and process data, rather than a local server or a personal computer.

**On-Premise**

- You own the servers
- You hire the IT staff
- You own or rent the real-estate
- You take all the risks

**Cloud Providers**

- Someone else owns the servers
- Someone else hires the IT staff
- Someone else owns or rents the real-estate
- You are responsible for configuring cloud services and code, someone else takes care of the rest

### The Evolution of Cloud Hosting

**Dedicated Server**

- One physical machine dedicated to a single business.
- Runs a single web app
- Very expensive, high maintenance, high security

**Virtual Private Server (VPS)**

- One physical machine dedicated to a single business
- The physical machine is virtualized into sub-machines
- Runs multiple web apps
- Better utilization and isolation of resources

**Shared Hosting**

- One physical machine shared by hundreds of businesses
- Relies on most tenants under-utilizing their resources
- Very cheap, limited functionality, poor isolation

**Cloud Hosting**

- Multiple physical machines that act as one system
- The system is abstracted into multiple cloud services
- Flexibile, scalable, secure, cost-effective, high configurability

### What is Amazon?

Amazon has expanded beyond just an e-commerce store into:

- cloud computing (AWS)
- digital streaming (Prime Video, Twitch)
- grocery stores (Whole Foods)
- artificial intelligence
- low-orbit satellites (Kuniper Systems)

### What is AWS?

AWS is a collection of cloud services that can be used together under a single unified API to build a large range of workloads. Since officially launching in 2006, it has become the leading cloud service provider (CSP) in the world.

Simple Queue Services (SQS) was the first AWS services launched for public use in 2004.

Simple Storage Service (S3) was launched in March 2006.

Elastic Compute Cloud (EC2) was launched in August 2006. It is still the most used service in AWS.

By November 2010, all of Amazon.com's retail sites had migrated to AWS.

To support training and skills standardization, AWS began offering a certification programme for computer engineers in April 2013.

### What is a Cloud Service Provider (CSP)?

A Cloud Service Provider is a company which:

- provides multiple cloud services
- those cloud services can be chained together to create cloud architectures
- those cloud services are accessible via a single unified API
- those cloud services use metered billing based on usage
- those cloud services have rich monitoring built in
- those cloud services have an Infrastructure as a Service (IaaS) offering
- those cloud services offer automation via Infrastructure as Code (IaC)

If a company offers multiple cloud services under a single UI but do not meet most of these requirements, it's referred to as a Cloud Platform (for example, Twilio, HashiCorp, Databricks).

### Landscape of CSPs

**Tier-1 (Top Tier)**

Early to market, wide offering, strong synergies between services, well-recognised in the industry: AWS, Azure, GCP, Alibaba Cloud.

**Tier-2 (Mid Tier)**

Backed by well-known tech companies, slow to innovate and turned to specialization: IBM Cloud, Oracle Cloud, Rackspace.

**Tier-3 (Light Tier)**

VPSs turned to offer core IaaS offering. Simple, cost-effective: Vultr, Digital Ocean, Linode.

### Gartner Magic Quadrant for Cloud

Magic Quadrant (MQ) is a series of market research reports published by IT consulting form Gartner that rely on proprietary qualitative data analysis methods to demonstrate market trends, such as direction, maturity and participants. It puts AWS in the lead.

### Common Cloud Services

A CSP can have hundreds of cloud services that are grouped into various types of services. The four most common types of cloud service (the core 4) for IaaS would be:

**Compute**

Imagine having a virtual computer that can run applications, programs and code

**Networking**

Imagine having a virtual network defining internet connections or network isolations between services or outbound to the internet

**Storage**

Imagine having a virtual hard-drive that can store files

**Databases**

Imagine a virtual database for storing reporting data or a database for general purpose web applications

AWS has 200+ cloud services.

### AWS Technology Overview

- Compute - EC2 Virtual Machines

- Networking - VPC Private Cloud Network

- Storage - EBS Virtual Hard Drives

- Databases - RDS SQL Databases

- Analytics

- Application Integration

- AR and VR

- AWS Cost Management

- Blockchain

- Business Applications

- Containers

- Customer Engagement

- Developer Tools

- End User Computing

- Game Tech

- Internet of Things

- Machine Learning

- Management and Governance

- Media Services

- Migration and Transfer

- Mobile

- Quantum Technologies

- Robotics

- Satellites

- Security, Identity and Compliance

### Evolution of Computing

**Dedicated**

- A physical server wholly utilized by a single customer
- You have to guess your capacity
- You'll overpay for an underutilized server
- You can't vertically scale, you need a manual migration
- Replacing a server is very difficult
- You are limited by the host operating system
- Multiple apps can result in conflicts in resource sharing
- Technically, you have a guarantee of security, privacy and full utility of the underlying resources

**Virtual Machines**

- You can run multiple virtual machines on one machine
- Hypervisor is the software layer that lets you run the VMs
- A physical server shared by multiple customers
- You pay for a fraction of the server
- You'll overpay for an underutilized VM
- You are limited by the guest operating system
- Multiple apps on a single VM can result in conflicts in resource sharing
- Easier to export or import images for migration
- Easier to vertically or horizontally scale

**Containers**

- Virtual machine running multiple containers
- Docker Daemon is the software layer that lets you run multiple containers
- You can maximize the utilization of the available capacity, which is more cost-effective
- Your containers share the same underlying OS so containers are more efficient thatn multiple VMs
- Multiple apps can run side by side without being limited to the same OS requirements and will not cause conflicts during resource sharing.

**Functions**

- Managed VMs running managed containers
- Known as Serverless Compute
- You upload a piece of code, choose the amount of memery and duration
- You're only responsible for code and data, nothing else
- Very cost-effective, you only pay for the time the code is running. VMs only run when there is code to be executed.
- Cold Starts are a side-effect of this setup

### Types of Cloud Computing

**Saas** (Software as a service)

A product that is run and managed by a service provider. You don't worry about how the service is maintained. It just works and remains available.

**PaaS** (Platform as a Service)

Fosued on the deployment and management of your apps. You don't worry about provisioning, configuring or understanding the hardware or OS.

**IaaS** (Infrastructure as a Service)

The basic building blocks for Cloud IT. Provides access to networking features, computers and data storage space. You don't worry about IT staff, data centres and hardware.

### Cloud Computing Deployment Models

**Public Cloud**

Everything (the workload or project) is built on the CSP. Also known as Cloud-Native or Cloud-First.

**Private Cloud**

Everything is built on a company's datacentres. Also known as On-Premise. The cloud could be OpenStack.

**Hybrid**

Using both On-Premise and a Cloud Service Provider.

**Cross Cloud**

Using multiple Cloud Service Providers. Also known as multi-cloud

### Deployment Model Use Cases

**Cloud**

Companies that are starting out today, or are small enough to make the leap from a VPS to a CSP.

- Startups
- SaaS offerings
- New projects and companies

**Hybrid**

Organizations that started with their own datacentre, can't fully move to cloud due to the effort of migration or security compliance.

- Banks
- finTech, Investment Management
- Large professional service providers
- Legacy on-premise

**On-Premise / Private Cloud**

Organizations that cannot run on cloud due to strict regulatory compliance or the sheer size of their organization.

- Public Sector, Government
- Super Sensitive Data, Hospitals
- Large enterprises with heavy regulation, Insurance Companies

There isn't really a good reason to be wholly on-premise.

### AWS Free Tier

AWS makes a free tier available for the first 12 months of a new AWS account. The are limitations to which services, and how much of them, are available on the free tier.

You can set up alerts in the Billing Management Console to warn you if you are approaching free tier limits.

### Innovation Waves

Kondratiev Waves are hypothesized cycle-like phenomena in the global world economy, closely linked to technology life cycles. Each wave irreversibly changes society on a global scale. Cloud technology is arguably the latest wave.

### Burning Platform

Burning platform is a term used when a company abandons old technology for new technology, with an uncertainty of success. It can be motivated by fear that the organization's future survival hinges on its digital transformation.

### Evolution of Computing Power

Computing power is the throughput measured at which a computer can complete a computational task. We're not done with it by any means.

GPU computing is approximately 50x faster than traditional CPUs.

Quantum Computing is 100 million times faster than traditional CPUs.

In these 3 categories would be AWS's Elastic Compute Cloud (EC2), AWS Inferentiare (Inf1), and AWS Bracket (via CalTech).

### The Benefits of Cloud

Originally the Six Advantages of Cloud.

- Agility
- Pay-as-you-go pricing
- Economies of scale
- Global reach
- Security
- Reliability
- High Availability
- Scalability
- Elasticity
- Fault Tolerance
- Disaster Recovery

### The Six Advantages of Cloud

1. Trade capital expense for variable expense

You can pay on-demand, meaning there's no upfront cost and you pay for only what you consume or by the hour, minute, second.

2. Benefit from massive economies of scale

You are sharing the cost with other customers to get unbeatable savings.

3. Stop guessing capacity

Scale up or down to meet the current need. Launch and destroy services whenever.

4. Increase speed and agility

Launch resources in minutes with a few clicks

5. Stop spending money on running and maintaining data centers

Focus on your own customers and developing your own applications.

6. Go global in minutes

Deploy your app in multiple regions around the world with a few clicks, providing low latency and a better experience for your customers.

### Seven Advantages to Cloud

**Cost-efective**

You pay for what you consume, no up-front cost.

**Global**

Launch workloads anywhere in the world, just choose a region.

**Secure**

Cloud providers take care of physical security and cloud services can be secure by default.

**Reliable**

Data backup, disaster recovery, data replication and fault tolerance.

**Scalable**

Increase or decrease resources and services based on demand.

**Elastic**

Automate scaling during spikes and drop in demand

**Current**

The underlying hardware and managed software is patched, upgraded and replaced by the cloud provider without interruption to you.

### AWS Global Infrastrcture Overview

The AWS global infrastructure is globally distributed hardware and data centers that are physically networked together to act as one large resource for the end customer. It is (currently) made up of:

- 25 launched regions
- 81 availability zones
- 108 direct connection locations
- 275+ points of presence
- 11 local zones
- 17 wavelength zones

### Regions

Regions are geographically distinct locations consisting of one or more Availability Zones.

Every region is physically isolated from and independent of every other region in terms of location, power and water supply.

US-East 1 (Northern Virginia) was AWS's first region.

Each region generally has three Availability Zones.

New services almost always become available first in US-East.

Not all AWS services are available in all regions.

Al your billing information appears in US-East 1.

The costs of AWS services vary per region.

When you choose a region you need to consider four factors:

1. What regulatory compliance does this region meet?

2. What is the cost of AWS services in this region?

3. What AWS services are available in this region?

4. What is the distance or latency to end-users?

### Regional vs Global Services

**Regional Services**

AWS scopes their AWS Management Console on a selected Region. This will determine where an AWS service will be launched and what will be seen within an AWS service's console.

**Global Services**

Some AWS services operate across multiple regions and the region will be fixed to "Global", for example S3, CloudFront, Route53, IAM.

For these global services, at the time of creation:

- There is no concept of region, for example an IAM user
- A single region must be explicitly chosen, for example an S3 buckaet
- A group of regions are chosen, for example CloudFront Distributed

### Availibility Zones (AZs)

An Availability Zone (AZ) is a physcial location made up of one or more data centres, securely containing hundreds or thousands of computers.

A region will \*generally contain 3 Availability Zones.

Data centres within a region will be isolated from each other (different buildings). But they will be close enough to provide low latency (within 100km and < 10ms latency).

All traffic between AZs is encrypted.

It's common practice to run workloads in at least 3 AZs to ensure services remain available in case one or two data centres fail (high availability).

AZs are represented by a region code and letter, for example us-east-1a.

You never chose an AZ when launching resources. You chose the Subnet which is associated to the AZ.

US-EAST-1 has 6 AZs, the most AZs of any region.

Some services, such as EC2, are regional and require you to select a subnet and AZ. Others, such as S3, are global.

### Fault Tolerance

A fault domain is a section of a network that is vulnerable to damage if a critical device or system fails. The purpose of a fault domain is that if a failure occurs it will not cascade outside that domain, limiting the possible damage.

You can have fault domains nested inside fault domains.

A fault level is a collection of fault domains.

An AWS Region would be a Fault Level.

An Availability Zone would be a Fault Domain.

The scope of a fault domain could be:

- specific servers in a rack
- an entire rack in a data center
- an entire room in a data center
- the entire data center building

It's up to the CSP to determine the boundaries of a domain.

Each Amazon Region is designed to be completely isolated from the other Amazon Regions. This achieves the greatest possible fault tolerance and stability.

Each Availability Zone is isolated, but the Availability Zones in a Region are connected through low-latency links.

Each Availability Zone is designed to be an independent failure zone (fault domain).

**Failure Zone**

- AZs are physically seperated within a typical metropolitan region and are located in lower risk flood plains
- discrete uninterruptable power supply (UPS) and onsite backup generation facilities
- data centers located in different AZs are designed to be supplied by independent substations to reduce the risk of an event on the power grid impacting more than one AZ
- AZs are all redundantly connected to multiple tier-1 transit providers

**Multi-AZ for High Availability**

If an application is partitioned across AZs, companies are better isolated and protected from issues such as power outages, lightning strikes, tornadoes, earthquakes and more.
