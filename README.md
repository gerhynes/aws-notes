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

On-Premise:

- You own the servers
- You hire the IT staff
- You own or rent the real-estate
- You take all the risks

Cloud Providers:

- Someone else owns the servers
- Someone else hires the IT staff
- Someone else owns or rents the real-estate
- You are responsible for configuring cloud services and code, someone else takes care of the rest

### The Evolution of Cloud Hosting

Dedicated Server

- One physical machine dedicated to a single business.
- Runs a single web app
- Very expensive, high maintenance, high security

Virtual Private Server (VPS)

- One physical machine dedicated to a single business
- The physical machine is virtualized into sub-machines
- Runs multiple web apps
- Better utilization and isolation of resources

Shared Hosting

- One physical machine shared by hundreds of businesses
- Relies on most tenants under-utilizing their resources
- Very cheap, limited functionality, poor isolation

Cloud Hosting

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

Tier-1 (Top Tier) - Early to market, wide offering, strong synergies between services, well-recognised in the industry: AWS, Azure, GCP, Alibaba Cloud.

Tier-2 (Mid Tier) - Backed by well-known tech companies, slow to innovate and turned to specialization: IBM Cloud, Oracle Cloud, Rackspace.

Tier-2 (Light Tier): VPSs turned to offer core IaaS offering. Simple, cost-effective: Vultr, Digital Ocean, Linode.

### Gartner Magic Quadrant for Cloud

Magic Quadrant (MQ) is a series of market research reports published by IT consulting form Gartner that rely on proprietary qualitative data analysis methods to demonstrate market trends, such as direction, maturity and participants. It puts AWS in the lead.

### Common Cloud Services

A CSP can have hundreds of cloud services that are grouped into various types of services. The four most common types of cloud service (the core 4) for IaaS would be:

- Compute - Imagine having a virtual computer that can run applications, programs and code

- Networking - Imagine having a virtual network defining internet connections or network isolations between services or outbound to the internet

- Storage - Imagine having a virtual hard-drive that can store files

- Databases - Imagine a virtual database for storing reporting data or a database for general purpose web applications

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

Dedicated:

- A physical server wholly utilized by a single customer
- You have to guess your capacity
- You'll overpay for an underutilized server
- You can't vertically scale, you need a manual migration
- Replacing a server is very difficult
- You are limited by the host operating system
- Multiple apps can result in conflicts in resource sharing
- Technically, you have a guarantee of security, privacy and full utility of the underlying resources

Virtual Machines:

- You can run multiple virtual machines on one machine
- Hypervisor is the software layer that lets you run the VMs
- A physical server shared by multiple customers
- You pay for a fraction of the server
- You'll overpay for an underutilized VM
- You are limited by the guest operating system
- Multiple apps on a single VM can result in conflicts in resource sharing
- Easier to export or import images for migration
- Easier to vertically or horizontally scale

Containers:

- Virtual machine running multiple containers
- Docker Daemon is the software layer that lets you run multiple containers
- You can maximize the utilization of the available capacity, which is more cost-effective
- Your containers share the same underlying OS so containers are more efficient thatn multiple VMs
- Multiple apps can run side by side without being limited to the same OS requirements and will not cause conflicts during resource sharing.

Functions:

- Managed VMs running managed containers
- Known as Serverless Compute
- You upload a piece of code, choose the amount of memery and duration
- You're only responsible for code and data, nothing else
- Very cost-effective, you only pay for the time the code is running. VMs only run when there is code to be executed.
- Cold Starts are a side-effect of this setup

### Types of Cloud Computing

Saas (Software as a service)

A product that is run and managed by a service provider. You don't worry about how the service is maintained. It just works and remains available.

PaaS (Platform as a Service)

Fosued on the deployment and management of your apps. You don't worry about provisioning, configuring or understanding the hardware or OS.

IaaS (Infrastructure as a Service)

The basic building blocks for Cloud IT. Provides access to networking features, computers and data storage space. You don't worry about IT staff, data centres and hardware.

### Cloud Computing Deployment Models

Public Cloud

**Everything** (the workload or project) is built on the CSP. Also known as Cloud-Native or Cloud-First.

Private Cloud

Everything is built on a company's datacentres. Also known as On-Premise. The cloud could be OpenStack.

Hybrid

Using both On-Premise and a Cloud Service Provider.

Cross Cloud

Using multiple Cloud Service Providers. Also known as multi-cloud
