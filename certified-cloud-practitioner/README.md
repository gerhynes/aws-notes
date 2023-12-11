# AWS Certified Cloud Practitioner Notes

Sources:
- [AWS Certified Cloud Practitioner Certification Course](https://www.exampro.co/clf-c01).

The Cloud Practitioner Exam has 4 domains:

- Domain 1: Cloud Concepts - 26% - 13 questions
- Domain 2: Security and Compliance - 25% - 16-17 questions
- Domain 3: Technology - 33% - 21-22 questions
- Domain 4: Billing and Pricing - 16% - 10-11 questions

You need to know a wide range of AWS services as well as knowing core services in more depth.

A passing grade is approximately 700/1000. AWS uses scaled scoring so aim for higher.

The exam contains 65 questions: 50 scored and 15 unscored. You can afford to get 15 questions wrong and there is no penalty for wrong questions.

The unscored questions are used to evaluate new questions and determine the appropriate difficulty level.

The exam lasts 90 minutes. The seat time is 120 minutes to give you time to review instructions, let the proctor see your workspace, and read and accept the NDA.

The exam is valid for 36 months before recertification.

## Cloud Concepts
### What is Cloud Computing?
Cloud computing is the practice of using a network of remote servers hosted on the internet to store, manage, and process data, rather than a local server or a personal computer.

#### On-Premise
- You own the servers
- You hire the IT staff
- You own or rent the real-estate
- You take all the risks

#### Cloud Providers
- Someone else owns the servers
- Someone else hires the IT staff
- Someone else owns or rents the real-estate
- You are responsible for configuring cloud services and code, someone else takes care of the rest

### The Evolution of Cloud Hosting
#### Dedicated Server
- One physical machine dedicated to a single business.
- Runs a single web app
- Very expensive, high maintenance, high security

#### Virtual Private Server (VPS)
- One physical machine dedicated to a single business
- The physical machine is virtualized into sub-machines
- Runs multiple web apps
- Better utilization and isolation of resources

#### Shared Hosting
- One physical machine shared by hundreds of businesses
- Relies on most tenants under-utilizing their resources
- Very cheap, limited functionality, poor isolation

#### Cloud Hosting
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

**Simple Queue Service** (SQS) was the first AWS services launched for public use in 2004.

**Simple Storage Service** (S3) was launched in March 2006.

**Elastic Compute Cloud** (EC2) was launched in August 2006. It is still the most used service in AWS.

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
#### Tier-1 (Top Tier)
Early to market, wide offering, strong synergies between services, well-recognised in the industry: AWS, Azure, GCP, Alibaba Cloud.

#### Tier-2 (Mid Tier)
Backed by well-known tech companies, slow to innovate and turned to specialization: IBM Cloud, Oracle Cloud, Rackspace (OpenStack).

#### Tier-3 (Light Tier)
VPSs turned to offer core IaaS offering. Simple, cost-effective: Vultr, Digital Ocean, Linode.

### Gartner Magic Quadrant for Cloud
Magic Quadrant (MQ) is a series of market research reports published by IT consulting form Gartner that rely on proprietary qualitative data analysis methods to demonstrate market trends, such as direction, maturity and participants. It puts AWS in the lead.

### Common Cloud Services
A CSP can have hundreds of cloud services that are grouped into various types of services. The four most common types of cloud service (the core 4) for IaaS would be:

#### Compute
Imagine having a virtual computer that can run applications, programs and code

#### Networking
Imagine having a virtual network defining internet connections or network isolations between services or outbound to the internet

#### Storage
Imagine having a virtual hard-drive that can store files

#### Databases
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
#### Dedicated
- A physical server wholly utilized by a single customer
- You have to guess your capacity
- You'll overpay for an underutilized server
- You can't vertically scale, you need a manual migration
- Replacing a server is very difficult
- You are limited by the host operating system
- Multiple apps can result in conflicts in resource sharing
- Technically, you have a guarantee of security, privacy and full utility of the underlying resources

#### Virtual Machines
- You can run multiple virtual machines on one machine
- Hypervisor is the software layer that lets you run the VMs
- A physical server shared by multiple customers
- You pay for a fraction of the server
- You'll overpay for an underutilized VM
- You are limited by the guest operating system
- Multiple apps on a single VM can result in conflicts in resource sharing
- Easier to export or import images for migration
- Easier to vertically or horizontally scale

#### Containers
- Virtual machine running multiple containers
- Docker Daemon is the software layer that lets you run multiple containers
- You can maximize the utilization of the available capacity, which is more cost-effective
- Your containers share the same underlying OS so containers are more efficient than multiple VMs
- Multiple apps can run side by side without being limited to the same OS requirements and will not cause conflicts during resource sharing.

#### Functions
- Managed VMs running managed containers
- Known as Serverless Compute
- You upload a piece of code, choose the amount of memory and duration
- You're only responsible for code and data, nothing else
- Very cost-effective, you only pay for the time the code is running. VMs only run when there is code to be executed.
- Cold Starts are a side-effect of this setup

### Types of Cloud Computing
#### Saas (Software as a service)
A product that is run and managed by a service provider. You don't worry about how the service is maintained. It just works and remains available.

#### PaaS (Platform as a Service)
Fosued on the deployment and management of your apps. You don't worry about provisioning, configuring or understanding the hardware or OS.

#### IaaS (Infrastructure as a Service)
The basic building blocks for Cloud IT. Provides access to networking features, computers and data storage space. You don't worry about IT staff, data centres and hardware.

### Cloud Computing Deployment Models
#### Public Cloud
Everything (the workload or project) is built on the CSP. Also known as Cloud-Native or Cloud-First.

#### Private Cloud
Everything is built on a company's datacentres. Also known as On-Premise. The cloud could be OpenStack.

#### Hybrid
Using both On-Premise and a Cloud Service Provider.

#### Cross Cloud
Using multiple Cloud Service Providers. Also known as multi-cloud.

### Deployment Model Use Cases
#### Cloud
Companies that are starting out today, or are small enough to make the leap from a VPS to a CSP.

- Startups
- SaaS offerings
- New projects and companies

#### Hybrid
Organizations that started with their own data center, can't fully move to cloud due to the effort of migration or security compliance.

- Banks
- finTech, Investment Management
- Large professional service providers
- Legacy on-premise

#### On-Premise / Private Cloud
Organizations that cannot run on cloud due to strict regulatory compliance or the sheer size of their organization.

- Public Sector, Government
- Super Sensitive Data, Hospitals
- Large enterprises with heavy regulation, Insurance Companies

There isn't really a good reason to be wholly on-premise any more.

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
1. **Trade capital expense for variable expense**

You can pay on-demand, meaning there's no upfront cost and you pay for only what you consume or by the hour, minute, second.

2. **Benefit from massive economies of scale**

You are sharing the cost with other customers to get unbeatable savings.

3. **Stop guessing capacity**

Scale up or down to meet the current need. Launch and destroy services whenever.

4. **Increase speed and agility**

Launch resources in minutes with a few clicks

5. **Stop spending money on running and maintaining data centers**

Focus on your own customers and developing your own applications.

6. **Go global in minutes**

Deploy your app in multiple regions around the world with a few clicks, providing low latency and a better experience for your customers.

### Seven Advantages to Cloud
#### Cost-efective
You pay for what you consume, no up-front cost.

#### Global
Launch workloads anywhere in the world, just choose a region.

#### Secure
Cloud providers take care of physical security and cloud services can be secure by default.

#### Reliable
Data backup, disaster recovery, data replication, and fault tolerance.

#### Scalable
Increase or decrease resources and services based on demand.

#### Elastic
Automate scaling during spikes and drop in demand

#### Current
The underlying hardware and managed software is patched, upgraded and replaced by the cloud provider without interruption to you.

## AWS Global Infrastructure
The **AWS Global Infrastructure** is globally distributed hardware and data centers that are physically networked together to act as one large resource for the end customer. It is (currently) made up of:

- 25 launched regions
- 81 availability zones
- 108 direct connection locations
- 275+ points of presence
- 11 local zones
- 17 wavelength zones

### Regions
**Regions** are geographically distinct locations consisting of one or more **Availability Zones**.

Every region is physically isolated from and independent of every other region in terms of location, power and water supply.

US-East 1 (Northern Virginia) was AWS's first region.

Each region generally has three Availability Zones.

New services almost always become available first in US-East.

Not all AWS services are available in all regions.

All your billing information appears in US-East 1.

The costs of AWS services vary per region.

When you choose a region you need to consider four factors:

1. What regulatory compliance does this region meet?
2. What is the cost of AWS services in this region?
3. What AWS services are available in this region?
4. What is the distance or latency to end-users?

### Regional vs Global Services
#### Regional Services
AWS scopes their AWS Management Console on a selected Region. This will determine where an AWS service will be launched and what will be seen within an AWS service's console.

#### Global Services
Some AWS services operate across multiple regions and the region will be fixed to "Global", for example S3, CloudFront, Route53, IAM.

For these global services, at the time of creation:

- There is no concept of region, for example an IAM user
- A single region must be explicitly chosen, for example an S3 buckaet
- A group of regions are chosen, for example CloudFront Distributed

### Availibility Zones (AZs)
An **Availability Zone** (AZ) is a physical location made up of one or more data centres, securely containing hundreds or thousands of computers.

A region will \*generally contain 3 Availability Zones.

Data centers within a region will be isolated from each other (different buildings). But they will be close enough to provide low latency (within 100km and < 10ms latency).

All traffic between AZs is encrypted.

It's common practice to run workloads in at least 3 AZs to ensure services remain available in case one or two data centres fail (high availability).

AZs are represented by a region code and letter, for example us-east-1a.

You never choose an AZ when launching resources. You chose the Subnet which is associated to the AZ.

US-EAST-1 has 6 AZs, the most AZs of any region.

Some services, such as EC2, are regional and require you to select a subnet and AZ. Others, such as S3, are global.

### Fault Tolerance
A **Fault Domain** is a section of a network that is vulnerable to damage if a critical device or system fails. The purpose of a fault domain is that if a failure occurs it will not cascade outside that domain, limiting the possible damage.

You can have fault domains nested inside fault domains.

A **Fault Level** is a collection of fault domains.

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

#### Failure Zone
- AZs are physically seperated within a typical metropolitan region and are located in lower risk flood plains
- discrete uninterruptable power supply (UPS) and onsite backup generation facilities
- data centers located in different AZs are designed to be supplied by independent substations to reduce the risk of an event on the power grid impacting more than one AZ
- AZs are all redundantly connected to multiple tier-1 transit providers

#### Multi-AZ for High Availability
If an application is partitioned across AZs, companies are better isolated and protected from issues such as power outages, lightning strikes, tornadoes, earthquakes and more.

### AWS Global Network
The **AWS Global Network** represents the interconnections between AWS Global Infrastructure. It's commonly referred to as "the Backbone of AWS". Think of it as a private expressway, where things can move fast between datacenters.

**Edge Locations** act as on and off ramps to the AWS Global Network.

**AWS Global Accelerator** and **AWS S3 Transfer Acceleration** use edge locations as an on-ramp to quickly reach AWS resources in other regions by traversing the fast AWS Global Network.

**Amazon CloudFront** (CDN) uses edge locations as an off-ramp to provide at-the-Edge storage and compute near the end user.

**VPC Endpoints** ensure your resources stay within the AWS Network and do not traverse over the public internet.

### Points of Presence (PoP)
**Points of Presence** (PoP) are intermediate locations between an AWS Region and the end user. This location could be a datacenter or a collection of hardware.

For AWS, a Point of Presence is a datacenter owned by AWS or a trusted partner that is utilized by AWS Services related to content delivery or expediated upload.

PoP resources are:
- Edge Locations
- Regional Edge Caches

Edge Locations are datacenters that hold cached copies of the most popular files (for example, web pages, images and videos) so that the delivery distances to the end user are reduced.

**Regional Edge Locations** are datacenters that hold much larger caches of less-popular files to reduce a full round trip and also to reduce the cost of transfer fees.

### Tier 1
PoPs live at the intersection of two networks. A Tier 1 network is a network that can reach every other network on the internet without purchasing IP transit or paying for peering.

AWS Availability Zones are redundantly connected to multiple Tier 1 transit providers.

### AWS Services using PoPs
The following AWS Services use PoPs for content delivery or expediated upload:

**Amazon Cloudfront** is a CDN where:
- You point your website to CloudFront so that it will route request to the nearest Edge Location cache
- It allows you to choose an origin (such as a web server or storage) for the cache source
- It caches the content of what the origin would return to various Edge Locations around the world

**Amazon S3 Transfer Acceleration** allows you to generate a URL that can be used by end users to upload files to a nearby Edge Location. Once a file is uploaded to an Edge Location, it can move much faster within the AWS Network to reach S3.

**AWS Global Accelerator** can find the optimal path from the end user to your web servers. These are deployed within Edge Locations  so you send user traffic to an Edge Location instead of directly to your web app.

### AWS Direct Connect
**AWS Direct Connect** is a private/dedicated connection between your datacenter, office, co-location and AWS.

Direct Connect has two very fast network connection options.
1. Lower bandwidth 50 MBps - 500 MBps
2. Higher bandwidth 1GBps - 10GBps

This helps reduce network costs and increase bandwidth throughput (great for high traffic networks).

It provides a more consistent network experience than a typical internet-based connection (more reliable and secure).

A co-location (aka carrier-hotel) is a data center where equipment, space and bandwidth are available for rental to retail customers.

### Direct Connect Locations
**Direct Connect Locations** are trusted partner data centers where you can establish a dedicated, high-speed, low-latency connection from your on-premise to AWS.

You would use the AWS Direct Connect service to order and establish a connection.

### AWS Local Zones
**Local Zones** are data centers located very close to a densely populated area to provide single-digit millisecond latency (~7ms) for that area.

Los Angeles was the first Local Zone deployed. It is a logical extension of the US_Westm Region. The identifier has the format: `us-west-2-lax-1a`.

Only specific AWS services (such as EC2, EBS, and Amazon VPC) have been made available on Local Zones.

The purpose of Local Zones is to support highly-demanding applications sensitive to latencies:
- Media and entertainment
- Electronic design automation
- Ad-tech
- Machine Learning

To use Local Zones, you need to opt in.

### Wavelength Zones
**AWS Wavelength Zones** allow for edge-computing on 5G Networks. Applications will have ultra low-latency, being as close as possible to users.

AWS has partnered with various telecom companies to use their 5G networks.

You create a Subnet tied to a Wavelength Zone and then you can launch Virtual Machines to the edge of the targeted 5G networks.

### Data Residency
**Data Residency** is the physical location of where an organization or cloud resources reside.

**Compliance Boundaries** are a regulatory compliance (legal requirement) by a government or organization that describes where data and cloud resources are allowed to reside.

**Data Sovereignity** is the jurisdictional control or legal authority that can be asserted over data because its physical location is within jurisdictional boundaries.

For workloads that need to meet compliance boundaries strictly defining the data residency of data or cloud resources in AWS you can use:

- **AWS Outposts** - a physical rack of servers that you can put in your data center. Your data will reside wherever the outpost physically resides.
- **AWS Config** - a policy as code service. You can create rules to continuously check AWS resource configurations. If they deviate from your expectations you are alerted, or in some cases AWS Config can auto-remediate.
- **IAM Policies** can be written to explicitly deny access to specific AWS regions. A **Service Control Policy** (SCP) is a set of permissions applied organization-wide.

### AWS for Government
The public sector includes public goods and governmental services such as:
- military
- law enforcement
- infrastructure
- public transit
- public education
- healthcare
- the government itself

AWS can be utilized by public sector organizations developing cloud workloads for the public sector.

AWS achieves this by meeting regulatory compliance programs along with specific governance and security controls, such as HIPAA, FedRAMP, CJIS and FIPS.

AWS has special regions for US regulation called **GovCloud**.

### GovCloud
The Federal Risk and Authorization Management Program (FedRAMP) is a US government-wide program that provides a standardized approach to security assessment, authorization, and continuous monitoring for cloud products and services.

A Cloud Service Provider will generally offer an isolated region (GovCloud) to run FedRAMP workloads.

AWS GovCloud Regions allow customers to host sensitive controlled unclassified information and other types of regulated workloads.

GovCloud Regions are only operated by employees who are US citizens, on US soil. They are only accessible to US entities and root account holders who pass a screening process. Customers can architect cloud solutions that comply with government security requirements.

### AWS in China 
AWS China is the AWS cloud offering in mainland China. It is intentionally completely isolated from AWS Global to meet regulatory compliance for mainland China and is on its own domain amazonaws.cn.

In order to operate in an AWS China Region you need to have a Chinese Business Licence (ICP licence). Not all services are available in China (such as Route53).

Running in mainland China means you do not need to traverse the Great Firewall.

AWS has two regions in mainland China:
- Ningxia CN-NorthWest-1, operated by NSWCF
- Beijing CN-North-1, operated by SINNET

### Sustainability
Amazon co-founded the Climate Pledge to achieve net-zero carbon emissions by 2040 across all of Amazon's businesses, including AWS.

AWS Cloud's sustainability goals are composed of three parts:
1. **Renewable Energy** - AWS is working towards having their Global Infrastructure powered by 100% renewable energy by 2025.
2. **Cloud Efficiency** - AWS's infrastructure is 3.6 times more energy efficient than the median of US enterprise data centers surveyed.
3. **Water Stewardship**
	- Direct evaporative technology is used to cool data centers
	- Recycled non-potable water is used for cooling
	- On-site water treatment allows for more reuse cycles
	- Water efficiency metrics determine and monitor optimal water use for each AWS Region

AWS purchases and retires environmental attributes to cover the non-renewable ebergy for AWS Global Infrastructure:
- Renewable Energy Credits
- Guarantees of Origin

### AWS Ground Station
AWS Ground Station is a fully managed service that lets you control satellite communications, process data, and scale your operations without having to worry about building or managing your own ground station infrastructure.

Use cases for Ground Station include:
- weather forecasting
- surface imaging
- communications
- video broadcasts

To use Ground Station:
- You schedule a Contact (select satellite, start and end times, and the ground location)
- Use the AWS Ground Station EC2 AMI to launch EC2 instances that will uplink and downlink data during the contact or receive downlinked data in an Amazon S3 bucket

Example use case: A company reaches an agreement with a Satellite Image Provider to take satellite photos of a specific region. They use AWS Ground Station to communicate with that satellite and download image data to S3.

### AWS Outposts
**AWS Outposts** is a fully managed service that offers the same AWS infrastructure, AWS services, APIs, and tools to virtually any data center, co-location space, or on-premises facility for a truly consistent hybrid experience.

An AWS Outpost is a rack of servers running AWS infrastructure in your physical location.

A **Server Rack** is a frame designed to hold and organize IT equipment. The industry standard rack size is 48U (7 foot rack). U stands for "rack units" or "U spaces" which is equal to 1.75 inches.

A full-size rack cage is 42U high. Equipment is typically sized 1U, 2U, 3U or 4U high. 

AWS Outposts come in three form factors: 42U, 1U and 2U.

42U is a full rack of servers provided by AWS. It's delivered to your preferred physical location fully assembled and ready to be rolled into final position. It's installed by AWS and the rack just needs to be plugged into power and network.

1U and 2U are servers that you can place into your existing racks.

1U:
- suitable for 19-inch wide / 24 inch deep cabinets
- uses Amazon Graviton2 (up to 64 vCPUs)
- 128 GB memory
- 4 TB local NVMe storage

2U:
- suitable for 19-inch wide / 36 inch deep cabinets
- uses Intel processor (up to 128 vCPUs)
- 256 GB memory
- 8 TB local NVMe storage

## Cloud Architecture
### Cloud Architecture Terminologies
**Solutions Architect** - a role in a technical organization that architects a technical solution using multiple systems via researching, documentation, experimentation.

Cloud Aerchitect - a solutions architect that is focused solely on architecting technical solutions using cloud services.

A cloud architect needs to understand the following terms and factor them into their designed architecture based on the business requirements.
- **Availability** - Your ability to ensure a service remains available. Highly Available (HA)
- **Scalability** - Your ability to grow rapidly or unimpeded
- **Elasticity** - Your ability to shrink and grow to meet demand
- **Fault Tolerance** - Your ability to prevent a failure
- **Disaster Recovery** - Your ability to recover from a failure. Highly Durable (HD)

A solutions architect also needs to always consider the following business factors:
- **Security** - How secure is this solution?
- **Cost** - How much is this going to cost?

### High Availability
**High Availability** is your ability for your service to remain available, by ensuring there is **no single point of failure**, and/or ensure a certain level of performance.

Running your workload across multiple Availability Zones ensures that if 1 or 2 AZs become unavailable your service/applications remain available.

**Elastic Load Balancer** allows you to evenly distribute traffic to multiple servers in one or more data centers. If a data center or server becomes unavailable/unhealthy, the load balancer will route the traffic to available data centers/servers.

### High Scalability
**High Scalability** is your ability to increase your capacity based on the increasing demands of traffic, memory and computing power.

Vertical scaling (scaling up) involves upgrading to a bigger server.

Horizontal scaling (scaling out) involves adding more servers of the same size. This also improves availability.

### High elasticity
High Elasticity is your ability to **automatically** increase or decrease your capacity based on the current demands of traffic, memory and computing power.

Just as scaling out means adding more servers of the same size, scaling in means removing underutilized servers of the same size.

Vertical scaling is generally hard for traditional architecture, so you'll usually only see horizontal scaling described with elasticity.

Auto Scaling Groups (ASG) is an AWS feature that will automatically add or remove servers based on scaling rules you define based on metrics.

### Fault Tolerance
**Fault Tolerance** is your ability for your service to ensure there is no single point of failure, preventing the chance of failure.

**Fail-overs** is when you have a plan to shift traffic to a redundant system in case the primary system fails.

A comon example is having a secondary copy of your database where all ongoing changes are synced. The secondary system is not in use until a fail over occurs and it becomes the primary database.

**RDS Multi-AZ** is when you run a duplicate standby database in another Availability Zone in case your primary database fails.

### High Durability
**High Durability** is your ability to recover from a disaster and to prevent the loss of data. Solutions that recover from a disaster are known as **Disaster Recover** (DR).
- Do you have a backup?
- How fast can you restore that backup?
- Does your backup still work?
- How do you ensure current live data is not corrupt?

**CloudEndure Disaster Recovery** continuously replicates your machines into a low-cost staging area in your target AWS account and preferred Region enabling fast and reliable recovery in case of data center failures.

### Business Continuity Plan
A **Business Continuity Plan** (BCP) is a document that outlines how a business wil continue operating during an unplanned disruption of services.

**Recovery Point Objective** (RPO) is the maximum acceptable amount of data loss after an unplanned data loss incident, expressed as an amount of time. How much data are you willing to lose?

**Recovery Time Objective** (RTO) is the maximum amount of downtime your business can tolerate without incurring a significant financial loss. How much time are you willing to go down?

### Disaster Recovery Options
There are multiple options for recovery that trade cost vs time to recover.
- Backup and restore - You backup your data and restore it to new infrastructure 
	- RPO/RTO - Hours
	- Lower priority use cases
	- Deploy resources after event
	- Very cost effective
- Pilot Light - Data is replicated to another region with the minimal services running
	- RPO/RTO - 10 Minutes
	- Less stringent RTO and RPO
	- Core services
	- Start and scale resources after event
	- A little more expensive
- Warm Standby - Scaled down copy of your infrastructure running, ready to scale up
	- RPO/RTO - Minutes
	- Business critical services
	- Scale resources after event
	- More expensive
- Multi-site Active - Scaled up copy of your infrastructure in another region
	- RPO/RTO - Real-time
	- Zero downtime
	- Near zero loss
	- Mission critical services
	- As expensive as your original infrastructure

### Recovery Time Objective
**Recovery Time Objective** (RTO) is the maximum acceptable delay between the interruption and restoration of service. This objective determines what is considered an acceptable time window when service is unavailable, and is defined by the organization.

### Recovery Point Objective
**Recovery Point Objective** (RPO) is the maximum acceptable amount of time since the last data recovery point. This objective determines what is considered an acceptable loss of data between the last recovery point and the interruption of service, and is defined by the organization.

## Management and Development Tools
### AWS API
An API is software that allows two applications/services to talk to each other. The most common type of API is via HTTP/S requests.

AWS API is a HTTP API that you can interact with by sending requests from an application such as Postman.

Each AWS service has its own service endpoint which you send requests to, with the format `SERVICE_CODE.REGION_CODE.amazonaws.com`.

To authorize use, you will need to generate a signed request. You make a seperate request with your AWS credentials and get back a token.

You also need to provide an **action** and accompanying **parameters** as the payload.

User rarely send HTTP requests directly to the AWS API. It's much easier to interact with the API via developer tools, such as:
- AWS Management Console - a web interface
- AWS SDK - Interact with the API using your preferred programming language
- AWS CLI - Interact with the API from the command line

### AWS Management Console
The AWS Management Console is a web-based unified console, located at console.aws.amazon.com, that allows you to build, manage and monitor everything from simple web apps to complex cloud deployments.

The console allows you to point and click to manually launch and configure AWS resources with limited programming knowledge. This is know as **ClickOps** since you perform all your system operations via clicks.

### Service Console
AWS services each have their own customized console. You can access these consoles by searching the service name. 

Some AWS service consoles will act as an umbrella console containing many AWS services (especailly if they are tightly coupled):
- VPC Console
- EC2 Console
- Systems Manager Console
- SageMaker Console
- CloudWatch Console

### AWS Account ID
Every AWS account has a unique **Account ID**. The Account ID can be easily found by dropping down the current user in the Global Navigation.

The AWS Account ID is composed of 12 digits.

The AWS Account ID is used:
- when logging in with a non-root user account
- for cross-account roles
- for support cases

It's generally good to keep your Account ID private as it is one of many components used to identify an account for attack by a malicious actor.

### AWS Tools for PowerShell
PowerShell is a task automation and configuration management framework, a command-line shell, and a scripting language. 

Unlike most shells, which accept and return text, PowerShell is built on top of the .NET Common Language Runtime (CLR), and accepts and returns .NET objects.

AWS Tools for PowerShell lets you interact with the AWS API  via PowerShell Cmdlets. Cmdlet is a special type of command in PowerShell in the form of capitalized verb-and-noun, for example `New-S3Bucket`.

### Amazon Resource Name (ARN)
Amazon Resource Names (ARNs) uniquely identify AWS resources. ARNs are required to specify a resource unambiguously across all of AWS.

The ARN has the following format variations:
- `arn:partition:service:region:account-id:resource-id`
- `arn:partition:service:region:account-id:resource-type/resource-id`
- `arn:partition:service:region:account-id:resource-type:resource-id`

The partition can be:
- `aws` - AWS regions
- `aws-cn` - China regions
- `aws-us-gov` - AWS GovCloud (US) regions

The service identifies the service:
- `ec2`
- `s3`
- `iam`

The region identifies which AWs resource is being used:
- `us-east-1`
- `ca-central-1`

The resource ID could be a number, name, or path:
- `user/bob`
- `instance/i-1234567890abcdef0`

If a value isn't needed, for example for some global services, it will be ommitted: `arn:aws:s3:::my-bucket`

In the AWS Management Console, it's common to be able to copy the ARN to  your clipboard.

ARNs can include a path and paths can include a wildcard character:
- IAM Policy ARN path `arn:aws:iam::123456789012:user/Development/product_1234/*`
- S3 ARN path `arn:aws:s3:::my_corporate_bucket/Development/*`

### AWS Command Line Interface (CLI)
A command line interface (CLI) processes commands to a computer program in the form of lines of text. Operating systems implement a CLI in a shell.

A terminal is a text-only interface. A console is a physical computer to physically input information into a terminal.

A shell is a command line program that users interact with to input commands. Popular shell programs include: Bash, zsh and PowerShell.

**AWS Command Line Interface** (CLI) allows users to programmatically interact with the AWS API via entering single or multi-line commands into a shell.

The AWS CLI is a Python executable program and Python is required to install AWS CLI.

The AWS CLI can be installed on Mac, Windows and Linux and the program is always called `aws`. 

### AWS Software Development Kit (SDK)
A Software Development Kit (SDK) is a collection of software development tools in one installable package.

You can use the AWS SDK to programmatically create, delete or interact with AWS resources.

AWS SDK is offered in several programming languages:
- Java
- Python
- Go
- JavaScript
- Ruby
- PHP
- C#
- C++

### AWS CloudShell
**AWS CloudShell** is a browser-based shell built into the AWS Management Console. It's scoped per region (and only available in certain regions), has access to the credentials of the logged-in user, and is a free service.

Preinstalled tools include: AWS CLI, Python, Node.js, Git, pip, tar, vum, wget and more.

1GB of free storage is included per AWS region.

Files saved in your home directory are available in future sessions for the same AWS region.

You can seamlessly switch between Bash, PowerShell and zsh shell environments.

### Infrastructure as Code (IaC)
**Infrastructure as Code** (IaC) is where you write a configuration script to automate creating, updating, or destroying cloud infrastructure.
- IaC is a blueprint for your infrastructure
- IaC allows you to easily share, version or inventory your cloud infrastructure/

AWS has two offerings for writing Infrastructure as Code.

**AWS CloudFormation** (CFN) is a **declarative** IaC tool
- What you see is what you get. It's explicit
- More verbose, but near-zero chance of misconfiguration
- Uses scripting languages, such as JSON, YAML, XML

**AWS Cloud Development Kit** (CDK) is an **imperative** IaC tool.
- You say what you want and the rest is filled in. It's implicit
- Less verbose, but more chance of misconfiguration
- Does more than declarative approaches
- Uses programming languages, such as Python or JavaScript

### CloudFormation
**AWS CloudFormation** allows you to write Infrastructure as Code (IaC) as either a JSON or YAML file.

CloudFormation is smple but can lead to large files or is limited in some regards to creating dynamic or repeatable infrastructure compared to CDK.

CloudFormation can be easier for DevOps engineers who do not have a background in web programming languages.

Since CDK generates out CloudFormation it is still important to be able to read and understand CloudFormation in order to debug IaC stacks.

CloudFormation has its own CLI.

Knowledge of CloudFormation is essential for any of the more advanced AWS certs.

### Cloud Development Kit (CDK)
AWS CDK lets you use programming languages to write Infrastructure as Code. Supported langauges include: TypeScript, Java, Python, JavaScript and .NET.

- CDK is powered by CloudFormation and generates CloudFormation templates
- CDK has a large library of reusable cloud components, called [CDK Constructs](https://constructs.dev/).
- CDK comes with its own CLI
- CDK pipelines let you quickly set up CI/CD pipelines for CDK projects (this is more painful in CloudFormation)
- CDK has a testing framework for unit and integration testing

AWS SDK looks similar, but the key difference is that CDK ensures idempotence. You won't inadvertantly create more infrastructure than you intended.

### AWS Toolkit for VSCode
**AWS Toolkit** is an open-source plugin for VSCode to create, debug, and deploy AWS resources.

It has four components:
1. **AWS Explorer** - lets you explore a wide range of AWS resources linked to your AWS account
2. **AWS CDK Explorer** - lets you explore your stacks as defined by CDK
3. **Amazon Elastic Container Service** - provides intellisense for ECS task-definition files
4. **Serverless Applications** - lets you create, debug and deploy serverless applications via SAM and CFN

### Access Keys
**Access Keys** are the key and secret required to have programmatic access to AWS resources when interacting with the AWS API outside of the AWS Management Console.

An Access Key is commonly referred to as AWS Credentials.

A user must be granted access to use Access Keys.

- Never share your Access Keys
- Never commit Access Keys to version control
- You can have two active Access Keys
- You can deactivate Access Keys
- Access Keys have whatever access a user has to AWS resources

Even if you are not planning on using Access Keys, you should set them and leave them deactivated, so that malicious actors cannot set ones. 

Access Keys should be stored in `~/.aws/credentials` and follow a TOML file format.

```TOML
[default]
aws_access_key_id=
aws_secret_access_key=
[your_profile]
aws_access_key_id=
aws_secret_access_key=
region=
```

`default` will be the Access Key used when no profile is selected. You can store multiple Access Keys by giving the profiles names.

You can use the `aws configure` CLI command to populate the credentials file.

The AWS SDK will automatically read Access Keys from environmental variables. This is the safest way to use Access Keys within your code.

```bash
export AWS_ACCESS_KEY= 
export AWS_SECRET_ACCESS_KEY=
export AWS_DEFAULT_REGION=
```

## Shared Responsibility Model
The **Shared Responsibility Model** is a cloud security framework that defines the security obligations of the custoemr versus the Cloud Service Provider. 

Each CSP has their own variant of the Shared Responsibility Model but they are all generally the same.

The type of cloud deployment model and/or the scope of cloud service category can result in specialized Shared Responsibility Models.

### AWS Shared Responsibility Model
AWS is responsible for:
- Hardware/Global Infrastructur
	- Regions
	- Availability Zones
	- Edge Locations
	- Physical Security
- Software
	- Compute
	- Storage
	- Databases
	- Networking

The Customer is responsible for:
- Configuration of Managed Services ot Third-Party Software
	- Platforms
	- Applications
	- Identity and Access Management (IAM)
- Configuration of Virtual Infrastructure and Systems
	- Operating Systems
	- Networks
	- Firewalls
- Security Configuration of Data
	- Client-side Data Encryption
	- Server-side Encryption
	- Networking Traffic Protection
	- Customer Data

In summary, Customers are responsible for secutiy **in** the Cloud. AWS is responsible for the security **of** the Cloud.

### Types of Cloud Responsibilities
With On-Premise, the customer is responsible for essentially everything.

With Infrastructure as a Service, the CSP is responsible for hardware and virtualization, while the customer is responsible for the layers from OS to application.

With Platform as a Service, the customer is really only responsible for applications and data.

With Software as a Service, the CSP is responsible for essentially everything.

### Shared Responsibility for Compute
Looking at compute as an example of the Shared Responsibility Model.

#### Infrastructure as a Service
##### Bare Metal
EC2 Bare Metal instance

The Customer is responsible for:
- The Host OS configuration
- The Hypervisor

AWS is responsible for:
- The physical machine

##### Virtual Machine
Elastic Cloud Compute (EC2)

The Customer is responsible for:
- The Guest OS configuration
- The container runtime

AWS is responsible for:
- The Hypervisor and the physical machine

##### Containers
AWS Elastic Container Service (ECS)

The Customer is responsible for:
- Configuration of containers
- Deployment of containers
- Storage of containers

AWS is responsible for:
- The OS, Hypervisor and Container Runtime

#### Platform as a Service
##### Managed Platform
AWS Elastic Beanstalk

The Customer is responsible for:
- Uploading their code
- Some configuration of the environment
- Deployment strategies
- Configuration of associated services

AWS is responsible for:
- Servers, OS, Networking, Storage, and Security

#### Software as a Service(SaaS)
##### Content Collaboration
Amazon WorkDocs

The Customer is responsible for:
- Contents of documents
- Management of files
- Configuration of shared access controls

AWS is responsible for:
- Servers, OS, Networking, Storage, and Security

#### Functions as a Service (FaaS)
#### Functions
AWS Lambda

The Customer is responsible for:
- Uploading their code

AWS is responsible for:
- Deployment, Container Runtime, Networking, Storage, Security, Physical Machine (basically everything)

### Shared Responsibility Model Alternative
The Shared Responsibility Model is a simple visualization that helps determine what the customer is responsible for and what the CSP is responsible for.

The Customer is responsible for the data and the configuration of access controls that reside in AWS.

The Customer is responsible for the configuration of cloud services and granting access to to users via permissions.

The CSP is generally responsible for the underlying infrastructure.

**Responsibility in the Cloud** - If you can configure or store it, then you the customer are responsible

**Responsibility of the Cloud** - If you cannot configure it, then the CSP is probably responsible for it.

### Shared Responsibility Model Architecture
AWS services range from traditional VMs to serverless functions, offering more or less responsibility.

Traditional VMs (such as EC2 or Elastic Beanstalk) offer an architecture familiar to a global workforce, with lots of documentation, frameworks and support.

Microservices and Containers (such as ECS/EKS Containers or Fargate Serverless Containers) allow you to mix and match languages and provide better utilization of resources.

Serverless/Functions as a Service (such as Lambda Serverless Architecture or Amplify Serverless Framework) let you just worry about your data and code, and not servers.

## Compute
### EC2 Overview
**Elastic Compute Cloud** (EC2) allows you to launch **Virtual Machines** (VMs).

A Virtual Machine is an emulation of a physical computer using software. Server virtualization allows you to easily create, copy, resize or migrate your server. Multiple VMs can run on the same physical server so you can share the costs with other customers. Imagine if your server or computer was an executable file on your computer.

When we launch a virtual machine we call it an **instance**.

An **Amazon Machine Image** (AMI) is a predefined configuration for a virtual machine.

EC2 is a highly configurable server where you can chose an AMI that affects options such as:
- The amount of CPUs
- The amount of memory (RAM)
- The amount of network bandwidth
- The Operating System, such as Windows 10, Ubuntu, AWS Linux 2
- Attaching multiple virtual hard drives for storage, such as Elastic Block Store (EBS)

EC2 is also considered the backbone of AWS because the majority of AWS services are using EC2 as their underlying servers, such as S3, RDS, DynamoDB, Lambdas.

### VMs, Containers and Serverless
**Virtual Machines** are an emulation of a physical computer using software.

**Amazon Lightsail** is the managed virtual server service. It's the "friendly" version of EC2 Virtual Machines. Use it when you need to launch a Linux or Windows server but don't have much AWS knowledge, such as launching a WordPress site.

**Containers** are virtualizations of an OS to run multiple workloads on a single OS instance. Containers are generally used in microservice architecture, where you divide your application into smaller applications that talk to each other.

**Elastic Container Service** (ECS) is a container orchestration service that supports Docker containers. It launches a cluster of servers on EC2 instances with Docker installed. Use it when you need Docker as a service, or to run containers.

**Elastic Container Registry** (ECR) is a repository for container images. In order to launch a container, you need an image. An image is a saved copy while a repository is storage that has version control.

**ECS Fargate** is a serverless orchestration container service. It's the same as ECS except you pay-on-demand per running container. With ECS you have to keep an EC2 server running even if you have no containers running. AWS manages the underlying server, so you don't have to scale or upgrade the EC2 server.

**Elastic Kubernetes Service** (EKS) is a fully managed Kubernetes service. Kubernetes (K8s) is an open-source orchestration software that was created by Google and is generally the standard for managing microservices. Use it when you need to run Kubernetes as a service.

**Serverless** is when the underlying servers are managed by AWS, so you don't need to configure or manage them.

**AWS Lambda** is a serverless functions service that lets you run code without provisioning or managing servers. You upload smal pieces of code, choose how much memory and how long a function is allowed to run before timing out. You are charged based on the runtime of the serverless function rounded to the nearest 100ms.

### High Performance Computing (HPC)
**High Performance Computing** (HPC) is using a cluster of thousands of servers with fast connections between each of them with the purpose of boosting computing capacity. Use it when you need to perform computational problems too large or too time-consuming to run on standard computers. 

The **Nitro System** is a combination of dedicated hardware and lightweight hypervisor enabling faster innovation and enhanced security. All new EC2 instances use the Nitro System.

- Nitro Cards- specialized cards for VPC, EBS and Instance Storage and controller card
- Nitro Security Chips - integrated into the motherboard. Protects hardware resources.
- Nitro Hypervisor - lightweight hypervisor for memory and CPU alocation providing bare-metal-like performance

**Bare Metal Instance** You can launch an EC2 instance that has no hypervisor so you can run workloads directly on the hardware for maximum performance and control. The M5 and R5 EC2 instances are bare metal.

**Bottlerocket** is a Linux-based open-source OS purposely-built by AWS for running containers on VMs or bare metal hosts.

**AWS ParallelCluster** is an AWS-suported open-source cluster management tool that makes it easy for you to deploy and manage High Performance Computing clusters on AWS.

### Edge and Hybrid
**Edge Computing** is when you push your computing workloads outside of your networks to run as close as possible to the destination location. 

**Hybrid Computing** is when you're able to run workloads on both your on-premise data center and AWS Virtual Private Cloud.

**AWS Outposts** are physical racks of servers that you can put in your data center. AWS Outposts allow you to use AWS API and Services such as EC2 right in your data center.

**AWS Wavelength** allows you to build and launch your applications in a telecom data center. By doing this, your applications will have ultra-low-latency since they will be pushed over a 5G network and be as close as possible to the end user.

**VMWare Cloud on AWS** allows you to manage on-premise virtual machines using VMWare as EC2 instances. The data center must be using VMWare for virtualization.

**AWS Local Zones** are edge data centers located outside of an AWS region so that you can use AWS closer to the end destination. Use this when you need faster computing, storage and databases in populated areas outside an AWS region.

### Cost and Capacity Management
**Cost Management** is how you save money.

**Capacity Management** is how you meet the demands of traffic and usage by adding or upgrading servers.

**EC2 Spot Instances**, **Reserved Instances** and **Savings Plans** are ways to save on computing, by paying up front in full or partially, by committing to a yearly contract, or by being flexible about availability and interruptions to computing services.

**AWS Batch** plans, schedules and executes your batch computing workloads across the full range of AWS compute services, and can utilize Spot Instances to save money.

**AWS Compute Optimizer** suggests how to reduce costs and improve performance by using machine learning to analyze your previous usage history.

**EC2 Autoscaling Groups** (ASGs) automatically add or remove EC2 servers to meet the current demands of traffic. This will save you money and meet capacity since you only run the amoutn of servers you need.

**Elastic Load Balancer** (ELB) distributes traffic to multiple instances, and can re-route traffic from unhealthy instances to healthy ones. It can also route traffic to EC2 instances running in different Availability Zones.

**AWS Elastic Beanstalk** (EB) is for easily deploying web-applications without developers having to worry about setting up and understanding the underlying AWS services, similar to Heroku.
  
## Storage
### Types of Storage Services
Storage comes in three types: Block, File and Object.

**Elastic Block Store** (EBS)
- Data is evenly split into blocks
- Directly accessed by the OS
- Supports only a single write volume

Use this when you need a virtual hard drive attached to a VM.

**AWS Elastic File Storage** (EFS)
- File is stored with data and metadata
- Supports multiple connections via a network share
- Supports multiple reads, while writes lock the file

Use this when you need a file-share where multiple users or VMs need to access the same drive.

**Amazon Simple Storage Service** (S3)
- Object is stored with data, metadata and unique ID
- Scales with no storage limit
- Supports multiple reads and writes with no locks

Use this when you just want to upload files and not have to worry about the underlying infrastructure. This is not intended for high IOPs.

### Introduction to S3
**File Systems** manage data as files in a file hierarchy

**Block Storage** manages data as blocks and tracks on disks.

**Object Storage** manages data as objects.

S3 provides you with unlimited storage. You don't need to think about the underlying infrastructure. The S3 Console provides an interface for you to upload and access your data.

**S3 Objects** contain your data. They are like files.

An object may consist of:
- Key - the name of the object
- Value - the data itself, made up of a sequence of bytes
- Version ID - the version of the object (when versioning is enabled)
- Metadata - additional information attached to the object

**S3 Buckets** hold objects. Buckets can also have folders, which in turn hold objects.

S3 is a universal namespace so bucket names must be unique, comparable to having a domain name.

You can store an individual object from 0 Bytes to 5 Terabytes in size.

### S3 Storage Classes
AWS offers a range of S3 storage classes that trade retrieval time, accessibility and durability for cheaper storage.

**S3 Standard** (default) is fast, has 99.99% availability, 11 9s durability and is replicated acorss at least three AZs.

**S3 Intelligent Tiering** uses ML to analyze object usage and determine the appropriate storage class. Data is moved to the most cost-effective access tier, without any performance impact or added overhead.

**S3 Standard-IA** (Infrequent Access) is still fast, and cheaper if you access files less than once a month. An additional retrieval fee is applied. It's 50% cheaper than STandard but has reduced availability.

**S3 One-Zone-IA** is still fast but objects only exist in one AZ. Availability is 99.5%. It's cheaper than Standard-IA by 20% but there is reduced durability and data could get destroyed. A retrieval fee is applied.

**S3 Glacier** is for long-term cold storage. Retrieval of data can take minutes to hours but the storage is very cheap.

**S3 Glacier Deep Archive** is the lowest cost storage class. Data retrival time is 12 hours.

**S3 Outposts** has its own storage class.

### AWS Snow Family
**AWS Snow Family** are storage and compute devices used to physically move data into or out of the cloud, when moving data over the internet or private connections would be too slow, difficult or costly.

**Snowcone** comes in two sizes:
- 8TB of storage (HDD)
- 14TB of storage (SSD)

**Snowball Edge** generally comes in two types:
- Storage optimized, 80TB
- Compute optimized, 39.5TB

**Snowmobile** can support up to 100PB of storage. Multiple snowmobiles can be ordered for very large data transfer projects.

Data is delivered to S3.

### Storage Services
**Simple Storage Service** (S3) is a serverless object storage service. You can upload very large files and an unlimited amount of files. You pay for what you store and don't need to worry about the underlying file system or upgrading the disk size.

**S3 Glacier** is a cold storage service. It's designed as a low cost storage solution for archiving and long-term backup. It uses previous generation HDD drives to get that low cost. It's highly secure and durable.

**Elastic Block Store** (EBS) is a persistent block storage service. It's a virtual hard drive in the cloud that you atach to EC2 instances. You can choose different kinds of drives: SSD, IOPS SSD, Throughput HDD, Cold HDD.

**Elastic File Storage** (EFS) is a cloud-native NFS file system service. It's file storage that you can mount to multiple EC2 instances at the same time. Use it when you need to share files between multiple servers.

**Storage Gateway** is a hybrid cloud storage service that extends your on-premise storage to the cloud.
- **File Gateway** extends your local storage to S3
- **Volume Gateway** caches your local drives to S3 so you have a continuous backup of local files in the cloud
- **Tape Gateway** stores files onto virtual tapes for backing up your files on very cost-effective long-term storage.

**AWS Snow Family** are storage devices used to physically migrate large amounts of data to the cloud.
- Snowball Edge is a briefcase-sized data storage device storing 50-80TB
- Snowmobile is a cargo container filled with racks of storage, transported via truck, to transfer up to 10PB per trailer
- Snowcone is a small version of Snowball that can transfer 8TB of data.

**AWS Backup** is a full-managed backup service that makes it easy to centralize and automate the backup of data across multiple AWS services, such as EC2, EBS, RDS, DynamoDB, EFS, Storage Gateway. You can create backup plans.

**CloudEndure Disaster Recovery** continuously replicates your machine into a low-cost staging area in your target AWS account and preferred Region, enabling fast and reliable recovery in case of data center failures.

**Amazon FSx** is a feature rich and highly-performant file system.
- **Amazon FSx for Windows File Server** uses the SMB protocol and allows you to mount FSx to Windows servers
- **Amazon FSx for Lustre** uses Linux's Lustre file system and allows you to mount FSx to Linux servers

## Databases
A **Database** is a data-store that stores semi-structured and structured data.

A database is a more complex data store as it requires using formal design and modelling techniques.

Databases can generally be categorized as either:
- Relational
	- Structured data that strongly represents tabular data (tables, columns and rows)
	- These can be row-oriented or columnar-oriented
- Non-relational
	- Semi-structured that may or may not distantly resemble tabular data

Databases have a rich set of functionality:
- specialized languages to query data
- specialized modelling strategies to optimize retrieval for different use cases
- more fine-tuned control over the transformation of the data into useful data structures or reports

Normally a database infers someone is using a relational row-oriented data store.

### Data Warehouses
A **Data Warehouse** is a relational data store (generally column-oriented) designed for analytic workloads.

Companies will have terabytes and millions of rows of data, and they need a fast way to be able to produce analytics reports.

Data warehouses generally perform aggregation, the grouping of data, such as finding a total or average. They are optimized around columns since they need to quickly aggregate column data.

Data warehouses are generally designed to be hot, meaning they can return queries very fast even though they have vast amounts of data.

Data warehouses are infrequently accessed, meaning they aren't intended for real-time reporting, but maybe daily or weekly to generate business and user reports.

A data warehouse needs to consume data from a (usually) relational database on a regular basis.

### Key-Value Stores 
A **Key-Value Database** is a type of non-relational (NoSQL) database that uses a simple key-value method to store data.

Key value stores are dumb but fast. They generally lack features like:
- Relationships
- Indexes
- Aggregation

A key-value database stores a unique key alongside a value. A simple key-value store will interpret this data as resembling a dictionary/associative array.

A key-value store can resemble tabular data but it does not have to have the consistent columns per row (it's schemaless).

Due to their simple design, they can scale well beyond a relational database.

### Document Stores
A **Document Store** is a NoSQL database that stores documents as its primary data structure. A document is commonly JSON-like, but could be JSON or XML.

Document stores are a superset of key-value stores.

The components of a document store can be compared to a relational database.

|Relational Database| Document Store|
|--|--|
|Tables|Collections|
|Rows|Documents|
|Columns|Fields|
|Indexes|Indexes|
|Joins|Embedding and Linking|

### NoSQL Database Services
**DynamoDB** is a serverless NoSQL key-value and document database. It is designed to scale to billions of records with guaranteed consistent data returns in at most a second. You also don't have to worry about managing shards. Use it when you want a massively scalable database.

DynamoDB is AWS's flagship database service, meaning whenever you think of a database that just scales, is cost effective and very fast, you should think of DynamoDB.

In 2019, Amazon's online retail services shut down their last Oracle database and completed their migration to DynamoDB. They ahd 7,500 Oracle databases and 75 petabytes of data. With DynamoDB, they reduced their costs by 60% and reduced latency by 40%.

**DocumentDB** is a NoSQL document database that is "MongoDB compatible". MongoDB is a very popular NoSQL database. There were open-source licensing issues around using open-source MongoDb, so AWS got around it by just building their own MongoDB database. Use it when you want a MongoDB database.

**Amazon Keyspaces** is a fully-managed Apache Cassandra database. Cassandra is an open-source NoSQL key-value database similar to DynamoDB in that it's a columnar store database but has some additional functionality. Use it when you want to use Apache Cassandra.

### Relational Database Services
**Relational Database Service** (RDS) is a relational database service that supports multiple SQL engines. Relational databases are the most commonly used type of database  among tech companies and start-ups.

RDS supports the following SQL engines:
- **MySQL** - The most popular open-source SQL database, purchased and now owned by Oracle
- **MariaDB** - An open-source fork of MySQL, made when MySQL was bought by Oracle
- **PostgreSQL** - The most popular open-source SQL database among developers. Has rich features but added complexity over MySQL
- **Oracle** - Oracle's proprietary SQL database. Well used by Enterprise companies. You have to buy a licence to use it
- **Microsoft SQL Server** - Microsoft's proprietary SQL database. You have to buy a licence to use it
- **Aurora** - AWS's fully managed database

**Aurora** is a fully managed database for either MySQL (5x faster) or PostgreSQL (3x faster). Use it when you want a highly available, durable, scalable and secure relational database for PostgreSQL or MySQL.

**Aurora Serverless** is the serverless on-demand version of Aurora. Use it when you want most of the benefits of Aurora but can trade to have cold starts or you don't have lots of traffic demand.

**RDS on VMware** allows you to deploy RDS-supported engines to an on-premise data center. The data center must be using VMware for virtualization. Use it when you want databases managed by RDS in your own data center.

### Other Database Services
**Redshift** is a petabyte-sized data warehouse. Data warehouses are for Online analytical Processing (OLAP). Data warehouses can be expensive because they keep data "hot", meaning they can run a very complex query on a large amount of data and get that data back quickly. Use this when you need to quickly generate analytics or reports from a large amount of data.

**ElastiCache** is a managed database for in-memory and caching open-source databases like Redis or Memcached. Use this when you need to improve the performance of an application by adding a caching layer in front of a web server or database.  

**Neptune** is a managed graph database. Data is represented as interconnected nodes. Use this when you need to understand the connections between data, such as mapping fraud rings or social media relationships.

**Amazon Timestreams** is a fully managed time seres database. Think of devices that send lots of time-sensitive data, such as IoT devices. Use this when you need to measure how things change over time.

**Amazon Quantum Ledger Database** is a fully-managed ledger database that provides transparent, immutable and cryptographically variable transaction logs. Use this when you need to record a history of financial transactions that can be trusted.

**Database Migration Service** (DMS) is a database migration service. You can migrate from:
- on-premise databases to AWS
- two databases in one or more AWS accounts using different SQL engines
- SQL to NoSQL databases

## Networking
### Cloud-Native Networking Services
**Virtual Private Cloud** (VPC) is a logically-isolated section of the AWS Cloud where you can launch AWS resources.

**Internet Gateway** enables access to the internet.

**Region** is the geographical location of your network.

**AZ** is the data centers of your AWS resources.

**Subnets** are a logical partition of an IP network into multiple, smaller network segments.

**Route Tables** determine where network traffic from your subnets are directed.

**Network Access Control Lists** (NACLs) act as firewalls at the subnet level.

**Security Groups** acts as firewalls at the subnet level.

### Enterprise/Hybrid Networking Services
**AWS Virtual Private Network** (VPN) is a secure connection between on-premise, remote offices, and mobile employees.

**DirectConnect** is a very fast dedicated gigabit connection from on-premise data centers to AWS.

**PrivateLinks** (VPC Interface Endpoints) keep traffic within the AWS network and does not traverse the internet to keep traffic secure.

### Virtual Private Cloud (VPC) and Subnets
**Virtual Private Cloud** (VPC) is a logically-isolated section of the AWS Network where you launch AWS resources. You choose a range of IPs using CIDR Range. CIDR Range of 10.0.0.0/16 = 65,536 IP Addresses.

**Subnets** are logical partitions of an IP network into multiple smaller network segments. You are breaking up your IP range for VPC into smaller networks.

Subnets need to have a smaller CIDR Range than the VPC to represent their portion of it. For example, a subnet CIDR Range of 10.0.0.0/24 = 256 IP Addresses.

A **Public Subnet** is one that can reach the internet.

A **Private Subnet** is one that cannot reach the internet.

### Security Groups vs NACLs
**Network Access Control Lists** (NACLs) act as a virtual firewall at the subnet level. You create Allow and Deny rules and can, for example, block a specific IP address known for abuse.

**Security Groups** act as a virtual firewall at the instance level. They implicitly deny all traffic and you create only Allow rules. For example, you can allow an EC2 instance access on port 22 for SSHing. You cannot block a specific IP address.   

## EC2
Elastic Compute Cloud (EC2) is a highly configurable virtual server. It is essentially resizable compute capacity and can launch new instances in minutes. Anything and everything on AWS uses EC2 instances under the hood.

1. Choose OS via Amazon Machine Image (AMI): Red Hat, Ubuntu, Windows, Amazon Linux, Suse
2. Choose an Instance type: from t2.nano ($0.0065/hour ($4.75/month) 1 vCPU 0.5GB memory) to c4.8xlarge ($1.591/hour ($1161.43/month) 36 vCPU 60GN memory 10 Gigabit performance)
3. Add Storage (EBS, EFS) - SSD, HDD, Virtual Magentic Tape, Multiple Volumes
4. Configure the Instance - Security Groups, KEy Pairs, UserData, IAM Rules, Placement Groups

### EC2 Instance Families
**Instance Families** are different combinations of CPU, Memory, Storage and Networking capacity.

Instance Families allow you to choose the appropriate combination of capacity to meet your application's unique requirements.

Different Instance Families differ because of the varying hardware used to give them their unique properties.

Instance Families are commonly called "instance types" but an instance type is a combination of size and family.

**General Purpose** (A1, T2, T3, Mac etc) offer a balance of compute, memory and networking resources. Use cases are web servers and code repositories.

**Compute Optimized** (C4, C5, C6gn etc) are ideal for compute-bound applications that benefit from high-performance processors. Use cases are scientific modelling, dedicated gaming servers and ad server engines.

**Memory Optimized** (R4, X1, z1d etc) offer fast performance for workloads that process large data sets in memory. Use cases are in-memory caches, in-memory databases, real time big data analysis.

**Accelerated Optimized** (P2, G3, VT1 etc) offer hardware accelerators or co-processors. Use cases are machine learning, computational finance, seismic analysis, speech recognition.

**Storage Optimized** (I3, D2, H1 etc) offer high sequential read and write access to very large data sets on local storage. Use cases are NoSQL databases, in-memory or transactional databases, data warehouses.

## EC2 Instance Types
An **Instance Type** is a particular instance size and instance family.

A common pattern for instance sizes is:
- nano
- micro
- small
- medium
- large
- xlarge
- 2xlarge
- 4xlarge
- 8xlarge
- ...

There are exceptions to this pattern, such as c6g.metal (a bare metal machine) or C5.9xlarge (not a power of 2).

EC2 Instance Sizes generally double in price and key attributes. Sometimes it's better to get an additional instance of the same size rather than to go up in size.

|Name|vCPU|RAM (GB)|On-demand per hour| On-demand per month|
|---|---|---|---|---|
|t2.small|1|12|$0.023|$16.79|
|t2.medium|2|24|$0.0464|$33.87|
|t2.large|2|36|$0.0928|$67.74|
|t2.xlarge|4|54|$0.1856|$135.48|

### Dedicated Host vs Dedicated Instances
Dedicated Hosts are single-tenant EC2 instances designed to let you bring-your-own-license (BYOL) based on machine characteristics.

|&nbsp;|Dedicated Instance|Dedicated Host|
|--|--|--|
|Isolation|Instance Isolation|Physical Server Isolation|
|Billing|Per-instance billing (+$2 per region fee)|Per-host billing|]
|Visibility of Physical Characteristics|No visibilities|Sockets, cores, host ID|
|Affinity between host and instance|No affinity|Consistently deploy to the same instances on the same server|
|Targeted instance placement|No control|Additional control over instance placement on physical server|
|Automatic instance placement|Yes|Yes|
|Add capacity using an allocation resource|No|Yes|

### EC2 Tenancy
EC2 has three levels of tenancy:
- **Dedicated Host** - your server lives on the same physical machine and you have control of its physical attributes
- **Dedicated Instance** - your server always lives on the same physical machine with the same dedicated slot
- **Default** - your instance lives on a specific server until reboot

## EC2 Pricing Models
There are 5 different ways to pay for EC2 virtual machines.

**On-Demand** (least commitment)
- low cost and flexible
- only pay per hour or second
- use for short-term, spiky, unpredictable workloads
- cannot be interrupted
- use for first time apps

**Spot** (biggest savings, up to 90%)
- request spare computing capacity
- flexible start and end times
- can handle interruptions (server randomly stopping and starting)
- use for non-critical background jobs

**Reserved** (best long-term, up to 75% savings)
- for steady state or unpredictable usage
- comit to EC2 over a 1 or 3 year term
- can resell unused reserved instances

**Dedicated** (most expensive)
- dedicated servers
- can be on-demand, reserved, or spot
- use when you need a guarantee of isolated hardware (enterprise requirements)

**AWS Savings Plan** is another way to save but can be used for more than EC2.

### On-Demand
**On-Demand** is a pay-as-you-go model where you consume compute and then you pay.

When you launch an EC2 instance it is using the On-Demand Pricing be default.

On-Demand has no up-front payment and no long-term committment.

You are charged by the second (minimum of 60 seconds) or by the hour

Per-second billing is used for: Linux, Windows, Windows with SQL Enterprise, Windows with SQL Standard, and Windows with SQL Web Instances that do not have a sperate hourly charge.

Per-hour billing is used for: all other instance types.

When looking up pricing, it will always show EC2 pricing in the hourly rate.

On-Demand is for applications where the workload is hort-term, spiky or unpredictable.

Use it when you have a new app for development or you want to run experiments.

### Reserved Instances (RI)
**Reserved Instances** are designed for applications that have a steady-state, predictable usage, or require reserved capacity.

Reduced Pricing is based on **Term** x **Class Offering** x **RI Attributes** x **Payment Options**

**Term** - the longer the term the greater the savings
- You commit to a 1 year or 3 year contract. Reserved Instances do not renew automatically. When they expire, your instance will use On-Demand with no interruption to service.

**Class** - the less flexible the greater the savings
- Standard - Up to 75% reduced pricing compared to on-demand. You can modify RI Attributes
- Convertible - Up to 54% reduced pricing compared to on-demand. You can exchange RI based on RI Attributes if greater or equal in value
- ~~Scheduled~~ - AWS no longer offers scheduled RIs

**Payment Options** - the greater the upfront payment the greater the savings
- All Upfront - Ful payment is made at the start of the term
- Partial Upfront - A portion of the cost must be paid upfront and the remaining hours in the term are billed at a discounted hourly rate
- No Upfront - You are billed a discounted hourly rate for every hour within the term, regardless of whether the Reserved Instance is being used

RIs can be shared between multiple accounts within an AWS Organization.

Unused RIs can be sold in the Reserved Instance Marketplace.

### RI Attributes
**RI Attributes** (aka Instance Attributes) are limited based on Class Offering and can affect the final price of an RI instance. There are 4 RI Attributes:
1. **Instance Type**: for example, m4.large. This is composed of the instance family (for example, m4) and the instance size (for example, large)
2. **Region**: The Region in which the Reserved Instance is purchased
3. **Tenancy**: Whether your instance runs on shared (default) or single-tenant (dedicated) hardware
4. **Platform**: The OS, such as Linux or Windows

### Regional and Zonal RIs
When you purchase an RI, you determine the scope of the Reserved Instance. The scope does not affect the price.

**Regional RI** - purchase is for a Region
- does not reserve capacity
- RI discount applies to instance usage in any AZ in the Region
- RI discount applies to instance usage within the instance family, regardless of size. Only supported on Amazon Linux RIs with default tenancy
- You can queue purchases for regional RIs

**Zonal RI** - purchase is for an Availability Zone
- reserves capacity in the specified AZ
- RI discount applies to instance in the selected AZ (No AZ flexibility)
- No instance size flexibility. RI discount applied to instance usage for the specified instance type and size only
- You can't queue purchases for zonal RIs

### RI Limits
There is a limit to the number of Reserved Instances that you can purchase per month.

Per month, you can purchase:
- 20 Regional RIs per Region
- 20 Zonal RIs per AZ

#### Regional Limits
You cannot exceed your running On-Demand Instance limit by purchasing regional Reserved Instances. The default On-Demand Instance limit is 20.

Before purchasing RIs ensure your On-Demand limit is equal to or greater than the RIs you intend to purchase.

#### Zonal Limits
You can exceed your running On-Demand Instance limit by purchasing zonal Reserved Instances.

If you already have 20 running On-Demand Instances, and you purchase 20 zonal Reserved Instances, you can launch a further 20 On-Demand instances that match the specifications of your zonal RIs.

### Capacity Reservations
EC2 instances are backed by different kinds of hardware and so there is a finite amount of servers available within an Availability Zone per instance type or family. You could go to launch a specific type of EC2 instance but AWS has run out of that server.

Capacity Reservation is a service of EC2 that allows you to request a reserve of EC2 instance types for a specific Region and AZ.

The reserved capacity is charged at the selected instance type's On-Demand rate, whether the instance is running in it or not.

You can also use your regional reserved instances with your Capacity Reservations to benefit from billing discounts.

### Standard vs Convertible RI
There are some key differences between Standard and Convertible RIs:

**Standard RI**
- RI attributes can be modified
	- Change the AZ within the same Region
	- Change the scope of the zonal RI to Regional RI, or vice versa
	- Change the instance size (Linux only, default tenancy)
	- Change network from EC2-classic to VPC and vice versa
- Can't be exchanged
- Can be bought or sold in the RI Marketplace

**Convertible RI**
- RI attributes can't be modified (you perform an exchange)
- Can be exchanged during the term for another COnvertible RI with new RI attributes, including:
	- instance family
	- instance type
	- platform
	- scope
	- tenancy
- Can't be bought or sold in the RI Marketplace

### RI Marketplace
The EC2 Reserved Instance Marketplace allows you to sell your unused Standard RI to recoup your RI spend for RIs you do not intend to, or cannot, use.
- RIs can be sold after they have been active for at least 30 days and once AWS has received the upfront payment (if applicable)
- You must have a US bank account to sell RIs on the RI Marketplace
- There must be at least one month remaining in the term of the RI you are listing
- You will retain the pricing and capacity benefit of your reservation until it's sold and the transaction is complete
- Your company name (and address upon request) will be shared with the buyer for tax purposes
- A seller can set only the upfront price for an RI, The usage price and other configuration (such as, instance type, AZ, platform) willl remain the same as when the RI was initially purchased
- The term length will be rounded down to the nearest month. For example, a reservation with 9 months and 15 days remaining will appear as 9 months on the RI Marketplace
- You can sell up to $20,000 in RIs per year.
- RIs in the GovCloud region cannot be sold on the RI marketplace

### Spot Instances
AWS has unused compute capacity and want to maximise the utility of their idel servers. It's like hotels or airlines offering discounts to fill vacant rooms/seats.

**Spot Instances** provide a discount of 90% compared to On-Demand pricing. Spot Instances can also be terminated if the computing capacity is needed by other On-Demand customers.

They are designed for applications that have flexible start and end times, or that are only feasible at very low compute costs.

AWS Batch (for batch processing) is commonly used with Spot Pricing.

Instances can be terminated by AWS at any time. If your instance is terminated by AWS, you don't get charged for a partial hour of usage. If you terminate an instance, you will still be charged for any hour that it ran.

### Dedicated Instances
**Dedicated Instances** are EC2 instances that run in a virtual private cloud (VPC) on hardware that's dedicated to a single customer. They are designed to meet regulatory requirements.

When you have strict server-bound licensing that won't support multi-tenancy or cloud deployments, use Dedicated Hosts.

Instances can be multi-tenant or single-tenant.

Multi-tenant is when multiple customers are running workloads on the same hardware, separated by virtual isolation. Think of living in an apartment building.

Single-tenant is when a single customer has dedicated hardware, separated by physical isolation. Think of living in your own house.

You choose tenancy when you launch your EC2 instance.

Dedicated Instances can be offered for:
- On-Demand
- Reserved (Up to 60% savings)
- Spot (Up to 90% savings)

Enterprise and Large Organizations may have security concerns or obligations about sharing the same hardware with other AWS customers.

### AWS Savings Plan
**AWS Savings Plans** offer similar discounts to Reserved Instances but simplify the purchasing process.

You choose one of three plan types:
- Compute Savings Plans
- EC2 Instance Savings Plans
- SageMaker Savings Plans

You choose between two different terms:
- 1 year
- 3 year

You choose an hourly commitment and the payment options:
- All Upfront
- Partial Upfront
- No upfront

**Compute Savings Plans** provide the most flexibility and help to reduce your costs by up to 66%. These plans automatically apply to EC2 instance usage, AWS Fargatema and AWS lambda service usage regardless of instance family, size, AZ, region, OS, or tenancy.

**EC2 Instance Savings Plans** provide the lowest prices, offering savings of 72% in exchange for committment to usage of individual instance families in a region. They automatically redice your cost on the selected instance family in that region regardless of AZ, size, OS or tenancy. They give you the flexibility to change your usage between instances within a family in that region.

**SageMaker Savings Plans** help you reduce SageMaker (AWS's Machine Learning service) costs by up to 64%. They automatically apply to SageMaker usage regardless of instance family, size, component, or region.

## Identity
### Zero-Trust Model
The **Zero Trust Model** operates on the principle of "truster no one, verify everything".

Malicious actors being able to bypass conventional access controls demonstrates that traditional security measures are no longer sufficient.

In the Zero Trust Model **Identity** becomes the primary security perimeter.

The **Primary Security Perimeter** defines the first line of defence and its security controls that protect a company's cloud resources and assets.

**Network-Centric** (old way): Traditional security focused on firewalls and VPNs since there were few employees or workstations outside the office or they were in speific remote offices.

**Identity-Centric** (new way): Remote work is much more common and we can't trust if an employee is in a secure location. We have identity based security controls like MFA, or providng provisional access based on the level of risk from where, when and what a user wants to access.

Identity-Centric security augments but does not replace Network-Centric security.

### Zero-Trust on AWS
**Identity Security Controls** you can implement on AWS to meet the Zero-Trust Model.

**AWS Identity and Access Management (IAM)**
- IAM Policies
- Permission Boundaries
- Service Control Policies (Organization-wide policies)
- IAM Policy Conditions
	- aws:SourceIp - Restrict on IP Address
	- aws:RequestedRegion - Restrict on Region
	- aws:MultiFactorAuthPresent- Restrict if MFA is turned off
	- aws:CurrentTime - Restrict access based on time of day

AWS does not have ready-to-use identity controls that are intelligent, which is why AWS is considered not to have a true Zero-Trust offering for customers, and third-party services need to be used.

AWS services can be set up for intelligent-ish detection of identity concerns but require expert knowledge.
- **AWS CloudTrail** tracks all API calls
- **Amazon GuardDuty** detects suspicious or malicious activity based on CloudTrail and other logs
- **Amazon Detective** is used to analyze, investigate and quickly identify security issues  (can ingest findings from GuardDuty)

### Zero-Trust on AWS with Third-Parties
AWS technically implements a Zero Trust Model but does not allow for intelligent identity security controls.

For example, Azure Active Directory has real-time and calculated risk detection based on more data points than AWS. And the security controls, verification or logic restriction are much more robust:
- Device and application
- Time of day
- Location
- MFA turned on
- What is being accessed

Third-party Identity Solutions all have more intelligent security controls for real-time detection:
- Azure Active Directory
- Google BeyondCorp
- JumpCloud

You would connect these to AWS via AWS Single Sign On (SSO).

### Directory Service
A **Directory Service** maps the names of network resources to their network addresses.

A directory service is shared information infrastructure for locating, managing, administering and organizing resources:
- Volumes
- Folders
- Files
- Printers
- Users
- Groups   
- Devices
- Telephone numbers
- Other objects

A directory service is a critical component of a network operating system.

A directory server (name server) is a server which provides a directory service.

Each resource on the network is considered an object by the directory server. Information about a particular resource is stored as a collection of attributes associated with that resource or object.

Well-known directory services include:
- Domain Name System (DNS), the directory service for the internet
- Microsoft Active Directory and Azure Active Directory
- Apache Directory Server
- Oracle Internet Directory (OID)
- OpenLDAP
- Cloud Identity
- JumpCloud

### Active Directory
Microsoft introduced Active Directory Domain Services in Windows 2000 to give organizations the ability to manage multiple on-premise infrastructure components and systems using a single identity per user. Active Directory can be used with AWS.

### Identity Providers (IdPs)
**Identity Provider** (IdP) is a system entity that creates, maintains, and manages identity information for principals and also provides authentication services to applications within a federation or distributed network. It is a trusty provider of your user identity that lets you use authentication to access other services.

Identity Providers could be: Facebook, Amazon, Google, Twitter, GitHub, LinkedIn.

**Federated Identity** is a method of linking a user's identity across multiple seperate identity management systems.

**OpenID** - an open standard and decentralized authentication protocol. For example, it allows you to log into a different social media platform using a Google or Facebook account. OpenID is about proving who you are.

**OAuth2.0** - an industry standard protocol for authorization. OAuth doesn't share password data but instead uses authorization tokens to prove an identity between customers and service providers. OAuth is about granting access to functionality.

**SAML** (Security Assertion Markup Language) - an open standard for exchanging authentication and authorization between an identity provider and a service provider. An important use case for SAML is Single-Sign-On via web browser.

### Single-Sign-On
**Single Sign-On** (SSO) is an authentication scheme that allows a user to log in with a single ID and password to different systems and software.

SSO allows IT departments to administer a single identity that can access many machines and cloud services.

Login for SSO is seamless. Once a user is logged into their primary directory, they won't be asked for their credentials when using other connected services.

### LDAP
**Lightweight Directory Access Protocol** (LDAP) is an open, vendor-neutral, industry standard application protocol for accessing and maintaining distributed directory information services over an IP network.

A common use of LDAP is to provide a central place to store usernames and passwords.

LDAP is for same sign-on, which allows users to use a single ID and password, but they have to enter it every time they want to log into something.

Why use LDAP when SSO is more convenient? Most SSO systems are using LDAP under the hood. LDAP was not designed to natively work with web-applications. Some systems only support integration with LDAP and not SSO.

### Multi-Factor Authentication (MFA)
**Multi-Factor Authentication** is a security control where after you fill in your credentials you have to use a second device, such as a phone, to confirm that its you logging in.

MFA protects against people who have stolen your password.

MFA is an option in most cloud providers and even social media sites.

### Security Keys
A Security Key is a secondary device used as a second dtep in authentication processes to gain access to a device, workstation, or application.

A security key can resemble a memory stick. When your finger makes contact with a button of exposed metal on the device it will generate and autofill a security token. 

A popular brand is Yubikey.
- Works out of the box with Gmail, Facebook and hundreds of services
- Supports FIDO2/WebAuthn, U2F
- Waterproof and crush resistant
- USB-A and NFC dual connectors on a single key

### AWS Identity and Access Management (IAM)
**AWS Identity and Access Management** (IAM) lets you create and manage AWS users and groups, and use permissions to allow or deny their access to AWS resources.

**IAM Policies** are JSON documents which grant permissions for a specific user, group, or role to access services. Policies are attached to IAM identities.

**IAM Permissions** are API actions that can or cannot be performed. They are represented in the IAM Policy document.

**IAM Users** are end users who log into the console or interact with AWS resources programmatically or via clicking UI interfaces.

**IAM Groups** are groups of users who all share the permissions levels of the group, such as administrators, developers, auditors.

**IAM Roles** grant AWS resources permissions to specific AWS API actions. Policies are associated to a role and it is then assigned to an AWS resource.

### Anatomy of an IAM Policy
IAM Policies are written in JSON and contain all the permissions which determine what APIO actions are allowed or denied.

They contain:
- Version - policy language version. 2012-10-17 is the latest version
- Statement - a container for the policy. The policy can contain multiple statements
- Sid (optional) - a way of labelling your statements
- Effect - sets wheneter the policy will allow or deny something
- Action - a list of actions that the policy allows or denies
- Principal - the account, user, role, or federated user to which you want to allow or deny access
- Resource - the resources to which the action applies
- Condition (optional) - the circumstances under which the policy grants permission

### Principle of Least Privilege (PoLP)
**Principle of Least Privilege** (PoLP) is the computer science concept of providing a user, role, or application the least amount of permissions to perform an operation or action.

**Just-Enough-Access** (JEA) - permitting only the exact actions for the identity to perform a task.

**Just-In-Time** (JIT) - permitting the smallest length of duration an identity can use permissions.

**Risk-based adaptive policies** - each attempt to access a resource generates a risk score of how likely the request is to be from a compromised source. The risk score could be based on many factors, such as device, user location, IP address, what sercvice is being accessed and when.

AWS doesn't currently have risk-based adaptive policies built into IAM.
   
ConsoleMe is an open-source Netflix project to self-serve short-lived IAM policies so an end user can access AWS resources while enforcing JEA and JIT.

### AWS Account Root User
- **AWS Account** - the account which holds all your AWS resources
- **AWS Account Root User** - a special account with full access that cannot be deleted
- **AWS Account** - User - a user for common tasks that is assigned permissions

AWS Account Root User is a special user who is created at the time of the AWS account creation:
- The Root User account uses an email and password to login
	- A regular user has to provide the Account ID / Alias, username and password
- The Root User account cannot be deleted
- The Root User account has full permissions to the account and its permissions cannot be limited
	- You cannot use IAM policies to explicitly deny the root user access to resources
	- You can only use an AWS Organizations service to explicitly deny the root user access to resources
- There can only be one Root User per AWS account
- The Root User is for very specific and specialized tasks that are infrequently performed
	- The AWS Root User account should not be used for daily or common tasks
- It is strongly recommended to never use Root User Access Keys
- It is strongly recommended to turn on MFA for the Root User

 Administrative tasks that only the Root User can perform:
 - **Change your account settings**
	 - includes the account name, email address, root user password, and root user access keys
	 - Other account settings, such as contact information, payment currency preference, and Regions, do not require Root User credentials
- Restore IAM user permissions
	- If the only IAM administrator accidentally revokes their own permissions, you can sign in as the rot user to edit policies and restore those permissions
- Activate IAM access to the Billing and Cost Management console
- View certain tax invoices
- **Close your AWS account**
- **Change or cancel your AWS support plan**
- Register as a seller in the Reserved Instance Marketplace
- Enable MFA Delete on an S3 bucket
- Edit or delete an S3 bucket policy that includes an invalid VPC ID or VPC endpoint ID
- Sign up for GovCloud

### AWS Single Sign-On (SSO)
AWS Single Sign-On (AWS SSO) is where you create, or connect, your workforce identities in AWS once and manage access centrally across your AWS organization.

Choose your identity source
- AWS SSO
- Active Directory
- SAML 2.0 IdP

Manage User Permissions Centrally
- AWS Account
- AWS Applications
- SAML Applications

Users get single click access

## Application Integration
**Application Integration** is the process of letting two independent applications communicate and work with each other, commonly facilitated by an intermediate system.

Cloud workloads encourage systems and services to be loosely coupled and so AWS has many services for the specific purpose of application integration.

The common systems or design patterns used for application integration generally are:
- Queueing
- Streaming
- Pub/Sub
- API Gateways
- State Machines
- Event Buses

### Queueing and SQS
A Messaging System is used to provide asynchronous communication and decouple processes via messages/events from a sender/producer to a receiver/consumer.

A Queueing System is a messaging system that generally will delete messages once they are consumed

### Streaming and Kinesis
**Streaming** is when multiple consumers can react to events (messages). Events live in the stream for long periods of time, so complex operations can be applied. It's used for real time data.

**Amazon Kinesis** is the AWS fully managed solution for collecting, processing, and analyzing streaming data in the  cloud.

### Pub-Sub and SNS
**Publish-Subscribe** is a pattern commonly implemented in messaging systems.

In a pub-sub system the sender of messages (**publishers**) do not send their messages directly to receivers. They instead send their messages to an **event bus**. The event bus categorizes the messages into groups. 

The receivers of messages (**subscribers**) subscribe to these groups. Whenever new messages appear within their subscription, the messages are immediately delivered to them.

- Publishers have no knowledge of who their subscribers are
- Subscribers do not pull for messages
- Messages are automatically and immediately pushed to subscribers
- Messages and events are interchangeable terms in pub-sub

This pattern is commonly used for real-time chat systems or web-hook systems.

**Simple Notification Service** (SNS) is a highly available, durable, secure, fully managed pub-sub messaging service that enables you to decouple microservices, distributed systems, and serverless applications.

### API Gateway
An **API Gateway** is a program that sits between a single entry point and multiple backends. API Gateways allow for throttling, logging, routing logic, or formatting of the HTTP request and response.

**Amazon API Gateway** is a solution for creating secure APIs in your cloud environment at any scale. You can create APIs that act as a front door for applications to access data, business logic, or functionality from backend services.

### State Machines
A **State Machine** is an abstract model which decides how one state moves to another based on a series of conditions. Think of it like a flow chart.

**AWS Step Functions**
- Coordinate multiple AWS services into a serverless workload
- Provide a graphical interface to visualize the components of your application as a series of steps
- Automatically triggers and tracks each step and retries when there are errors, so your application executes in order and as expected, every time
- Logs the state of each step, so when things go wrong, you can diagnose and debug problems quickly

### Event Bus and Amazon EventBridge
An **Event Bus** receives events from a source and routes events to a target based on rules.

**EventBridge** (formerly Amazon CloudWatch Events) is a serverless event bus service used for application integration by streaming real-time data to your applications.

**Default Event Bus** - an AWS account has a default event bus
**Custom Event Bus** - Scoped to multiple accounts or other AWS accounts
**SaaS Event Bus** - Scoped to third-party SaaS providers

**Events** are data emitted by services, usually JSON objects that stream within the event bus.

**Producers** are AWS services that emit events.

**Targets** are AWS services that consume events (5 targets per rule).

**Rules** determine what events to capture and pass to targets (100 rules per bus).

**Partner Sources** are third-party aps that can emit events to an event bus.

### Application Integration Services
**Simple Notification Service** (SNS) is a pub-sub messaging system. Notifications are sent via various formats such as plainttext, email, HTTP/s (webhooks), SMS, SQS and Lambda. It pushes messages which are then sent to subscribers.

**Simple Queue Service** (SQS) is a queueing messaging service. Events are sent to a queue. Other applications pull the queue fr messages. It's commonly used for background jobs.

**Step Functions** is a state machine service. It coordinates multiple AWS services into serverless workflows, letting you easily share data among Lambdas. You can have a group of lambdas wait for each other and create logical steps. It also works with Fargate Tasks.

**EventBridge** (previously CloudWatch Events) is a serverless event bus that makes it easy to connect applications together from your own application, third-party services and AWS services.

**Kinesis** is a real-time streaming data service. Producers send data to a stream. Multiple consumers can consume data within a stream. Used for real-time analytics, click streams, ingesting data from a fleet of IoT devices.

**Amazon MQ** is a managed message broker service that uses Apache ActiveMQ.

**Managed Kafka Service** (MSK) is a fully-managed Apache Kafka service. Kafka is an open-source platform for building real-time streaming data pipelines and applications, similar to Kinesis but more robust.

**API Gateway** is a fully-managed service for developers to create, publish, maintain, monitor, and secure APIs. You can create API endpoints and route them to AWS services.

**AppSync** is a fully managed GraphQL service. GraphQL is an open-source quuery language that allows you to query data from many different data sources.

## Containers
### VMs vs Containers
VMs do not make best use of space. You are always paying for some unused space.

Apps are not isolated, which could cause config conflicts, security problems, or resource hogging.

Containers allow you to run multiple apps which are virtually isolated from each other.

You can launch new containers and configure OS dependencies per container.

### Microservices
**Monolithic Architecture** - one app which is responsible for everything and functionality is tightly coupled.

**Microservice Architecture** - multiple apps which are responsible for one thing each. Functionality is isolated and stateless.

### Kubernetes
**Kubernetes** (K8) is an open-source container orchestration system for automating deployment, scaling, and management of containers.

Originally created by Google and now maintained by the Cloud Native Computing Foundation (CNCF).

The advantage of Kubernetes over Docker is the abilty to run containers distributed across multiple VMs.

A unique component of Kubernetes is a pod. A pod is a group of oen or more containers with shared storage, network resources, and other shared settings.

Kubernetes is ideal for microservice architectures where a company has dozens or hundreds of services they need to manage.

### Docker
**Docker** is a  set of platform as a service (PaaS)  products that use OS-level virtualization to deliver software in packages called containers.

Docker was the earliest popularized pen-source container platform. When people think of containers, they think of Docker.

**Docker CLI** - a CLI tool to download, upload, build, run, and debug containers.

**Dockerfile** - a configuration file on how to provision a container.

**Docker Compose** - a tool and configuration file when working with multiple containers.

**Docker Swarm** - an orchestration tool for managing deployed multi-container architectures

**Dockerhub** - a public online repository for containers published by the community for download

The Open Container Initiative (OCI) is an open governance structure for creating open industry standards around container formats and runtimes. Docker established the OCI and it is now maintained by the Linux Foundation.

Docker has been somewhat losing favour with developers  due to their handling of the introduction of a paid open-source model and alternatives like Podman are growing.

### Podman, Buildah and Skopeo
**Podman** is a container runtime engine that is OCI-compliant and is a drp-in replaccement for Docker.

- Podman is daemon-less where Docker uses a  cntainerd daemon
- Podman allows you to create pods like K8, Docker does not have pods
- Podman only replaces one part of Docker. Podman is to be used alngside Buildah and Skopeo

**Buildah** is a tool to build OCI images.

**Skopeo** is a tool for moving containers between different types of container storages.

### Container Services
**Primary Services** 
- Elastic Container Service (ECS)
	- No cold starts
	- Self-managed EC2
- AWS Fargate
	- More  robust than Lambda
	- Scale to zero cost
	- AWS-managed EC2
- Elastic Kubernetes Service (EKS)
	- Open source
	- Avoid vendor lock-in
- AWS Lambda
	- Only think about code
	- Short running tasks
	- Can deploy custom containers

**Provisioning and Deployment**
- Elastic Beanstalk (EB)
	- ECS on training wheels
	- Platform as  a service
- App Runner
	- Platform as a Service
	- Specifically for containers
- AWS Copilot CLI
	- build, release and operate production-ready containerized applications on AWS App Runner, Amazon ECS, and AWS Fargate

**Supporting Services**
- Elastic Container Registry
	- Repos for your  container images
- X-Ray
	- Analyze and debug between microservices
- Step Functions
	- Stitch together Lambdas and ECS tasks

## Governance
### Organizations and Accounts
**AWS Organizations** allow the creation of new AWS accounts. They let you centrally manage billing, control access, compliance, security and share resources across your AWS accounts.

**Root Account User** is a single sign-in identity that has complete access to all AWS services and resources in an account. Each account has a Root Account User.

**Orgainzation Units** are a group of AWS accounts within an organization which can also contain other organizational units, creating a hierarchy.

**Service Control Policies** give central control over the allowed permissions for all accounts in your organization, helping to ensure your accounts stay within your organization's guidelines.

AWS Organizations must be turned on, once turned on it cannot be turned off. You can create as many AWS Accounts as you like, one account will be the Master/Root Account.

An **AWS Account** is not the same as a **User Account**.

### AWS Control Tower
**AWS Control Tower** helps enterprises quickly set up a secure AWS multi-account. It provides you with a baseline environment to get started with a multi-account architecture.

AWS Control Tower is the replacement for the retired AWS Landing Zones.

**Landing Zone** is a the baseline environment following well-architected and best practices to start launching production-ready workloads.
- AWS SSO is enabled, centralized logging for AWS CloudTrail and cross-account security auditing is provided.

**Account Factory**
- Automates provisioning of new accounts in your organization
- standardizes the provisioning of new accounts with pre-approved account configurations
- configures your account factory with pre-approved network configuration and region selections
- enables self-service for your builders to configure and provision new accounts using AWS Service Catalog

**Guardrails** are pre-packaged governance rules for security, operations, and compliance that customers can select and apply enterprise-wide or to specific groups of accounts.

### AWS Config
**Change Management** in the context of cloud infrastructure is when you have a formal process to:
- monitor changes
- enforce changes
- remediate changes

**Compliance-as-Code** is when you utilize programming to automate the monitoring, enforcing and remediating changes to stay compliant with a compliance program or expected configuration.

**AWS Config** is a Compliance-as-Code framework that allows you to manage change in your AWS accounts on a per-region basis.

You should use AWS Config when:
- You want a resource to stay configured a specific way for compliance
- You want to keep track of configuration changes to resources
- You want a list of all resources in a region
- You want to analyze potential security resources and need detailed historical information
 
### AWS Quick Starts
**AWS Quick Starts** are prebuilt templates by AWS and AWS partners to help deploy a wide range of stacks. They reduce hundreds of manual procedures into just a few steps.

A Quick Start is composed of 3 parts:
1. A reference architecture for the deployment
2. AWS CloudFormation templates that automate and configure the deployment
3. A deployment guide explaining the architecture and implementation in detail

Most Quick Starts reference deployments enable you to spin up a fully functional service in less than an hour.

### Tagging
A **tag** is a key-value pair that you can assign to AWS resources.

Examples could include:
- Dept = Finance
- Status = Approved
- Team = Compliance
- Environment = Production
- Project = Enterprise
- Location = Canada

Tags allow you to organize your resources in the following ways:
- Resource management - specific workloads, environments, such as Developer Environments
- Cost management and optimization - Cost tracking, budgets, alerts
- Operations management - Business commitments and SLA operations, such as Mission-critical services
- Security - Classification of data and security impact
- Governance and regulatory compliance
- Automation
- Workload optimization

### Resource Groups
**Resource Groups** are a collection of resources that share one or more tags.

They help you organize and consolidate information based on your project and the resources that you use.

Resource Groups can display details about a group of resources based on
- Metrics
- Alarms
- Configuration Settings

At any time, you can modify the settings of your resource groups to change what resources appear.

Resource Groups appear under Resource Groups and Tag Editor.

### Business-Centric Services
**Amazon Connect** is a virtual call center service. You can create workflows to route callers, record phone calls, and manage a queue of callers. It's based on the same proven system used by Amazon customer service teams.

**Workspaces** is a virtual remote desktop service. It's a secure managed service for provisioning either Windows or Linux desktops in just a few minutes which quickly scales up to thousands of desktops.

**WorkDocs** is a shared collaboration service. It's a centralized store to share content and files, similar to Microsoft SharePoint. Think of it as a shared folder where the company has ownership.

**Chime** is a video-conferencing service, similar to Zoom or Skype. You can screenshare and have multiple people on the call. It's secure by default and can show you a calendar of your upcoming calls.

**WorkMail** is a managed business email, contacts, and calendar service with support for existing desktop and mobile client applications, similar to Gmail or Exchange.

**Pinpoint** is a marketing campaign management service, for sending targeted emails, SMS, push notifications, and voice messages. You can perform A/B testing or create Journeys (complex email response workflows).

**Simple Email Service** (SES) is a transactional email service. You can integrate SES into your application to send emails, create common templates, track open-rates, and keep track of your reputation.

**QuickSight** is a Business Intelligence (BI) service that lets you connect multiple data sources and quickly visualize data in the form of graphs with little to no programming knowledge.

## Provisioning
**Provisioning** is the allocation or creation of resources and services to a customer. AWS Provisioning Services are responsible for setting up and then managing those AWS services.

**Elastic Beanstalk** (EB) is a Platform as a Service (PaaS) to easily deploy web applications. EB will provision various AWS services, including EC2, S3, SNS, CloudWatch, EC2 Auto Scaling Groups, and Elastic Load Balancer. It's the AWS equivalent to Heroku.

**AWS OpsWorks** is a configuration management service that also provides managed instances of the open-source configuration management software Chef and Puppet.

**CloudFormation** is an infrastructure modelling and provisioning service. It automates the provisioning of AWS services by writing CloudFormation templates in either JSON or YAML. This is an example of Infrastructure as Code (IaC).

**AWS QuickStarts** are pre-made packages that can launch and configure your AWS compute, network, storage, and other services required to deploy a workload on AWS.

**AWS Marketplace** is a digital catalogue of thousands of software listings from independent software vendors that you can use to find, buy, test, and deploy software.

**AWS Amplify** is a serverless mobile and web-application framework that will provision multiple AWS services as your backend.

**AWS AppRunner** is a fully-managed service that makes it easy for developers to quickly deploy containerized web applications and APIs at scale and with no prior infrastructure experience required.

**AWS Copilot** is a CLI that enables customers to quickly launch and easily manage containerized applications on AWS.

**AWS CodeStar** provides a unified user interface, enabling you to easily manage your software development activities in one place and easily launch common tech stacks, such as LAMP.

**AWS Cloud Development Kit** (CDK) is an Infrastructure as Code tool that allows you to use your favourite programming language to generate CloudFormation templates.

### AWS Elastic Beanstalk
**Elastic Beanstalk** is a Platform as a Service for deploying web applications with little-to-no knowledge of the underlying infrastructure so you can focus on writing application code instead of setting up an automated deployment pipeline and DevOps tasks.

You choose a platform, upload your code, and it runs with little required knowledge of the infrastructure.

AWS doesn't recommend it for production applications for large companies.

Elastic Beanstalk is powered by a CloudFormation template. It sets up for you:
- Elastic Load Balancer
- Autoscaling Groups
- RDS Database
- EC2 Instance - preconfigured or custom
- Monitoring (CloudWatch/SNS)
- In-place and Blue/Green deployment strategies
- Security - rotates passwords
- Can run Dockerized environments

## Serverless
**Serverless** is when the underlying servers, infrastructure and OS are taken care of by the Cloud Service Provider. Serverless is generally by default highly available, scalable, and cost effective. You pay for what you use.

**DynamoDB** is a serverless NoSQL key-value and document database. It's designed to scale to billions of records with guaranteed consistent data return in at least a second. You don't have to worry about managing shards.

**Simple Storage Service** (S3) is a serverless object storage service. You can upload an unlimited amount of files. You pay for what you store and you don't need to worry about the underlying file system or upgrading the disk size.

**ECS Fargate** is a serverless container orchestration service. It's the same as ECS except you pay on demand per running container. With ECS you have to keep an EC2 server running even if there are no containers running. AWS manages the udnerlying server, so you don't have to scale or upgrade the EC2 server.

**AWS Lambda** is a serverless functions service. You can run code without provisioning or managing servers. You upload small pieces of code, chose how much memory and how long the function is allowed to run before timing out. You are charged based on the runtime of the serverless function rounded to the nearest 100ms.

**Step Functions** is a state machine service. It coordinates multiple AWS services into serverless workflows, letting you easily share data among Lambdas, have a group of Lambdas wait for each other, and create logical steps. It also works with Fargate Tasks.

**Aurora Serverless** is a serverless on-demand version of Aurora. Use it when you want most of the benefits of Aurora but can trade having cold starts, or you don't have lots of traffic demand.

### Serverless Architecture
Serverless architecture generally describes fully managed cloud services. The classification of a cloud service as being serverless is not a hard yes/no, but is on a scale where a cloud service is serverless to a greater or lesser degree.

A serverless service could have all or most of the following characteristics:
- Highly elastic and scalable
- Highly available
- Highly durable
- Secure by default
- Abstracts away the underlying infrastructure and bills are based on the execution of your business task
- Can scale-to-zero meaning when resources are not in use they cost nothing

Serverless implies pay-for-value, you don't pay for idle servers.

An analogy could be energy rating labels. Some services are more serverless than others.

## Windows on AWS
AWS has multiple cloud services and tools to make it easy to run Windows workloads on AWS. 

Windows Servers on EC2 - you can select from a number of Windows Server versions.

SQL Server on RDS - you can select from a number of SQL Server database versions.

AWS Directory Service lets you run Microsoft Active Directory (AD) as a managed service.

AWS Licence Manager makes it easier to manage your software licences from vendors such as Microsoft.

Amazon FSx for Windows File Server is a fully-managed scalable storage built for Windows.

AWS Software Development Kit (SDK) allows you to write code in your favourite language to interact with AWS API. The SDK supports .NET, a framework favoured by Windows developers.

Amazon WorkSpaces allow you to run a virtual desktop. You can launch a Windows 10 desktop to provide a secure and durable workstation that is accessible from wherever you have an internet connection.

AWS Lambdas support PowerShell to write serverless functions.

AWS Migration Acceleration Program (MAP) for Windows is a migration methodology for moving large enterprises. AWS has Amazon Partners that specialize in providing professional services for MAP.

### AWS Licence Manager
Bring-your-own-licence (BYOL) is the process of reusing an existing software licence to run vendor software on a cloud vendor's computing service. BYOL allows companies to save money since they may have purchased the licence in bulk or at a time that provided a greater discount.

Licence Mobility is Microsoft Volume Licencing to customers with eligible server applications covered by active Microsoft Software Assurance (SA).

**AWS Licence Manager** is a service that makes it easier for you to manage your software licences from software vendors centrally across AWS and your on-premise environments.

It manages software that is licensed based on virtual cores (vCPUs), physical cores, sockets, or number of machines. This includes a variety of software products from Microsoft, IBM, SAP, Oracle, and other vendors.

AWS Licence Manager works with:
- EC2 - dedicated instances, dedicated hosts, spot instances
- RDS - only for Oracle databases

For Microsoft Windows Server and Microsoft SQL Server licenses you generally need to use a **dedicated host**.

## Logging
### Logging Services
**CloudTrail** logs all API calls (SDK, CLI) between AWS services, telling you who to blame for issues.
- Detects developer misconfiguration
- Detects malicious actors
- Automates responses

**CloudWatch** is a collection of multiple services
- **CloudWatch Logs** - a centralized place to store your cloud service log data or application logs
- **CloudWatch Metrics** - represents a time-ordered set of data points you can monitor
- **CloudWatch Events** (EventBridge) - triggers an event based on a condition, such as taking a snapshot of the server every hour
- **CloudWatch Alarms** - triggers notifications based on metrics
- **CloudWatch Dashboard** - creates visualizations based on metrics

**AWS X-Ray** is a distributed tracing system. You can use it to pinpoint issues with your microservices, see how data moves from one app to another, how long it took to move, and if it failed to move forward.

### AWS CloudTrail
**AWS CloudTrail** is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account.

CloudTrail is used to monitor API calls and Actions made on an AWS account. It lets you easily identify which users and accounts made the call to AWS, such as:
- Where - SourceIPAddress
- When EventTime
- Who - User, UserAgent
- What - Region, Resource, Action

CloudTrail is already logging by default and will collect logs for the last 90 days via Event History. If you need more than 90 days you need to create a **Trail**.

Trails are output to S3 and do not have GUIs like Event History. To analyze a Trail, you'd have to use **Amazon Athena**.

### CloudWatch Alarms
A CloudWatch Alarm monitors a CloudWatch Metric based on a defined threshold.

When an alarm breaches (goes outside a defined threshold) then it changes state.

Metric alarm states:
- OK - The metric or expression is within the defined threshold
- ALARM - The metric or expression is outside the defined threshold
- INSUFFICIENT_DATA 
	- The alarm has just started
	- The metric is not available
	- Not enough data is available

When an alarm changes state, we can define what action it should trigger:
- Notification
- Auto Scaling Group
- EC2 Action

An Alarm consists of:
- Threshold Condition - defines when a datapoint is breached
- Metric - the actual data being measured
- Data Point - represents the metric's measurement at a given period
- Period - how often it checks to evaluate the alarm
- Evaluation Period - the number of previosu periods being considered
- Datapoints to Alarm - how many data points are breached in an evaluation period

### Log Streams
A **Log Stream** represents a sequence of events from an application or instance being monitored.

You can create Log Streams manually but generally it's automatically done by the service you are using.

Log Streams are named after the running instance. 

### Log Events
**Log Events** represent single events in a log file. Log Events can be seen within a Log Stream.

You can filter events to filter out events based on simple or pattern matching syntax.

### Log Insights
**CloudWatch Logs Insights** enable you to interactively search and analyze your CloudWatch log data and has the following advantages:
- more robust filtering than using the simple filter events in a Log Stream
- less burdensome than having to export logs to S3 and analyse them via Athena

CloudWatch Logs Insights is commonly used via the console to do ad-hoc queries against log groups.

CloudWatch Logs Insights has its own language called CloudWatch Logs Insights Query Syntax.

A single request can query up to 20 log groups. Queries time out after 15 minutes, if they have not completed. Query results are available for 7 days.

AWS provides sample queries that can get you started for common tasks and to ease learning the Query Syntax. You can create and save your own queries to make future repetitive tasks easier.

### CloudWatch Metrics
A **CloudWatch Metric** represents a time-ordered set of data points that can be monitored over time.

CloudWatch comes with many predefined metrics that are generally namespaced by AWS service.

For example, EC2 Per-Instance Metrics include:
- CPUUtilization
- DiskReadOps
- DiskWriteOps
- DiskReadBytes
- DiskWriteBytes
- NetworkIn
- NetworkOut
- NetworkPacketsIn
- NetworkPacketsOut

## ML,  AI and Big Data
**Artificial Intelligence** (AI) is machines that perform jobs that mimic human behaviour.

**Machine Learning** (ML) is machines that get better at a task without explicit programming.

**Deep Learning** is machines that have an artificial network inspired by the human brain to solve complex problems.

**Amazon SageMaker** is a fully-managed service to build, train, and deploy machine learning models at scale.
- **Apache MXNet on AWS** - an open-source deep learning framework
- **TensorFlow on AWS** - an open-source machine intelligence library
- **PyTorch on AWS** - an open-source machine learning framework

**Amazon SageMaker Ground Truth** is a data-labelling service. You can have humans label a dataset that will be used to train machine learning models.

**Amazon Augmented AI** is a human-intervention review service. When SageMaker uses machine learning to make a prediction it is not confident it has the right answer to, you can queue up the prediction for human review.

### AI and ML Services
**Amazon CodeGuru** is a machine-learning code analysis service. It performs code reviews and will suggest changes to improve the quality of your code. It can show visual code profiles showing the internals of your code to pinpoint performance issues.

**Amazon Lex** is a conversion interface service that lets you build voice and chat bots.

**Amazon Personalize** is a real-time recommendation service. The same technology used to make product recommendations to customers shopping on the Amazon platform.

**Amazon Polly** is a text-to-speech service. You upload your text and an audio file spoken by a synthesized voice is generated.

**Amazon Rekognition** is an image and video recognition service. It analyses images and videos to detect and label objects and people.

**Amazon Transcribe** is a speech to text service. You upload oyur audio file and it's converted to text.

**Amazon Textract** is an OCR service that extracts text from scanned documents. Use it when you have paper forms and you want to digitally extract the data.

**Amazon Translate** is a neural machine learning translation service. It uses deep learning models to deliver more accurate and natural sounding translations.

**Amazon Comprehend** is a natural-language-processing (NLP) service. It finds relationships between texts to product insights. It looks at data such as customer emails, support tickets, social media to make predictions.

**Amazon Forecast** is a time-series forecasting service that lets you forecast business outcomes such as product demand, resource needs, or financial performance.

**AWS Deep Learning AMIs** are Amazon EC2 instances pre-installed with popular deep learning frameworks and interfaces such as TensorFlow, PyTorch, Apache MXNet, Chainer, Gluon, Horovod, and Keras.

**AWS Deep Learning Containers** are Docker image instances pre-installed with popular deep learning frameworks and interfaces such as TensorFlow, PyTorch, and Apache MXNet.

**AWS DeepComposer** is a machine-learnign-enabled musical keyboard.

**AWS DeepLens** is a video camera that uses deep learning.

**AWS DeepRacer** is a toy race car that can be powered with machine-learning to perform autonomous driving.

**Amazon Elastic Inference** allows you to attach low-cost GPU-powered acceleration to EC2 instances to reduce the cost of running deep learning inference by up to 75%.

**Amazon Fraud Detector** is fully-managed fraud detection as a service. It identifies potentially fraudulent online activities such as online payment fraud and the creation of fake accounts.

**Amazon Kendra** is an enterprise machine learning search engine service. It uses natural language to suggest answers to questions instead of just simple keyword matching.

### Big Data and Analytics Services
**Big Data** is a term used to describe massive volumes of structured or unstructured data that is so large it is difficult to move and process using traditional database and software techniques.

**Amazon Athena** is a serverless interactive query service. It can take a bunch of CSV or JSON files in an S3 bucket and load them into temporary SQL tables so you can run SQL queries. Use it when you want to query CSV or JSON files.

**Amazon CloudSearch** is a fully-managed full-text search service. Use it when you want to add search to your website.

**Amazon Elasticsearch Service** (ES) is a managed Elasticsearch cluster. Elasticsearch is an open-source full-text search engine. It's more robust than CloudSearch but requires more server and operational maintenance.

**Amazon Elastic MapReduce** (EMR) is for data processing and analysis. It can be used for creating reports like Redshift, but is more suited when you need to transform unstructured data into structured data on the fly.

**Kinesis Data Streams** is a real-time streaming data service. You create producers which send data to a stream, Multiple consumers can consume data within a stream. Use it for real-time analytics, click streams, ingesting data from a fleet of IoT devices.

**Kinesis Firehose** is a serverless, simpler version of Data Streams. You pay on-demand based on how much data is consumed through the stream and you don't worry about the underlying servers.

**Amazon Kinesis Data Analytics** allows you to run queries against data that is flowing through your real-time stream so you can create reports and analysis on emerging data.

**Amazon Kinesis Video Streams** allows you to analyse or apply processing on real-time streaming video.

**Managed Kafka Service** (MSK) is a fully-managed Apache Kafka service. Kafka is an open-source platform for building real-time streaming data pipelines and applications. It's similar to Kinesis but with more robust functionalities.

**Redshift** is a petabyte-size data warehouse. Data warehouses are for Online Analytical Processing (OLAP). Data warehouses can be expensive because they are keeping data "hot", meaning that you can run a very complex query on a large amount of data and get that data back very fast. Use it when you need to quickly generate analytics or reports from a large amount of data.

**Amazon QuickSight** is a business intelligence (BI) dashboard. You can use it to create business dashboards to power business decisions. It requires little to no programming knowledge and connects to many different types of databases. 

**AWS Data Pipeline** automates the movement of data. You can reliably move data between compute and storage services.

**AWS Glue** is an Extract, Transform, Load (ETL) service. Use it when you are moving data from one location to another and need to perform transformations before the final destination. It's similar to Database Migration Service but more robust.

**AWS Lake Formation** is a centralized, curated, and secured repository that stores all your data. A data lake is a storage repository that holds a vast amount of raw data in its native format until its needed.

**AWS Data Exchange** is a catalogue of third-party datasets that you can download for free, subscribe to, or purchase, such as Covid-19 foot traffic data, IMDB TV and film data, historical weather data.

### Amazon QuickSight
**Amazon QuickSight** is a Business Intelligence (BI) dashboard that allows you to ingest data from various AWS storage or database services to quickly visualize business data with minimal programming or data formula knowledge.

QuickSight uses SPICE (super-fast, parallel, in-memory calculation engine) to achieve blazing fast performance at scale.

**Amazon QuickSight ML** Insight detects anomalies, performs accurate forecasting and generates natural language narratives.

**Amazon QuickSight Q** lets you ask questions using natural language on all your data and receive answers in seconds. 

## AWS Well-Architected Framework
The [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/) is a whitepaper created by AWS to help customers build using best-practices defined by AWS. 

The framework is divided into 5 sections called pillars which address different aspects or lenses that can be applied to a cloud workload.

The 5 pillars are:
- **Operational Excellence**
- **Security**
- **Reliability**
- **Performance Efficiency**
- **Cost Optimization**

Each pillar also has its own detailed whitepaper.

### General Definitions
**Operational Excellence Pillar** - runs and monitors systems
**Security Pillar** - protects data and systems, mitigates risk
**Reliability Pillar** - mitigates and recovers from disruptions
**Performance Efficiency Pillar** - uses computing resources efectively
**Cost Optimization Pillar** - gets the lowest price

Business value comes from these 5 pillars, though pillars can be traded off based on the business context.

**Component** - Code, configuration and AWS resources used against a requirement
**Workload** - A set of components that work together to deliver business value
**Milestones** - key changes of your architecture through product lifecycle
**Architecture** - how components work together in a workload
**Technology Portfolio** - A collection of workloads required for the business to operate

### On Architecture
The AWS Well-Architected Framework is designed around a different kind of team structure. Enterprises generally have centralized teams with specific roles where AWS has distributed teams with flexible roles. Distrbuted teams can cme with new risks. AWS mitigates these with practices, mechanism, and leadership principles.

On-Premise Enterprise - centralized team consisting of:
- Technical Architect (infrastructure)
- Solutions Architect (software)
- Data Architect
- Networking Architect
- Security Architect

Managed by either TOGAF or Zachman Framework

AWS - distributed team consisting of:
- Practices
	- Team experts (raise the bar)
- Mechanisms
	- Automated checks for standards
- Amazon Leadership Principle

Supported by a virtual community of SMEs, Principal Engineers, such as via lunctime talk recycled into onboarding material.

### Amazon Leadership Principles
The **Amazon Leadership Principles** are a set of principles used during decision-making, problem-solving, simple brainstorming, and hiring.

1. Customer Obsession
2. Ownership
3. Invent and Simplify
4. Are Right, A Lot
5. Learn and Be Curious
6. Hire and Develop the Best
7. Insist on the Highest Standards
8. Think Big
9. Bias for Action
10. Frugality
11. Earn Trust
12. Dive Deep
13. Have Backbone; Disagree and Commit
14. Deliver Results
15. Strive to be Earth's Best Employer
16. Success and Scale Bring Broad Responsibilty

### General Design Principles
**Stop guessing your capacity needs**. With cloud computing you use as lttle or as much based on demand.

**Test systems at production scale**. Clone production env to testing. Tear down testing not in use to save money.

**Automate to make architectural experimentation easier**, such as using CloudFormation with ChangeSets, StackUpdate and Drift Detection.

**Allow for evolutionary architectures**, such as CI/CD, rapid or nightly releases, Lambdas deprecating runtimes forcing you to evolve.

**Drive architecture using data**, such as CloudWatch, Cloud Trail automatically turned on collecting data.

**Improve through game days**. Simulate traffic on production or purposely kill EC2 instances to see test recovery.

### Anatomy of a Pillar
A pillar of the Well-Architected Framework is structured as follows:
- Design Principles - A list of design principles that need to be considered during implementation
- Definition - Overview of the best practice categories
- Best Practices - Detailed information about each best practice with AWS services 
- Resources - Additional documentation, whitepapers and videos to implement this pillar  

### Operational Excellence
**Perform operations as code**
Apply the same engineering discipline you would to aplication code to your cloud infrastructure. By treating your operations as code, you can limit human error and enable consistent responses to events. This means Infrastructure as Code.

**Make frequent, small, reversible changes**
Design workloads to allow components to be upgraded regularly. This involves rollbacks, incremental changes, blue/green deployments, CI/CD.

**Refine operations procedures frequently**
Look for continuous opportunities to improve your operations. This might involve using game days to simulate traffic or event failure on your production workloads.

**Anticipate failure**
Perform post-mortems on system failures to better improve, write test code, kill production servers to test recovery.

**Learn from all operational failures**
Share lessons learned in a knowledge base for operational events and failures across your entire operation.

### Security
**Implement a strong identity foundation**
Implement Principle of Least Privilege (PoLP). Use centralized identity. Avoid long-lived credentials.

**Enable traceability**
Monitor alert and audit actions and changes to your environment in real-time. Integrate log and metric collection and automate investigation and remediation

**Apply security at all layers**
Take a Defence in Depth approach with multiple security controls for everything, such as edge network, load balancing instances, OS, application code

**Automate security best practices**

**Protect data in transit and at rest**

**Keep people away from data**

**Prepare for security events**
Incident management systems and investigation policy and processes. Tools to detect, investigate, and recover from incidents.

### Reliability
**Automate recovery from failure**
Monitor Key Performance Indicators (KPIs) and trigger automation when threshold is breached.

**Test recovery procedures**
Test how your workload fails, and validate your recovery procedures. You can use automation to simulate different failures or to recreate scenarios that led to failures before.

**Scale horizontally to increase aggregate system availability**
Replace one large resource with multiple small resources to reduce the impact of a single failure on the overall workload. Distribute requests across multiple, smaller resources to ensure that they don't share a common point of failure.

**Stop guessing capacity**
In on-premise it takes a lot of guesswork to determine the elasticity of your workload demands. With cloud you don't need to guess how much you need because you can request the right size of resources on-demand.

**Manage change in automation**

Manage changes via Infrastructure as Code. This will allow for a formal process to track and review infrastructure.

### Performance Efficiency
**Democratize advanced technologies**
Focus on product development rather than procurement, provisioning and management of services. Take advantage of advanced technology specialized and optimized for your use-case with on-demand cloud services.

**Go global in minutes**
Deploy yourt workload in multiple AWS regions around the world, which allows you to provide lower latency and a better experience for your customers at minimal cost.

**Use serverless architectures**
Serverless architectures remove the need for you to run and maintain physical servers for traditional compute activities. This removes the operational burden of managing physical servers, and can lower transactional costs because managed services operate at cloud scale.

**Experiment more often**
With virtual and automatable resources, you can quickly carry out comparative testing using different types of instances, storage, or configurations.

**Consider mechanical sympathy**
Understand how cloud services are consumed and always use the technology approach that aligns best with your workload goals. For example, consider data access patterns when you select database or storage approaches.

### Cost Optimization
**Implement cloud financial management**
Dedicate time and resources to build capability. Use cloud financial management and cost optimization tooling.

**Adopt a consumption model**
Pay only for the computing resources that you require and increase or decrease usage depending on business requirements.

**Measure overall efficiency**
Measure the business output of the workload and the costs associated with delivering it. Use this measure to know the gains you make from increasing output and reducing costs.

**Stop spending money on undifferentiated heavy lifting**
AWS does the heavy lifting of data center operations like racking, stacking and powering servers. It also removes the operational burden of managing OSes and applications with managed services. This allows you to focus on your customers and business projects rather than on IT infrastructure.

**Analyze and attribute expenditure**
The cloud makes it easier to accurately identify the usage and costs of systems, which then allows transparent attribution of IT costs to individual workload owners. This helps measure return on investment (ROI) and gives workload owners an opportunity to optimize their resources and reduce costs.

### AWS Well-Architected Tool
The **Well-Architected Tool** is an auditing tool used to assess your cloud workloads for alignment with the AWS Well-Architected-Framework.

It's essentially a checklist with references to help you assemble a report to share with executives and key stakeholders.

### AWS Architecture Center
The [AWS Architecture Center](https://aws.amazon.com/architecture/) is a web portal that contains best practices and reference architectures for a variety of different workloads.

## Total Cost of Ownership (TCO)
Total Cost of Ownership (TCO) is a financial estimate intended to help buyers and owners determine the direct and indirect costs of a product or service. 

Creating a TCO report is useful when your company is looking to migrate from on-premise to cloud.

According to research by Gartner, "cloud services can initially be more expensive than running on-premise data centers \[However\] cloud services can become cost-effective over time if organizations learn to use and operate them more efficiently." For example, one company moving 2,500 virtual machines to EC2 had a 55% cost reduction after 3 years. Migration investments should be considered.

On-premise costs include:
- Software licence fees
- Configuration
- Training
- Physical security
- Hardware
- IT personnel
- Maintenance

AWS costs include:
- Subscription fees
- Implementation
- Configuration
- Training

AWS use to promise up to 75% savings compared to on-premise.

### CAPEX vs OPEX
**Capital Expenditure** (CAPEX) involves spending money on physical infrastructure. You can deduct that money from your tax bill over time.
- Server costs
- Storage costs
- Network costs
- Backup and archive costs
- Disaster recovery costs
- Datacenter costs
- Technical personnel

With capital expenses you have to guess upfront what you plan to spend.

**Operational Expenditure** (OPEX), where the customer has shifted the costs of the on-premise datacenter to the cloud service provider, involves the customer only being concerned with non=physical costs.
- Leasing software and customizing features
- Training employees in cloud services
- Paying for cloud support
- Billing based on cloud metrics (compute and storage usage)

With operational expenses you can try a product or service without investing in equipment.

### Shifting IT Personnel
A company is considering migrating their workloads from on-premise to the cloud to take advantage of the savings. There is a common concern among the staff that there will be mass layoffs. Does cloud make IT personnel redundent?

Shifting your IT team
- A company needs IT personnel during the migration phase
- A company can transition some roles to new cloud roles, ushc as networking to cloud networking
- A company may decide to take a hybrid approach so they'll always need to have a traditional IT team and a cloud IT team
- A company can change employee activities from **managing infrastructure to generating revenue**.

### AWS Pricing Calculator
The **AWS Pricing Calculator** is a free cost estimate tool that can be used within your web browser without the need for an AWS account to estimate the cost of various AWS services.

The AWS Pricing Calculator contains 100+ services that you can configure for cost estimate.

To calculate Total Cost of Ownership, an organization needs to compare their existing cost against the AWS costs. You can export your final estimate to a CSV file.

### Migration Evaluator
**AWS Migration Evaluator** (formerly TSO Logic) is an estimate tool used to determine an organization's existing on-premise costs so it can compare it against AWS costs for planned cloud migration.

Migration Evaluation uses an Agentless Collector to collect data from your on-premise infrastructure to extract your on-premise costs.

### VM Import/Export
VM Import/Export allows users to import Virtual Machine images into EC2.

It has import instructions for:
- VMWare
- Citrix
- Microsoft Hyper-V
- Windows VHD from Azure
- Linux VHD from Azure

1. Prepare your virtual image for upload
2. Upload your virtual image to S3
3. Use the AWS CLI to import your image. It will generate an Amazon Machine Image (AMI)

### Database Migration Service
**AWS Database Migration Service** (DMS) allows you to quickly and securely migrate one database to another. DMS can be used to migrate your on-premise database to AWS.

It's very flexible and can convert between SQL and NoSQL databases.

**AWS Schema Conversion Tool** is used in many cases to automatically convert a source database schema to a target database schema. Each migration path requires some research since not all combination of sources and targets are possible.

### Cloud Adoption Framework (CAF)
The AWS Cloud Adoption Framework is a whitepaper to help you plan your migration from on-premise to AWS.

At the highest level, the CAF organizes guidance into six focus areas:

1. **Business Perspective** - Business Managers, Finance Managers, Budget Owners, and Strategy Stakeholders
	- How to update staff skills and organizational processes to optimize business value as they move ops to the cloud
2. **People Perspective** - Human Resources, Staffing, People Managers
	- How to update staff skills and organizational processes to optimize and maintain their workforce, and ensure competencies are in place at the appropriate time
3. **Governance Perspective** - CIO, Program Managers, Project Managers, Enterprise Architects, Business Architects
	- How to update staff skills and organizational processes that are necessary to ensure business governance in the cloud, and manage and measure cloud investments to evaluate their business outcomes
4. **Platform Perspective** - CTO, IT Managers, Solutions Architects
	- How to update staff skills and organizational processes that are necessary to deliver and optimize cloud solutions and services
5. **Security Perspective** - CISO, IT Security Managers, IT Security Analysts
	- How to update staff skills and organizational processes that are necessary to ensure that the architecture deployed in the cloud aligns with the company's security control, resilience, and compliance requirements
6. **Operations Perspective** - IT Operations Managers, IT Support Managers
	- How to update staff skills and organizational processes that are necessary to ensure system health and reliability during the move of operations to the cloud and then to operate using agile, ongoing cloud-computing best practices 

## Billing, Pricing, and Support
### AWS Free Services
**AWS Free Services** are free forever, unlike the "free tier" that are free up to a point of usage/time.

Free Services include:
- IAM
- Amazon VPC
- Auto Scaling
- CloudFormation
- Elastic Beanstalk
- Opsworks
- Amplify
- AppSync
- CodeStar
- Organizations and Consolidated Billing
- AWS Cost Explorer

However these services provision other services which may themselves cost money.

### AWS Support Plans
**Basic**
- Email Support only, for Billing and Account
- 7 Trusted Advisor Checks
- $0 USD/month

**Developer**
- Tech Support via email ~24 hours until reply
- No third-party support
- General Guidance < 24 hours
- System Impaired < 12 hours
- 7 Trusted Advisor Checks
- Starting at $29 USD/month

**Business**
- Tech Support via email ~24 hours until reply 
- Tech Support via Chat, Phone anytime 24/7
- General Guidance < 24 hours
- System Impaired < 12 hours
- Production System Impaired < 4 hours
- Production System down < 1 hour
- All Trusted Advisor Checks
- Starting at $100 USD/month

**Enterprise**
- Tech Support via email ~24 hours until reply 
- Tech Support via Chat, Phone anytime 24/7
- General Guidance < 24 hours
- System Impaired < 12 hours
- Production System Impaired < 4 hours
- Production System down < 1 hour
- Business Critical System Down < 15 mins
- Personal Concierge
- Technical Account Manager (TAM)
- All Trusted Advisor Checks
- Starting at $15,000 USD/month

Developer - $29 USD/month or 3% of monthly AWS usage, whichever is greater

Business - $100 USD/month or 
- 10% of AWS usage for the first $10K
- 7% of AWS usage from $10K-80K
- 5% of AWS usage from $80K-250K
- 3% of AWS usage over $250K, whichever is greater

Enterprise - $15,000 USD/month or 
- 10% of AWS usage for the first $150K
- 7% of AWS usage from $150K-500K
- 5% of AWS usage from $500K-$1M
- 3% of AWS usage over $1M, whichever is greater

### Technical Account Manager (TAM)
A **Technical Account Manager** (TAM) provides both proactive guidance and reactive support to help you succeed with your AWS journey.

Based off AWS job postings, a TAM:
- Builds solutions, provides technical guidance, and advocates for the customer
- Ensures AWS environments remain operationally healthy while reducing cost and complexity
- Developers trusting relationships with customers, understanding their business needs and technical challenges
- Uses their technical acumen and customer obsession to drive technical discussions regarding incidents, trade-offs and risk management
- Consults with a range of partners from developers through to C-Suite executives
- Collaborates with AWS Solutions Architects, Business Developers, Professional Service Consultants, and Sales Account Managers
- Proactively finds opportunities for customers to gain additional value from AWS
- Provides detailed reviews of service disruptions, metrics, detailed prelaunch planning
- Is part of a wider Enterprise Support team providing post-sales consultative expertise
- Solves a variety of problems across different customers as they migrate their workloads to the cloud
- Uplifts customer capabilities by running workshops and brown bag sessions

TAMs follow the Amazon Leadership Principles, especially about being customer obsessed.

TAMs are only available on the Enterprise Support tier.

### AWS Marketplace
**AWS Marketplace** is a curated digital catalogue with thousands of software listings from independent software vendors.

It lets you easily find, test, buy, and deploy software that already runs on AWS.

The product can be free to use or can have an associated charge. The charge becomes part of your AWS bill, and once you pay, AWS Marketplace pays the provider.

The sales channel for ISVs and Consulting Partners allows you to sell your solutions to other AWS customers.

Prducts can be offered as:
- Amazon Machine Images (AMIs)
- AWS CloudFormation templates
- Software as a Service (SaaS) offerings
- Web ACL
- AWS WAF rules

### Consolidated Billing
**Consolidated Billing** is a feature of AWS Organizations that allws you to pay for multiple AWS accounts with one bill.

For billing, AWS treats all the accounts in an organization as if they were one account.

You can designate one master/root account that pays the charges of all the other member accounts.

Consolidated billing is offered at no additional cost.

Use **Cost Explorer** to visualize usage for consolidated billing.

You can combine the usage across all accounts in the organization to share the volume pricing discounts.

Accounts that leave the organization can no longer access Cost Explorer data and need to be assigned a new payment method.

### Consolidated Billing Volume Discounts
AWS has Volume  Discounts for many services, with the idea that the more you use the more you save.

Consolidated Billing lets you take advantage of **Volume Discounts**. It's a feature of AWS Organizations.

For example, data transfer might cost 0.17c per GB for the first 10 TB and then 0.13c per GB for the next 40 TB.  

### AWS Trusted Advisor
**AWS Trusted Advisor** is a recommendation tool which automatically and actively monitors your AWS account to provide actionable recommendations across a series of categories.

Think of AWS Trusted Advisor like an automated checklist of best practices for AWS.

The 5 categories of AWS Trusted Advisor are:
- Cost Optimization - How can we save money?
- Performance - How can we improve performance?
- Security - How can we improve security?
- Fault Tolerance - How can we prevent a disaster or data loss?
- Service Limits - Are we going to hit the maximum limit for a service?

AWS Trusted Advisor provides different levels of checks based on your AWS Support Plan.

The following checks are provided for free:
1. MFA on Root Account
2. Security Groups
3. S3 Bucket Permissions
4. EBS Public Snapshots
5. RDS Public Snapshots
6. IAM Use
7. Service Limits

Other checks include:
- Cost Optimization
	- Idle Load Balancers
	- Unassociated  Elastic IP Addresses
- Performance
	- High Utilization Amazon EC2 Instances 
- Security
	- IAM Access Key Rotation
- Fault Tolerance
	- RDS Backups
- Service Limits
	- VPCs

### Service Level Agreements(SLAs)
A **Service Level Agreement** (SLA) is a formal commitment about  the expected level of service between a customer and a provider. When a service level is not met and the customer meets their obligations under the SLA, the customer will be eligible to receive compensation, such as financial or service credits.

A **Service Level Indicator** (SLI) is a metric that indicates what measure of performance a customer is receiving at a given time. A SLI metric could be uptime, performance, availability, throughput, latency, error rate, durability, or correctness.

A **Service Level Objective** (SLO) is the objective that the provider has agreed to meet. SLOs are represented as a specific target percentage over a period of time, such as 99.99% availability over 3 months.

99.999999999% is commonly called Nine Nines.

99.99999999999% is called Nine Elevens.

### AWS Service Level Agreements
AWS offers a number of Service Level Agreements, such as:

**DynamoDB's SLA**
AWS will use commercially reasonable efforts to make DynamoDB available with a Monthly Uptime Percentage for each AWS region, during any monthly billing cycle, of (a) at least 99.999% if the Global Tables SLA applies, or (b) at least 99.99% if the Standard SLA applies.

In the event DynamoDB des not meet the Service Commitment, you will be eligible to receive a Service Credit.

|-| Monthly Uptime Percentage| Service Credt Percentage|
|--|--|--|
|Global Tables SLA|99%-99.999%|10%|
||95%-99%|25%|
||<95%|100%|
|Standard SLA|99%-99.99%|10%|
||95%-99%|25%|
||<95%|100%|

**Compute SLAs**
Compute SLAs cover servces such as EC2, EBS, ECS, EKS.

AWS makes two SLA commitments for the included services:
1. a Region-level SLA that governs services deployed across multiple AZs or regions
2. an Instance-level SLA that governs EC2 instances individually

|-| Monthly Uptime Percentage| Service Credt Percentage|
|--|--|--|
|Region-level SLA|99%-99.99%|10%|
||95%-99%|30%|
||<95%|100%|
|Instance-level SLA|99%-99.95%|10%|
||95%-99%|30%|
||<95%|100%|

**RDS SLAs**
AWS will use commercially reasonable efforts to make Multi-AZ instances available with a Monthly Uptime Percentage of at least 99.95%  during any monthly billing cycle.

In the event that Amazon RDS does not meet the Monthly Uptime Percentage commitment, you will be eligible to receive a  service credit.

| Monthly Uptime Percentage| Service Credt Percentage|
|--|--|
|99%-99.95%|10%|
|95%-99%|25%|
|<95%|100%|

### Service Health Dashboard
The **Service Health Dashboard** shows the general status of AWS services. An icon and details will indicate the status of each AWS service.

### AWS Personal Health Dashboard
The **AWS Personal Health Dashboard** provides alerts and guidance for AWS events that might affect your environment.

All AWS customers can access the Personal Health Dashboard.

The Personal Health Dashboard shows recent events to help you manage active events, and shows proactive notifications so that you can plan for scheduled activities.

You can use these alerts to get notified about changes that can affect your AWS resources, and then follow the guidance to diagnose and resolve issues.

### AWS Abuse
 **AWS Trust and Safety** is a team that specifically deals with abuses occurring on the AWs platform for the following issues:
 - **Spam** - You are receiving unwanted emails from an AWS-owned IP address, or AWS resources are used to spam websites or forums
 - **Port Scanning** - Your logs show that one or more AWS-owned IP addresses are sending packets to multiple ports on your server. You also believe this is an attempt to discover unsecured ports
 - **Denial-of-Service Attacks** - Your logs show that one or more AWS-owned IP addresses are used to flood ports on your resources with packets. You also believe this is an attempt to overwhelm or crash your server or the software running on your server
 - **Intrusion Attempts** - Your logs show that one or more AWS-owned IP addresses are being used to attempt to log into your resources
 - **Hosting Prohibited Content** - You have evidence that AWS resources are being used to host or distribute prohibited content, such as illegal content or copyrighted content without the permission of the copyright owner
 - **Distributing Malware** - You have evidence that AWS resources are being used to distribute software that was knowingly created to compromise or cause harm to computers or machines that it's installed on

AWS Support does not deal with abuse tickets. You need to contact abuse@amazonaws.com or fill out the Report Amazon AWs Abuse form.

### AWS Free Tier
AWS has a free tier that allows you to use AWs at no cost:
- for the first 12 months of signup
- or free usage up to a certain monthly limit forever

EC2 Server - t2.micro 750 hours per month for 1 year

RDS Database (MySQL or Postgres) t2.db.micro 750 hours per month for 1 year

ELB Load Balancer 750 hours per month for 1 year

Amazon CloudFront 50 GB data transfer total for 1 year

Amazon Connect 90 minutes of call time per month for 1 year

Amazon ElastiCache cache.t3.micro 750 hours per month for 1 year

Amazon ElasticSearch Service 750 hours per month for 1 year

PinPoint Campaign 5,000 targeted users per month for 1 year

SES 62,000 emails per month forever

AWS CodePipeline CI/CD 1 pipeline free

AWS CodeBuild 100 build minutes per month forever

AWS Lambda 1M free requests per month, 3.2M seconds of compute time per month

### AWS Credits
AWS Promotional Credits are equivalent to USD on the AWS platform. Credits can be earned in several ways, such as joining the AWS Activate startup program, winning hackathons, participating in surveys.

AWS Credits generally have an expiry date attached to them. Credits can be used for most services but there are exceptions, such as purchasing a domain via Route53.

### AWS Partner Network
The AWS Partner Network (APN) is a global partner program for AWS. Joining the APN will open your organization up to business opportunities and gives access to exclusive training and marketing events.

When joining the APN you can either be a:
- Consulting Partner - you help companies utilize AWS
- Technology Partner - you build technology on top of AWS as a service offering

A partner belongs to a specific tier: Select, Advanced, or Premier. Different tiers have different annual fees and certification requirements. 

You can have unique speaking opportunities in the official AWS marketing channels, such as blogs or webinars.

Being part of the APN is a requirement to be a Sponsor with a vendor booth at AWS events.

### AWS Budgets
**AWS Budgets** give you the ability to set up alerts if you exceed or are approaching your defined budget. You can create Cost, Usage, or Reservation budgets.

They can be tracked at the monthly, quarterly, or annual levels, with customizable start and end dates.

Alerts support EC2, RDS, Redshift, and ElastiCache reservations.

AWS Budgets can be used to forecast costs but are limited compared to Cost Explorer or doing your analysis with AWS cost and Usage Reports along with a Business Intelligence tool.

Budget based on a fixed cost or plan your costs upfront based on your chosen level. This can be easily managed from the AWS Budgets dashboard or via the Budgets API.

You can be notified by email or chatbot. You can view your budget history and download it as a CSV.

The first two budgets are free. After that, each budget costs 0.02 cent per day or ~0.6 USD per month. There is an upper limit of 20,000 budgets.

### AWS Budget Reports
**AWS Budget Reports** are used alongside AWS Budgets to create and send daily, weekly, or monthly reports to monitor the performance of your AWS Budget that will be emailed to specific emails.

AWS Budget Reports serve as a more convenient way of staying on top of reports since they are delivered to your email instead of you logging into the AWS Management Console.

### AWS Cost and Usage Reports (CURs)
**AWS Cost and Usage Reports** (CURs) generate a detailed spreadsheet, enabling you to better analyze and understand your AWS costs.

Reports are placed into S3. You can use Athena to turn the report into a queryable database, or QuickSight to visualize your billing data as graphs.

You can choose the granularity of your data by selecting hourly, daily, or monthly.

The report will contain Cost Allocation Tags.

CUR data is stored in either a zipped CSV or Parquet format in your selected S3 bucket.

### Cost Allocation Tags
**Cost Allocation Tags** are optional metadata that can be attached to AWS resources so when you generate a Cost and Usage Report you can use them t better analyze your data.

There are two types of tags:
- User-Defined, such as Project
- AWS Generated, such as aws:createdBy

You have to activate the tags you want to show up in the report.

### Billing Alerts/Alarms
You can create your own **Billing Alarms** in CloudWatch Alarms to monitor spend.

You first need to turn on Billing Alerts. Then, when you create a CloudWatch Alarm, you can choose Billing as your metric.

Billing Alarms are much more flexible than AWS Budgets and are ideal for more complex use-cases for monitoring spend.

### AWS Cost Explorer
AWS Cost Explorer lets you visualize, understand, and manage your AWS costs and usage over time. 

Default reports help you gain insight into your cost drivers and usage trends.

You can choose specific ranges and aggregations. There is also robust filtering. You can use forecasting to get an idea of future costs.

You can choose if you want to view your data at a monthly or daily level of granularity. Use filtering and grouping functionalities to dig even deeper into your data.

Cost Explorer shows up in US-East-1.

### AWS Pricing API
With AWS you can programmatically access pricing information to get the latest price offering for services.

There are two versions of the API:
- Query API - The Pricing Service API, via JSON
- Batch API - The Price List API, via HTML

You can also subscribe to Amazon Simple Notification Service (SNS) notifications to get alerts when prices for the services change.

AWS prices change periodically, such as when AWS cuts prices, when new instance types are launched, or when new services are introduced.

## Security
### Defense in Depth
The 7 layers of Security:
1. Data - access to business and customer data, and encryption to protect data
2. Application - applications are secure and free of security vulnerabilities
3. Compute - access to virtual machines (ports, on-premise, cloud)
4. Network - limit communications between resources using segmentation and access controls
5. Perimeter - DDos protection to filter large-scale attacks before they can cause a denial of service for users
6. Identity and Access - controlling access to infrastructure and change control
7. Physical - limiting access to a datacenter to only authorized personnel

### Confidentiality, Integrity, Availability (CIA Triad)
**Confidentiality, Integrity, and Availability** (CIA) triad is a model describing the foundation to security principlesa and their trade-off relationships.

Confidentiality is a component of privacy that protects your data from unauthorized viewers. In practice, this can be by using cryptographic keys to encrypt our data, and using keys to encypt keys (envelope encryption).

Integrity involves maintaining and assuring the accuracy and completeness of data over its entire lifecycle. In parctice, this can involved using ACID-compliant databases for valid transactions, using tamper-evident or tamper-proof hardware security modules (HSM).

Availability means that information needs to be made available when needed. In practice, this means high availability, mitigating DDoS, decryption access.

The CIA triad was first mentioned in a NIST publication from 1977. There have been efforts to expand/modernize or suggest alternatives:
- 1998 Six Atomic Elements of Information - confidentiality, possession, integrity, authenticity, availability, and utility
- 2004 NIST Engineering Principles for Information Technology Security - 33 security principles

### Vulnerabilities
A **Vulnerability** is a hole or weakness in an application, which can be a design flaw or implementation bug, that allows an attacker to cause harm to the stakeholders of the application.

Examples include:
- Buffer Overflow
- Improper Data Validation
- Least Privilege Violation
- Memory Leak
- Using a broken or risky cryptographic algorithm

### Encryption
**Cryptography** is the practice and study of techniques for secure communication in the presence of third-party adversaries.

**Encryption** is the process of encoding (scrambling) information using a key and cipher to store sensitive data in an unintelligible format as a means of protection. An encryption takes in plaintext and produces a ciphertext.

For example, the Enigma Machine used during WW2 used a different key each day to set the position of its rotors and then relied on a simple substitution cipher.

### Ciphers
A **Cipher** is an algorithm that performs encryption or decryption. Cipher is synonymous with "code".

Ciphertext is the result of encryption performed on plaintext via an algorithm.

### Cryptographic Keys
A **Cryptographic Key** is a variable used in conjunction with an encryption algorithm to encrypt or decrypt data.

Symmetric Encryption is when the same key is used for encoding and decoding, such as with Advanced Encryption Standard (AES).

Asymmetric Encryption is when two keys are used. One to encode and one to decode, such as with Rivest-Shamir-Adleman (RSA).

### Hashing and Salting
A **Hashing Function** is a function that accepts arbitrarily-sized values and maps them to a fixed-size data structure. Hashing can reduce the size of the stored value.

Hashing is a one-way process and is deterministic, it always returns the same output for the same input.

Hashing functions are used to store passwords in a database so that the password doesn't reside in plaintext format.

To authenticate a user, when a user inputs their password, it is hashed and the hash is compared to the stored hash. If they match, the user has successfully logged in.

Popular hashing functions include MD5, SHA256, and Bcrypt. If an attacker knows what function you are using and steals your database, they could enumerate a dictionary of passwords to determine the password.

A **Salt** is a random string not known to the attacker that the hash function accepts to mitigate the deterministic nature of hashing functions.

### Digital Signatures and Signing
A **Digital Signature** is a mathematical scheme for verifying the authenticity of digital messages or documents.

A digital signature gives you tamper-evidence.
- Did someone modify the data?
- Is the data not from the expected sender?

There are three algorithms for digital signatures:
- **Key Generation** - generates a public and private key
- **Signing** - the process of generating a digital signature with a  private key and inputted message
- **Signing Verification** - verifies the authenticity of the message with a public key

SSH uses a public and private key to authorize remote access to a machine, such as a virtual machine. It's common to use RSA for this. `ssh-keygen -t rsa` is a well-known command to generate a public and private key.

**Code Signing** is when you use a digital signature to ensure computer code has not been tampered with.

### In-Transit and At-Rest Encryption
**Encryption in-Transit** is when data is secure while moving between locations. The algorithms are TLS and SSL.

**Encryption At-Rest** is when data is secure while residing in storage or in a database. The algorithms are AES and RSA.

**Transport Layer Security** (TLS) is an encryption protocol for data integrity between two or more communicating applications. TLS 1.0 and 1.1 are deprecated. TLS 1.2 and 1.3 are the current best practice.

**Secure Socket Layers** (SSL) is an encryption protocol for data integrity between two or more communicating applications. SSL 1.0, 2.0 and 3.0 are deprecated and have been superceded by TLS.

### Compliance Programs
**Compliance Programs** are sets of internal company policies and procedures to comply with laws, rules, and regulations or to uphold business reputation.

Common compliance programs include:
- ISO/IEC 27701 - outlines controls and processes to manage data privacy and protect PII
- PCI DSS -  a set of security standards designed to ensure that all companies that accept, process, store, or transmit credit card information maintain a secure environment
- FIPS 140-2 - a US and Canadian government standard that specifies the security requirements for cryptographic modules that protect sensitive information
- HIPAA - US federal law that regulates patient protected health information
- CSA STAR Certification - independent third-party assessment of a cloud provider's security posture
- FedRAMP - US government standardized approach to security authorizations for ccloud service offerings
- CJIS - security policy which any state or local agency must adhere to if they want to access the FBI's CJIS database
- GDPR - European privacy law that imposes new rules on companies, government agencies, non-profits and other organizations that offer goods and services to people in the EU, or that collect and analyze data tied to EU residents

### Penetration Testing
**Pen Testing** is an authorized simulated cyberattack on a computer system, performed to evaluate the security of the system.

Pen testing is allowed to be performed on AWS.

Permitted Services:
- EC2 instances
- NAT Gateways
- Elastic Load Balancers
- RDS
- CloudFront
- Aurora
- API Gateways
- Lambda and Lambda edge functions
- Lightsail resources
- Elastic Beanstalk environments

Prohibited activities:
- DNS zone walking via Route 53 hosted zones
- Subject to the DDoS Simulation Testing Policy
	- Denial of Service
	- Distributed Denial of Service
	- Simulated DoS, Simulated DDoS
- Port flooding
- Protocol flooding
- Request flooding (login request flooding, API request flooding)

For other simulated events you will need to submit a request to AWS. A reply can take up to 7 days.

### AWS Artifact
**AWS Artifact** is a self-service portal for on-demand access to AWS compliance reports.

You can choose a report and view as PDF or download as XLSX.

### AWS Inspector
Hardening is the act of eliminating as many security risks as possible. Hardening is common for Virtual Machines where you run a collection of security checks known as a security benchmark.

AWS Inspector runs a security benchmark against specific EC2 instances. You can run a variety of security benachmarks and can perform both network and host assessments.

- Install the AWS agent on your EC2 instances
- Run an assessment for your target
- Review your findings and remediate security issues

One popular benchmark is by CIS which has 699 checks.

### Distributed Denial of Service (DDoS)
**Distributed Denial of Service** is a malicious attempt to disrupt normal traffic by flooding a website with large amounts of fake traffic.

Cloud Service Providers' networks generally have built-in DDoS protection.

### AWS Shield
AWS Shield is a managed DDoS protection service that safeguards applications running on AWS.

For example, when you route your traffic through Route53 or CloudFront, you are using AWS Shield Standard.

AWS Shield protects you against attacks at:
- Layer 7 - Application
- Layer 4 - Transport
- Layer 3 - Network


Shield Standard (free) protects against most common DDoS attacks
- access tools and best practices to build a DDoS-resilient architecture
- automatically available on all AWS services

Shield Advanced (3000 USD/year) provides additional protection against larger and more sophisticated attacks.

Shield Advanced is available on
- Route 53
- CloudFront
- Elastic Load Balancing
- Global Accelerator
- Elastic IP

It's features include:
- Visibility and reporting on layers 3, 4, and 7
- Access to team and support (with Business or Enterprise Support)
- DDoS Cost Protection
- SLA

Both plans integrate with AWS Web Application Firewall (WAF) to give you layer 7 (application) protection. 

## AWS Guard Duty
An **Intrusion Detection System** (IDS) / **Intrusion Protection System** (IPS) is a adevice or application that monitors a network or systems for malicious activity or policy violations.

**AWS Guard Duty** is a threat detection service that continuously monitors for malicious, suspicious activity and unauthorized behaviour. It uses machine learning to analyze the following logs:
- CloudTrail logs
- VPC Flow logs
- DNS logs

It will alert you of findings and you can automate a response via CloudWatch Events or with third-party services.

### Amazon Macie
**Macie** is a fully-managed service that continuously monitors S3 data access activity for anomalies and generates detailed alerts when it detects risk of unauthorized access or inadvertent data leaks.

Macie works by using machine learning to analyze your CloudTrail logs.

Macie will identify your most at-risk users, which could lead to a compromise.

Alerts include:
- Anonymized access
- Config compliance
- Credential loss
- Data compliance
- File hosting
- Identity enumeration
- Information loss
- Location anomaly
- Open permissions
- Privilege escalations
- Ransomware
- Service disruption
- Suspicious activity

### AWS Virtual Private Network (VPN)
AWS VPN lets you establish a secure and private tunnel from your network or device to the AWS global network.

AWS Site-to-Site VPN securely connects on-premise networks or branch office sites to VPC.

AWS Client VPN securely connects users to AWS or on-premise networks.

Internet Protocol Security (IPSec) is a secure network protocol suite that authenticates and encrypts the packets of data to provide secure encrypted communication between two computers over an IP network. It's used in VPNs.

### AWS WAF
**AWS Web Application Firewall** (WAF) protects your web applications from common web exploits.

You write your own rules to allow or deny traffic based on the contents of a HTTP request.

Use a ruleset from a trusted AWS Security Partner in the AWS AWF Rules Marketplace.

WAF can be attached to either CloudFront or an Application Load Balancer.

It protects web aplications from attacks covered in the OWASP Top 10 most dangerous attacks:

1. Injection
2. Broken Authentication
3. Sensitive Data Exposure
4. XML External Entities (XXE)
5. Broken Access Control
6. Security Misconfigurations
7. Cross Site Scripting (XSS)
8. Insecure Deserialization
9. Using Components with Known Vulnerabilities
10. Insufficient Logging and Monitoring

### Hardware Security Module (HSM)
A **Hardware Security Module** (HSM) is a piece of hardware designed to store encryption keys. It holds keys in memory and never writes them to disk.

They generally follow FIPS, the US and Canadian government standard specifying the security requirements for cryptographic modules that protect sensitive information.

HSMs that are multi-tenant are FIPS 140-2 Level 2 compliant with multiple customers virtually isolated on the HSM. This uses AWS KMS.

HSMs that are single-tenant are FIPS 140-2 Level 3 Compliant with a single customer on a dedicated HSM. This uses AWS CloudHSM.

### AWS Key Management Service (KMS)
**AWS Key Management Service** (KMS) is a managed service that makes it easy for you to create and control the encryption keys used to encrypt your data.

KMS is a multi-tenant hardware security module (HSM)

Many AWS services are integrated to use KMS to encrypt your data with a simple checkbox.

KMS uses envelope encryption. When you encrypt your data, your data is protected, but you have to protect your encryption key. With envelope encryption, you encrypt your data key with a master key as an additional layer of security.

### AWS CloudHSM
**AWS CloudHSM** is a single-tenant HSM as a service that automates hardware provisioning, software patching, high availability, and backups.

CloudHSM lets you generate and use your encryption keys on FIPS 140-2 Level 3 validated hardware.

It is built on HSM industry standards to integrate with:
- PKCS#11
- Java Cryptography Extensions (JCE)
- Microsoft CryptoNG (CNG) libraries

You can also transfer your keys to other commercial HSM solutions to make it easy for you to migrate keys on or off AWS.

You can configure AWS KMS to use an AWS CloudHSM cluster as a custom key store rather than the default KMS key store.

## Variation Study
### Know Your Initialisms
- IAM - Identity and Access Management
- S3 - Simple Storage Service
- SWF - Simple Workflow Service
- SNS - Simple Notification Service
- SQS - Simple Queue Service
- SES - Simple Email Service
- SSM - Simple Systems Manager
- RDS - Relational Database Service
- VPC - Virtual Private Cloud
- VPN - Virtual Private Network
- CFN - CloudFormation
- WAF - Web Application Firewall
- MQ - Amazon ActiveMQ
- ASG - Auto Scaling Groups
- TAM - Technical Account Manager
- ELB - Elastic Load Balancer
- ALB - Application Load Balancer
- NLB - Network Load Balancer
- GWLB - Gateway Load Balancer
- CLB - Classic Load Balancer
- EC2 - Elastic Cloud Compute
- ECS - Elastic Container Service
- ECR - Elastic Container Repository
- EBS - Elastic Block Storage
- EFS - Elastic File Storage
- EMR - Elastic MapReduce
- EB - Elastic Beanstalk
- ES - Elasticsearch
- EKS - Elastic Kubernetes Service
- MSK - Managed Kafka Service
- RAM - Resource Access manager
- ACM - AWS Certificate Manager
- PoLP - Principle of Least Privilege
- IoT - Internet of Things
- RI - Reserved Instances

### AWS Config vs AWS AppConfig
**AWS Config** is a governance tool for Compliance as Code (CoC).

You can create rules that will check to see if resources are configured the way you expect them to be.

If a resource drifts from the expected configuration, you are notified or AWS Config can auto-remediate the configuration back to the expected state.

**AWS AppConfig** is used to automate the process of deploying application configuration variable changes to your web applications.

You can write a validator to ensure the changed variable will not break your web app.

You can also monitor deployments and automate integrations to catch errors or roll back.

### SNS vs SQS
**Simple Notification Service** (SNS) passes along messages using a pub-sub model.

It's used to send notifications to subscribers of topics via multiple protocols, such as HTTP, Email, SQS, SMS.

SNS is generally used for sending plaintext emails triggered via other AWS services. The best example of this is billing alarms.

It can retry sending in case of failure for HTTPS, but doesn't guarantee delivery.

It's good for webhooks, simple internal emails, and triggering lambda functions.

Comparable third-party services are Pusher and PubNub.

**Simple Queue Service** (SQS) queues up messages and offers guaranteed delivery.

It places messages into a queue. Applications can then pull from the queue using the AWS SDK.

It can:
- retain messages for up to 14 days
- send messages in sequential order or in parallel
- ensure only one message is sent
- ensure messages are delivered at least once

It's good for delayed tasks such as queueing up emails.

Comparable third-party services are RabbitMQ and Sidekiq.

### SNS vs SES vs PinPoint vs Workmail
All these services send emails.

**Simple Notification Service** (SNS) is for practical and internal emails.

It can send notifications to subscribers of topics via multiple protocols, not just email.

SNS is generally used for sending plaintext emails triggered via other AWS services. The best example of this is billing alarms.

Most exam questions are going to be about SNS because lots of services can trigger SNS for notifications. You need to knwo what are **topics** and **subscriptions**.

Simple Email Service (SES) is for transactional emails, emails that should be triggered based on in-app actions, such as signup, password reset, invoices.

- SES sends HTML emails, SNS cannot
- SES can receive inbound emails
- SES can create email templates
- You can sue a custom domain name with your emails
- You can monitor your email reputation

**Amazon PinPoint** is for promotional emails, emails for marketing.

- Create email campaigns
- Segment your contacts
- Create customer journeys via email
- A/B email testing

**Amazon Workmail** is an email web client, similar to Gmail or Outlook.

It lets you create company emails, read, write and send emails from a web client within the AWS Management Console.

### Amazon Inspector vs AWS Trusted Advisor
Both of these are security tools that perform audits.

Amazon Inspector audits a single EC2 instance that you've selected. IT generates a report from a long list of security checks.

AWS Trusted Advisor gives a holistic view of recommendations across multiple services and best practices. It doesn't generate a PDF report. 

You should use MFA on your root account when using Trusted Advisor.

### Connect-Named Services
Despite their names, these services are not related.

**Direct Connect** is a dedicated fibre optic connection from your datacenter to AWS.

It's intended for large enterprises with their own datacenter that need an exceptionally fast and private connection directly to AWS.

If you need a secure connection, you need to apply an AWS VPN connection on top of Direct Connect.

**Amazon Connect** is a call center as a service.

You get a toll-free number, it accept inbound and outbound calls, sets up automated phone systems. It also offers interactive voice systems (IVS).

**Media Connect** is a new version of Elastic Transcoder. It converts videos to different video formats, applies watermarks, and can insert clips into videos.

### Elastic Transcoder vs MediaConvert
Both services transcode videos to streaming formats.

Elastic Transcoder is the older service. Some legacy customers still use it for APIs or workflows not available on MediaConvert.

AWS Elemental MediaConvert is a more robust transcoding service that can perform various operations during transcoding. It also has a more fully-featured UI.

It can also:
- overlay images
- insert clips
- extract caption data

### AWS Artifact vs Amazon Inspector
Both services compile PDF reports.

**AWS Artifact** tells enterprises why they should trust AWS. 

It generates a security report based on global compliance frameworks, such as Service Organizational Control (SOC) or Payment Card Industry (PCI).

**Amazon Inspector** is an audit tool for the security of EC2 instances.

It runs a script that analyzes your EC2 instance then generates a PDF reporting outlining which security checks passed.

### ELB Variants
Elastic Load Balancer (ELB) has 4 different possible types.

**Application Load Balancer** (ALB) 
- Operates in Layer 7 - HTTP/S
- Provides routing rules based on HTTP request
- Can attach a WAF

**Network Load Balancer** (NLB)
- Layers 3 and 4 - TCP and UDP
- Use when extreme performance is required for TCP and TLS traffic
- Capable of handling millions of requests per second while maintaining ultra-low latencies
- Optimized for sudden and volatile traffic patterns while using a single static IP address per Availability Zone

**Gateway Load Balancer** (GWLB)
- Use when you need to deploy a fleet of third-party virtual appliances that support GENEVE

**Classic Load Balancer** (CLB)
- Layers 3,4 and 7
- Intended for applications that were built within the EC2-Classic network
- Doesn't use target groups
- Retired August 15 2022