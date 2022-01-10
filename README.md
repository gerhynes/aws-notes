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