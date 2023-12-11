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



