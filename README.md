AWS Cloud Practioner Essentials
---

# Module 5- Networking

Virtual Private Network (VPC) is like your own private network in the AWS Cloud. You decide who can talk to what, which servers are public, and which stay private. Simi to building your office network but in the cloud.


---

# Subnets

**Subnets** divide your **VPC** into smaller network sections.

**Simi to:**
 Dividing one big office floor into **different rooms** (HR room, Server room, Finance room).

You usually create:

* **Public Subnet**
* **Private Subnet**

---

## Public Subnet

**Public Subnet** → Servers that **can be accessed from the internet**.

**Simi to:**
 Reception area of the office where **visitors are allowed**

### Common resources here:

* Web servers (EC2)
* Load Balancers
* Bastion / Jump servers

### Example

User opens a website
 Internet
 Load Balancer in Public Subnet
 Web Server

 Has **Internet Gateway route**

---

## Private Subnet

**Private Subnet** → Servers **not accessible directly from the internet**.

**Simi to:**
 Server room locked inside the office (only staff allowed)

### Common resources here:

* Databases (RDS)
* Backend servers
* Internal services

### Example

Web server needs database access
 Web server (public subnet)
 Database (private subnet)
 Internet users cannot access DB directly

---

# Internet Gateway (IGW)

**Internet Gateway** connects your **VPC to the internet**.

**Simi to:**
 Main office door to the outside world

### Key points

* Required for **public subnet**
* Allows inbound & outbound internet traffic
* One IGW per VPC

### Example

Without Internet Gateway
 Your website is **offline**

---

# NAT Gateway

**NAT Gateway** allows **private subnet servers to access the internet**, but **blocks inbound access**.

**Simi to:**
 Asking the receptionist to download something for you, but visitors still can’t enter the server room

### Why needed?

* Private servers need updates (OS patches)
* Database needs to download updates
* App server needs external API access

### Example

Private EC2
 NAT Gateway
 Internet
 Can download updates
 Internet cannot connect back

---

# Route Tables

**Route Tables** control **where network traffic goes**.

**Simi to:**
 Google Maps directions for your network

### Examples

* `0.0.0.0/0 → Internet Gateway` → Public Subnet - Enables outbound internet access for instances in a public subnet.
* `0.0.0.0/0 → NAT Gateway` → Private Subnet - Allows instances in a private subnet to access the internet without being directly reachable from the internet.

If route is wrong →  no internet,  no access

---

# Security Groups

**Security Groups** are **firewalls for individual resources** (EC2, RDS, etc.).

**Simi to:**
 Personal door lock per room

### Key points

* Works at **instance level**
* **Allow rules only**
* Stateful (return traffic is automatically allowed)

### Example

Web EC2 Security Group:

* Allow HTTP (80) from internet
* Allow SSH only from IT IP

---

# Network ACLs (NACLs)

**Network ACLs** are **firewalls at the subnet level**.

**Simi to:**
 Building security guard checking everyone entering or exiting

### Key points

* Works at **subnet level**
* **Allow and Deny rules**
* Stateless (need inbound & outbound rules)

### Example

Block traffic from a malicious IP across entire subnet

---

#  Security Group vs NACL 

| Feature  | Security Group | Network ACL    |
| -------- | -------------- | -------------- |
| Level    | Instance       | Subnet         |
| Rules    | Allow only     | Allow + Deny   |
| Stateful | Yes            | No             |
| SIMI     | Door lock      | Building guard |

---

# Real-Life Flow Example

User opens website
➡️ Internet Gateway
➡️ Load Balancer (Public Subnet)
➡️ Web EC2 (Security Group allows HTTP)
➡️ Database (Private Subnet)
➡️ Database replies internally
➡️ User gets response

---

Remember

* **Public Subnet** → internet-facing
* **Private Subnet** → internal only
* **IGW** → VPC internet door
* **NAT** → safe internet access for private servers
* **Route Table** → traffic directions
* **Security Group** → server firewall
* **NACL** → subnet firewall


---

Virtual Private Gateway (VGW)

A Virtual Private Gateway is the AWS-side VPN router that connects your on-premises network to your AWS VPC using a secure tunnel.

Simi to: your office VPN gateway that lets employees securely access internal systems from outside.

Remember 

Virtual Private Gateway = AWS VPN door into your VPC

---

# AWS Client VPN

**AWS Client VPN** lets **individual users (laptops)** securely connect to AWS from **anywhere**.

**Simi to:**
 **Company VPN** you use at home to access office systems.

---

### What it does

* Users install a **VPN client** on their laptop
* Connect securely to AWS
* Access **VPC resources** (EC2, RDS, internal apps)

---

### When to use

* Work from home / remote users
* IT admins accessing AWS privately
* No office network required

---

### Example

You’re at home
 Connect using VPN client
 You can access internal EC2 / internal web apps
 Same feeling as connecting to office VPN

---

Remember

> **Client VPN = user-to-AWS secure access**

---

# AWS Site-to-Site VPN

**AWS Site-to-Site VPN** connects **your entire office network** to AWS.

**Simi to:**
 **Office network connected to another branch office**

---

### What it does

* Creates a **permanent encrypted tunnel**
* Between **on-prem router/firewall** and AWS VPC
* All office users can access AWS resources

---

### When to use

* Hybrid setup (on-prem + AWS)
* Multiple users need AWS access
* No need for individual VPN logins

---

### Example

Office PCs
 Office firewall
 VPN tunnel
 AWS VPC
 Access EC2 / RDS using private IP

---

Remember

> **Site-to-Site VPN = office network ↔ AWS**

---

# AWS PrivateLink

**AWS PrivateLink** allows private access to AWS services **without using the internet**.

**Simi to:**
 Accessing an internal system using a **private LAN IP**, not public URL.

---

### What it does

* Connects VPCs or AWS services **privately**
* Traffic stays **inside AWS network**
* No public IPs, no NAT, no internet

---

### When to use

* Secure service-to-service communication
* Exposing apps to other VPCs safely
* Compliance-heavy environments

---

### Example

VPC A (your app)
 PrivateLink
 VPC B (database or service)
 No internet exposure

---

Remember

> **PrivateLink = private service access inside AWS**

---

# AWS Direct Connect

**AWS Direct Connect** is a **dedicated physical connection** from your data center to AWS.

**Simi to:**
 Plugging a **LAN cable directly from office to AWS**

---

### What it does

* Bypasses the public internet
* More **stable, faster, predictable**
* Used for **large data transfer**

---

### When to use

* Large enterprises
* High bandwidth workloads
* Low latency & stable connection required

---

### Example

On-prem data center
 Dedicated fiber line
 AWS
 Faster than VPN
 No internet traffic

---


> **Direct Connect = private fiber cable to AWS**



Remember

* **Client VPN** → user to AWS
* **Site-to-Site VPN** → office to AWS
* **PrivateLink** → private AWS service access
* **Direct Connect** → physical private line to AWS


---


# Amazon Route 53

**Amazon Route 53** is AWS’s **DNS service** that directs users to the **correct AWS resource** (website, app, server) using a domain name.

**Simi to:**
 **Google Maps for the internet** — when someone types an address, Route 53 tells them where to go.

---

## What it does 

* Converts **domain names → IP addresses**
* Sends users to the **nearest or healthiest server**
* Keeps websites **highly available**
* Registers and manages domain names

---

## Why the name “Route 53”?

* **Route** → routing traffic
* **53** → DNS port number (53)

---


###  DNS (Domain Name System)

Turns:

```
www.mycompany.com
```

into:

```
54.23.10.5
```

**Simi to:**
 Contact name in phone → actual phone number

---

###  Domain Registration

You can **buy and manage domains** directly in AWS.

**Example**

* buy `mycompany.com`
* manage DNS in Route 53

---

###  Health Checks

Route 53 checks if your server is **up or down**.

**Simi to:**
 IT pinging a server to see if it’s alive

**Example**

* If EC2 in Singapore is down
   Route 53 automatically sends traffic to Tokyo

---

###  Traffic Routing Policies

Route 53 decides **where traffic goes** based on rules.

#### Common routing types:

* **Simple Routing** – one server
* **Weighted Routing** – split traffic (50/50)
* **Latency-based Routing** – send users to nearest region
* **Failover Routing** – auto switch when server is down
* **Geolocation Routing** – based on country

**Simi to:**
 Call center routing calls to the nearest or available agent

---

## Real-Life Example

You have:

* Website in **Singapore**
* Backup website in **Tokyo**

User opens `www.shop.com`

Route 53:

* Checks which server is **healthy**
* Sends user to the **nearest / working server**

User never notices downtime 

---

## Where Route 53 is used

* Websites hosted on EC2
* Load Balancers
* S3 static websites
* Multi-region applications
* Disaster Recovery setups

---

## Security & Reliability

* Highly available (global service)
* Integrated with:

  * **ELB**
  * **CloudFront**
  * **Health checks**
* No single point of failure

---

Remember

> **Amazon Route 53 = DNS + traffic controller + health checker for your AWS apps**


---

# Amazon CloudFront

**Amazon CloudFront** is AWS’s **Content Delivery Network (CDN)** that **caches and delivers content faster** by serving it from locations closer to users.

**Simi to:**
 **Netflix buffering solution** — instead of fetching the video from the main server every time, it plays from the nearest cache.

---

## What problem CloudFront solves

Without CloudFront:

* User in PH requests website
* Server is in US
* Long distance = slow load 

With CloudFront:

* Content is cached in a **nearby edge location**
* Faster load, lower latency 

---

## How it works

1. User opens your website
2. CloudFront checks **nearest Edge Location**
3. If content is cached → served immediately
4. If not cached → CloudFront fetches from **origin**
5. Content is cached for next users

---

## What is an “Origin”?

**Origin** = where CloudFront gets the original content

Common origins:

* S3 bucket (static website)
* Application Load Balancer
* EC2
* API Gateway

**Simi to:**
 Main warehouse (origin) → local branches (edge locations)

---

## What CloudFront can cache

* Images
* Videos
* HTML / CSS / JS
* API responses
* Downloads (PDFs, installers)

---

## Security features

CloudFront also helps with **security**, not just speed:

* HTTPS / SSL encryption
* Integrates with **AWS WAF**
* Protects against DDoS (via AWS Shield)
* Blocks bad IPs at the edge (before reaching servers)

**Simi to:**
 Security guard at the mall entrance instead of inside the shop

---

## Cost optimization bonus 

* Reduces load on your EC2 / backend
* Less data transfer from origin
* Cheaper than serving all traffic from one region

---

## Real-Life Example

Company website hosted in **Singapore**

Users from:

* Philippines
* Japan
* Australia

Without CloudFront:

* Everyone hits Singapore server

With CloudFront:

* PH users → Manila edge
* JP users → Tokyo edge
* AU users → Sydney edge

Result:
✔ Faster website
✔ Lower server load
✔ Better user experience

---

Remember

> **Amazon CloudFront = global cache that makes your website fast, secure, and closer to users**

---


# Module 6 - Storage

---


##  AWS Storage – Block vs Object vs File (How data is stored & updated)

---

##  Block Storage (Amazon EBS)

Block storage stores data in **small fixed-size blocks**, like a real hard drive (SSD/HDD).

**Key behavior:**

* Data is split into blocks
* When a file is modified, **only the changed block is updated**
* The entire file is **NOT re-uploaded**

### Example:

* 5 MB database file
* You update 1 KB
* Only the **block with that 1 KB** is saved again

 **Why it’s fast**

* Uses SSD/HDD
* Works like a local disk
* Perfect for OS, databases, apps

**SIMI:**
Block Storage = **Editing a file on your laptop → only the changed part is saved**

---

##  Object Storage (Amazon S3)

Object storage treats every file as **one whole object**.

**Key behavior:**

* No partial updates
* Any change means **uploading a new object**
* If versioning is ON → new version is created

### Example:

* 5 MB file in S3
* Change 1 byte
* S3 uploads **a new 5 MB object**

 **Why AWS designed it this way**

* Massive scale
* Very high durability
* Simple storage model

**SIMI:**
Object Storage = **Re-uploading a file to OneDrive or Google Drive after editing**

---

## File Storage (Amazon EFS)

File storage is like **a shared network drive**, but cloud-based.

**Key behavior:**

* Uses block-level updates (like EBS)
* Multiple EC2 instances can access the same files at once

### Example:

* Shared Excel file on a network drive
* Edit one cell
* Only the changed blocks are updated

**SIMI:**
File Storage = **Office shared folder / NAS**

---

##  Speed & Storage Type

Think it like this:

* **Cache / RAM** → nanoseconds to milliseconds (very fast)
* **Block/File storage (SSD/HDD)** → milliseconds (fast)
* **Object storage (S3)** → slower for updates, but extremely durable

**Your logic is correct:**

* Block/File = **disk-based (SSD/HDD)** → partial updates
* Object = **whole object** → full re-upload

---

##  Remember

Block & File storage update only the changed blocks.
 Object storage replaces the entire file.**


S3 Versioning vs EBS Snapshots

S3 Versioning

Stores entire new object

Every change = full file stored

Example:

5 MB file

Change 1 byte

New 5 MB version stored

EBS Snapshots

Stores only changed blocks

Example:

100 GB disk

Change 1 GB

Snapshot stores 1 GB

---

## When to use what

| Storage         | Use When                    |
| --------------- | --------------------------- |
| **EBS (Block)** | OS, databases, apps         |
| **EFS (File)**  | Shared folders, app servers |
| **S3 (Object)** | Backups, media, logs        |

---

AWS Storage Gateway is a hybrid storage service that connects your on-premises environment to AWS cloud storage.

SIMI:
Storage Gateway = Bridge or tunnel between on-prem storage and AWS (S3 / Glacier / EBS)
Like having a local file server, but the data actually lives in AWS.

 Why Storage Gateway Exists

Some companies:

Still have on-prem servers

Can’t move everything to cloud yet

Need backup, archiving, or cloud storage without changing apps

Storage Gateway lets them use AWS storage without fully migrating.

---


Types of AWS Storage Gateway

File Gateway

What it does:

Presents NFS / SMB shared folders on-prem

Stores files in Amazon S3

SIMI:
File Gateway = Shared Drive (File Server)
Users save files normally, but files are stored in S3.

Use cases:

File shares

Home drives

Department shared folders

Lift-and-shift file servers

 Volume Gateway
 
A) Cached Volume

What it does:

Frequently used data → cached locally

Full data → stored in AWS as EBS snapshots

SIMI:
Cached Volume = Small local SSD + huge cloud disk

Use cases:

Low on-prem storage

Need fast access to recent data

Backup to AWS

B) Stored Volume

What it does:

Data stored locally first

Backed up to AWS as snapshots

SIMI:
Stored Volume = Local disk with automatic cloud backup

Use cases:

On-prem apps that need low latency

Disaster recovery

Compliance backups

---

 Tape Gateway

What it does:

Replaces physical tape libraries

Stores backups in S3 / Glacier

SIMI:
Tape Gateway = Virtual tape library in the cloud

Use cases:

Legacy backup software

Long-term archiving

Compliance (7–10 year retention)


---


Elastic Disaster Recovery (Elastic DR) - helps you replicate your servers to AWS so that if your main server has a disaster, you can recover quickly with minimal downtime.

How it works

Replication setup – You install Elastic DR on your source servers (on-prem or cloud).

Small EC2 instances – AWS creates low-resource instances in the target region.

These instances just sync the data, not run the full server.

Only changed blocks of data are sent → efficient and fast.

Continuous sync – Your primary server’s changes are replicated in near real-time.

Failover / Recovery – If disaster happens:

AWS spins up full-size EC2 instances with all the synced data.

Your applications are back online quickly.

Key Points

Small EC2 instances always run in the background → just handle replication.

They are not full production servers → save cost and resources.

Only during disaster, AWS launches full production-sized servers.

---

Remember

small instances handle the sync, and full-size servers only get created during recovery.

These small instances are NOT production servers.

They store replicated data so that when disaster hits, AWS can launch a full-sized EC2 with all your latest data.
---
# Module 7 - Databases

---

Amazon RDS is a fully managed relational database service that automates backups, patching, scaling, and high availability for traditional SQL databases. Simi to having a database server but AWS is the Database Administrator that will handle you dont need maintain as you have already a Database Admin that is AWS. 

You will just focus on data and applications, not database maintenance.


Databases supported by RDS

MySQL

PostgreSQL

MariaDB

Oracle

SQL Server

RDS Read Replica - A copy of your primary database that stays in sync and handles read-only queries. Helps reduce load on the main database and improve performance since read replica is a different intance that would not affect the Utilization of your Main Database.

---


Amazon Aurora – High-performance cloud database, fully managed, compatible with MySQL and PostgreSQL. 


| Feature                | **RDS Read Replica**                        | **Aurora Replica**                                                                              |
| ---------------------- | ------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **Purpose**            | Offload read traffic from main DB           | Offload read traffic **and** provide high availability                                          |
| **Data Sync**          | Asynchronous (lag possible)                 | Synchronous or very fast asynchronous (almost no lag)                                           |
| **Failover**           | Needs promotion to become writable manually | Can **automatically failover** and become writable in Aurora Multi-AZ                           |
| **Write Capability**   | Read-only (until promoted)                  | Read-only by default, but Aurora can have **multiple read/write endpoints in Aurora Global DB** |
| **Number of Replicas** | Max 5 for MySQL/PostgreSQL                  | Aurora MySQL: up to 15, Aurora PostgreSQL: up to 15                                             |
| **Performance**        | Separate storage, replication can lag       | Shared storage, almost instant replication → very fast reads                                    |




---

NOSQL - Flexible databases that don’t rely on tables and rows like traditional relational databases.


DynamoDB – Fully managed NoSQL database that’s fast, scales automatically, and stores data in a flexible key-value or document format.

Why use DynamoDB:

Instant access → Reads & writes in milliseconds

Auto-scaling → Handles sudden traffic spikes like Black Friday shopping

Serverless → No need to patch, backup, or manage servers

Flexible schema → Add new attributes anytime without breaking existing data

Primary Key: Unique ID for each item → like a phone number in your contacts

Global Tables: Multi-region → friends around the world can see your new post instantly

DAX (In-memory cache): Speeds up reads → like having your contacts list in RAM instead of loading from storage

---

In Memory Cache - A place to store important data in memory (RAM) so your apps can grab it instantly, instead of going all the way to the database every time.

Cache = RAM → lightning-fast shortcut
Database = SSD/HDD → main storage room.


Amazon ElastiCache → Stores data in RAM for super fast access.
Amazon RDS / Aurora / DynamoDB → Stores data in persistent storage (SSD/HDD) for long-term use


Amazon ElastiCache – Managed in-memory caching service using Redis or Memcached. Simi to giving your apps a super-fast RAM shortcut so they don’t have to go all the way to the database (SSD/HDD) every time. Helps apps respond in milliseconds instead of seconds.

---

Amazon DocumentDB – Managed document database service that works with JSON data. Simi to MongoDB in the cloud, but AWS handles the servers, backups, and scaling for you.


--- 
AWS Backup – Centralized backup service that automatically backs up your AWS resources and manages backup policies in one place.

Simi to: an automatic backup system for servers and data, like setting scheduled backups for Windows OS in Laptor/desktop, but for EC2, RDS, DynamoDB, EFS, EBS, and more—all managed by AWS.

What it does:

Schedule automatic backups (daily, weekly, monthly)

Central place to manage all backups

Retention rules (how long backups are kept)

Restore data easily when something breaks or gets deleted

Helps with compliance and audits

Example:
Someone accidentally deletes an RDS database or an EC2 volume → AWS Backup lets IT restore it from last night’s backup in a few clicks.

Remember
AWS Backup = set it once, forget it, and recover when needed

---

Amazon Neptune – Managed graph database service used to store and analyze relationships between data.

Simi to: a mind map or relationship chart, where the focus is not just the data, but how things are connected.

What it’s good at:

Finding relationships fast (who is connected to who)

Querying complex connections in milliseconds

Fully managed (AWS handles patching, backups, scaling)

Example use cases:

Social networks → friends, followers, mutual connections

Fraud detection → detect unusual relationship patterns between users, devices, and transactions

Recommendation engines → “people who bought this also bought that”

Network & dependency mapping → system-to-system relationships

Remember

RDS = tables
DynamoDB = key-value
DocumentDB = JSON documents
Neptune = relationships

---

# Module 8 - AI/ML and Data Analytics

---


AI is the brain.
ML is how the brain learns. (ML is a subset of AI.)

AI = Think & act smart
ML = Learn from data


AWS services sample

Amazon Lex → AI chatbot

Amazon Polly → AI voice

Amazon GuardDuty → Uses ML to detect threats

Amazon Macie → Uses ML to find sensitive data

AWS services are AI-powered, but ML is what makes them smarter.

---
# Module 9 - Security

---

Authentication = “Who are you?” | Authorization = “What are you allowed to do?”


Logging into Windows with your username and password → Authentication
Being able to read files in C:\Shared but not delete them → Authorization

---
Root User  → full access, mostly for account setup & billing

Groups → Simi to “AD Security Groups” → manage permissions for multiple users at once

IAM Users → Like “Windows accounts” → assigned to groups or roles to get permissions

Roles → Like “temporary admin rights or service accounts” → usually vendor

---
AWS IAM Identity Center – Single Sign-On for AWS accounts and apps, giving users the right permissions automatically while logging in once. Simi to using AD logging in some applications.

---
AWS Secrets Manager – Secure vault for passwords, API keys, and credentials with automatic rotation and controlled access. Simi to a secure password vault like Nord Pass, but for AWS credentials, API keys, and other secrets.

IF Parameters store is just like Notepad we use it to store info but if credentials we use Nord Pass Secrets Manager.

---

AWS Systems Manager – Central tool to manage, patch, configure, and securely access all your AWS servers and resources. Simi to my explaination on the time UD has an major update that Tech need to do it manually -.- .

Example Scenario:

You have 50 POS running Universal Desktop

Use Systems Manager to:

Patch all servers automatically every week

Run a script across all instances to install an app updated Universal Desktop

Check compliance of configurations (like firewall or antivirus settings)

Access a server remotely without opening RDP or SSH → secure and logged

---

AWS Shield – AWS Shield – Cloud DDoS protection and network defense to keep your AWS apps online and safe from attacks.


Shield Standard → automatic protection for all AWS customers (no extra cost)

Shield Advanced → more sophisticated protection, real-time alerts, and 24/7 DDoS response team

---

AWS WAF – Web application firewall that protects your websites and apps from common attacks by filtering traffic before it reaches your servers.Simi to what Compliance do if they will block a Website that is suspicious

Types of Threats / Traffic WAF Can Block:

SQL Injection (SQLi)

Malicious input trying to manipulate your database via web forms Example: username=' OR '1'='1' --

Cross-Site Scripting (XSS)

Injecting malicious scripts into web pages viewed by other users Example: <script>alert('hack')</script>

Bad Bots / Crawlers

Bots scraping your website or performing automated attacks

IP Addresses

Block traffic from specific malicious IPs or geolocations

HTTP Headers & Request Patterns

Block requests with unusual headers, long query strings, or suspicious patterns

Rate-Based Rules

Block too many requests from the same source → protects against DDoS-like floods

Custom Rules

You can define rules for anything specific to your app (e.g., block /admin page from public)

---

Data Encryption -Remember the example of briefcase with key that is being deliver and how public/private key works.

At Rest = Locking data in a safe (disk/database/encrypted storage)

In Transit = Sending data through a secure tunnel (HTTPS/VPN)

--- 

Amazon Macie – Automated tool that discovers, classifies, and protects sensitive data in AWS, helping prevent accidental exposure. Simi to Outlook rules that if have an Personal Inforamtion and it has been sent to external emails it will be automatically not delivered.


AWS Certificate Manager (ACM) - ASIM

---

Amazon Inspector – Automated security scanner that checks AWS servers, containers, and functions for vulnerabilities and misconfigurations. 

Scans EC2 instances, container images, and Lambda functions for vulnerabilities

Detects security flaws, missing patches, and misconfigurations

Provides detailed findings and recommendations to fix issues

Helps meet security and compliance standards

---

Amazon GuardDuty – 24/7 threat detection service that monitors your AWS accounts and network for suspicious activity and alerts IT. SIMI to IT Compliance but 24/7 haha When user log in different country or visited an website that is phising.

Continuously monitors AWS accounts, VPC flow logs, CloudTrail logs, and DNS logs

Detects unusual behavior, compromised credentials, or malicious activity

Sends alerts to IT or Security team for investigation

Fully managed, no need to install agents

---

Amazon Detective – Cloud investigation tool that visualizes and analyzes security incidents to help IT understand what happened and why. SIMI to asking RCA to vendor.


---

AWS Security Hub – Central dashboard that collects security alerts from GuardDuty, Inspector, Macie, Config, IAM Access Analyzer, Firewall Manager, CloudTrail, and VPC Flow Logs.

List of all AWS services that included in Security Hubb.

Amazon GuardDuty – Detects suspicious activity and threats in your AWS accounts (like compromised IAM credentials, unusual API calls).

Amazon Inspector – Finds vulnerabilities and misconfigurations in EC2, containers, and Lambda.

Amazon Macie – Scans S3 buckets for sensitive data exposure (like personal info or credit cards).

AWS Firewall Manager – Manages firewall rules and protections across multiple accounts.

AWS IAM Access Analyzer – Detects resources shared outside your AWS account and potential overly permissive access.

AWS Config – Tracks configuration changes and compliance status of AWS resources.

AWS CloudTrail – Monitors API activity and helps track unusual actions.

Amazon VPC Flow Logs – Monitors network traffic for suspicious activity.

---

# Module 10 - Monitoring, Compliance and Governance in the AWS Cloud

---

Amazon CloudWatch – Simi to Windows Task Manager + Event Viewer + Performance Monitor, but for AWS. It watches your AWS servers, apps, and services in real time Shows CPU, memory, disk,network usage, and app health Helps IT quickly see if something is slow, down, or overloaded

CloudWatch is not just monitoring
It also includes:

Metrics – like performance counters (CPU, RAM, HDD/SSD)

Logs – like Event Viewer logs from servers and apps

Alarms – alerts when something exceeds a limit (ex: high CPU)

Dashboards – one screen view of system health

---


AWS CloudTrail - Simi to an Audit Log that records who did what and when in AWS. Tracks all user actions and API calls Shows who made the change, what was changed, and when it happened Helps investigate issues, misconfigurations, or security incidents

Example:

Someone deletes an EC2 instance CloudTrail shows the username, time, IP address, and action taken

---

AWS Config is a service that you can use to assess, audit, and evaluate the configurations of your AWS resources.Records configuration changes (before and after) Helps check compliance with security and best practices Useful for audits and troubleshooting misconfigurations. If misconfigurations or for example it set to public and the AWS detect that the file is containing Personal impormation it will flag as NON COMPLIANT since its should be not to set to public.

Example:

Someone opens an S3 bucket to public and the AWS Config detect that the file is containing Personal impormation it will flag as NON COMPLIANT since its should be not to set to public.

---

AWS Audit Manager – Simi to audit tool that tracks user actions (like password resets), collects logs, and helps with compliance and security checks.

---

AWS Organizations – Central AWS account management with SCPs for security, consolidated billing for easier cost tracking, and shared Reserved Instance discounts to save money.

Central account management: Organize accounts by department, project, or environment (Finance, HR, IT or Prod , Test environment)

SCPs take priority. Even if an IAM user has full permissions, if the SCP denies an action, it will not work.

Automated account creation: Quickly create new accounts with pre-configured policies

Consolidated Billing: Combine billing for all linked accounts into one invoice

Track spending per account or OU

Simplifies budgeting and cost management

Reserved Instance (RI) Discounts:

RIs purchased in one account can be shared across other accounts in the Organization

Helps maximize discounts and reduce overall AWS costs


SCP is Simi Group Policy in Active Directory

IAM permissions = the local user rights on a PC even if a local user is EUCT and have full access, Group Policy can block certain actions like resseting an AD account because ITSD only have the rights enable in Group Policy.

---

AWS Service Catalog – Pre-approved AWS resources organized in a catalog for teams to deploy securely and consistently. Simi to IT P1 and P2 or Monthly Server restart Templates. 

---

AWS License Manager – Tool to track, manage, and optimize software licenses, simi to Microsoft 365 license when we check if there an E5 license for them to access Office365.

---
AWS Trusted Advisor - Simi to asking me or manager Helps identify issues and improvement opportunities in optimize cost, efficiency, security, improve performance, and track service limits.

---
IAM Access Analyzer - Simi to IAA yearly Access review they will see when user not accesing the accounts or an access in a specific Application and they will also see if a user have a certain access that suppose to not have.

---
# Module 11 - Pricing and Support

Cost Factors 

Compute
Storage
Data Transfer

---

AWS Budgets

AWS Budgets – Simi to setting a monthly expense limit in Excel or Outlook alerts. You set a budget for AWS costs, and AWS will notify you if your spending, usage, or RI/Savings Plans utilization goes over the limit.

Use cases:

Get alerts when projected AWS costs exceed your defined budget

Monitor and control cloud spending before it becomes too expensive

---

AWS Cost Explorer

AWS Cost Explorer – Simi to a financial dashboard or pivot chart in Excel that shows where your AWS money is going using graphs and reports. It helps analyze usage trends and find cost-saving opportunities.

Use cases:

Review past AWS spending to see which services cost the most

Forecast future AWS costs based on current usage

---


AWS Pricing Calculator

AWS Pricing Calculator – Simi to planning costs before buying hardware. You select EC2 size, storage, and data transfer, and AWS calculates the estimated monthly cost before deployment.

Use cases:

Estimate AWS costs before creating resources

Compare different AWS service configurations to choose the cheapest option

---

Tip

Pricing Calculator = Before build (estimate cost)

Cost Explorer = After build (analyze spending)

Budgets = While running (alerts & control)

---

AWS Marketplace

AWS Marketplace – Simi to an App Store or Microsoft Store for AWS, where you can find, test, and buy ready-made software from third-party vendors that runs directly on AWS.

You can see pricing options, license models, and customer reviews

Software is pre-configured to run on AWS (no manual install)

Billing is added directly to your AWS account

Use cases:

Quickly deploy tools like firewalls, monitoring tools, or databases

Try software before buying without long setup

Reduce time installing and configuring third-party software

---

AWS Partner Network – Network of AWS-certified partners that help businesses build, migrate, and improve solutions on AWS.

---






# Module 12 - Migrating to the AWS Cloud

---

**Migration Phase**

Assess Phase > Mobilize Phase > Migrate and Modernize


Assess Phase - ( Goal is to know if migration is will be worth it )Migration Evaluator - Analyze the current On premises Environment and estimate AWS migration cost help to create a business case.

Mobilize Phase - ( Goal is to Discover resources and to create a detailed migration Plan )
Application Discovery Service - Discover all the Application resources that are connected ex Web server + database - Also it also can help to decide right compute sizing base on raw data using installing Agent in the onprem server or using agentless discover in VMware

AWS Migration Hub - Central dashboard Visibility and tracking the status is which applications are ready, in progress, or completed.

Migrate and Modernize Phase - (Goal is to move workloads to AWS and improve applications)
AWS Application Migration Service - Migrates applications from on-premises or cloud environments to AWS. Also you can improve your application ex your application database is always going high utilization due to many workloads and using a mysql database you can modernize change to RDS and add a Read Replica to lessen Main/Primary RDS DB utilization.


---
AWS CAF - Plan, Migrate, and Optimize - Help Organization why and how move to AWS Cloud

**Business Capabilities**

 Business 
 
 People
 
 Governance
 

**Technical Capabilities**

Platform

Security

Operations

---

Well-Architected Framework ( WAF) - Help design secure, reliable,high-performing, cost-efficient workloads. (QUALITY)

Operational Excellence

Security

Reliability

Perfomance Efficiency

Cost Optimization

Sustainability



---
CAF: Used before migration (planning & readiness)

Well-Architected: Used during/after build

CAF focuses on organizational cloud readiness

Well-Architected focuses on workload design

CAF = strategy, Well-Architected = execution

If the question mentions people, policies, governance = CAF

If it mentions architecture, performance, reliability = Well-Architected

---
The 7's R

Rehost (Lift and Shift)
Move applications as-is from on-premises servers to cloud VMs, with minimal or no changes.
Often chosen for speed and basic scalability/elasticity.

Relocate
Move existing virtual machines or containers from on-premises to the cloud without changing the architecture (e.g., VMware workloads moved to cloud VMware services).

Replatform (Lift, Tinker, and Shift)
Make small optimizations to take advantage of cloud services without changing the core application code.
Example: migrating MySQL on-prem to Amazon RDS or Aurora.

Refactor (Re-architect)
Redesign and rewrite the application to be cloud-native.
Chosen when on-prem limitations, lack of features, scalability needs, or long-term optimization justify the effort.

Repurchase (Drop and Shop)
Replace the existing application with a SaaS or managed solution that offers better features, cost, or efficiency.

Retain
Keep the application on-premises (or as-is) due to compliance, latency, cost, or strategic reasons.

Retire
Decommission applications that are no longer used or provide business value.


---

 Database Migration

 AWS Database Migration Service (DMS) - Migrate/move or replicate Onprem to AWS or AZURE/GCP to AWS with minimal downtime.

 AWS Schema Conversion Tool - Convert/transform database schemas and application/database code from one database engine to another (ex, MySQL to Amazon RDS, Oracle DB to Aurora).
 
---

 Transferring Data Online
 
---
 AWS DataSync - is Simi to OneDrive you can Move or SYNC From onprem to Cloud. also you can sched when the sync or move will be done.
 
---
 AWS Transfer Family - Simi to Shared Drive = EFS using a Protocol FTP Port 21
 
---
 Direct Connect - Move files from on prem to Cloud without using the internet/WIFI because Direct connect is like a lan cable connecting Onprem to Cloud. Instead of upload to cloud it just  Moving Files from onprem to cloud.
 
---
 Transferring Data Offline 
 
---

 Snowballs - Simi to Portable HDD/SSD send a hardware copy to onprem then deliver the Portable Storage to Cloud and paste.
 
---



# Module 13 - Well Architected Solutions



---

AWS CodeBuild - This where you type codes and test if their an error to be able to package your code to test and when passed it will be deployment ready. Simi to Github/ Visual Studio Code | CodeBuild = cloud compiler + test runner, like NetBeans or Visual Studio, but fully automated and scalable.

---

AWS CodePipeline - Used for CI/CD. Continious Integration Continious Deployment. Simi to Weekly Downtime summary Excel See below Stages for example.

Source Stage: Developer pushes the updated Excel file with Macros or Formula to Sharepoint

Build Stage (CodeBuild): CodeBuild runs a script to validate the macros or formula and ensure the Excel file works correctly.

Test Stage: Input data tests check for errors in formulas or macros.

Deploy Stage (CodeDeploy or S3): If the data in the excel file works without error and data is accurate Deploy via Sending via Email.

---

AWS Xray - Debuging Tool to know where the error located and giving solutions bestie of a developer. Simi to EUCT but a tool | Scenario is Excel with macro files experiencing Not responsing state. Using AWS xray it can trace or identify the problem and help to troubleshoot the issue. The issue is having a bottleneck in RAM have a high CPU but 4 gb of ram that cannot handle big excel file with Macros AWS xray Helps decide solutions Ex. Increase RAM,Optimize macro code,Split large Excel files.

---

AWS AppSync - Combine/connects multiple data to a single GraphQL API. Simi to Montly Top Performers - The creteria is 1. Total Ticket From Marval - Total Number of Call from Genesys APPSync  combining multiple DATA from different Application into One GraphQL API so Developers can Filter the Data or query the ranking of Top performers. It means insted of having 2 API to get the DATA from Marval API and GENESYS API AppSync replaces multiple APIs with one GraphQL API.

---

AWS Amplify - All in one Tool that help to create an APP and AWS AMplify will automatically code and connects the configurations of each like Front end Backend to Database. Simi to Creating an Character in a game You will choose your characters Apperance ( Front End) Character behavior ( Back end ) Knowledge or brain ( Database) you will just choose and AWS Amplify will handle the codes and configuration and Hosting.

Amplify Studio is a builder where you can design your app’s data, UI, and login using drag-and-drop instead of writing code.

Example of Steps on creating an APP

---

# 🧩 AWS Amplify Studio – No-Code UI (Visual Walkthrough)

## Example: **Employee CRUD App (No Coding)**



---

## 🔹 Step 1: Create an Amplify App

1. Go to **AWS Console**
2. Open **AWS Amplify**
3. Click **“New App” → “Build an App”**
4. Choose **Web App**
5. Connect GitHub (or skip for now)

👉 This creates your Amplify project.

---

## 🔹 Step 2: Open Amplify Studio

* Inside your Amplify app
* Click **“Launch Studio”**

👉 You now see a **visual design screen**, not code.

---

## 🔹 Step 3: Create Data Model (No Code)

1. Go to **Data → Models**
2. Click **Create Model**
3. Example:

| Field      | Type   |
| ---------- | ------ |
| name       | String |
| department | String |
| role       | String |

Click **Save and Deploy**

👉 Amplify automatically creates:

* Database
* CRUD APIs

**No SQL. No server setup.**

---

## 🔹 Step 4: Enable Authentication (1 Click)

1. Go to **Authentication**
2. Enable **Username / Email login**
3. Save

👉 Login & signup pages are auto-generated.

---

## 🔹 Step 5: Build UI with Drag & Drop

1. Go to **UI Library**
2. Click **Create Form**
3. Choose **Employee model**
4. Select **Create / Update Form**
5. Click **Save**

Amplify auto-creates:

* Input forms
* Tables
* Buttons

👉 Like dragging controls in **WinForms / Power Apps**.

---

## 🔹 Step 6: Preview the App

* Click **Preview**
* You see:

  * Login page
  * Employee form
  * Employee list

👉 Fully working CRUD app.

---

## 🔹 Step 7: Sync to Code (Optional)

* Amplify generates **React code automatically**
* Developers can customize later

👉 No-code → low-code → full-code path.

---

Amazon Connect – Cloud-based contact center service Simi to  Genesys Cloud that handles inbound and outbound calls, , call queues, and agent routing using AWS (no on-prem servers). But more versatile because you can ADD an AI like Amazon Lex you will interact with AI  and Polly to convert text to Speech .

---
Amazon Simple Email Service (Amazon SES) – Cloud-based service to send and receive emails securely, reliably, and at scale without managing mail servers. Simi to Outlook + Exchange but your own manage you can set an firewall what will gonna block example Spam and phising mails. Outlook Part (Email Client) Exchange Part (Email Server / Backend)

---

Amazon AppStream 2.0 - Simi to remote desktop but browser based (no need to install app like quickassist) and only for a Single APP example only Gooogle chrome you can just remote the chrome it self you cannot click outside chrome.

---

WorkSpaces - Simi to Remote Desktop you can access all the remote desktop features. same na same and need to install the app 

---

Amazon WorkSpaces Secure Browser - Simi to PSHR that is internaly hosted local network like you can access only infront of HR or other whitelisted IPs. Highly isolated, secure browser session


---


AWS IOT Core - Managed cloud service that securely connects, manages, and collects data from Internet of Things (IoT) devices, allowing apps to interact with devices in real time. Simi to Skydatacenter Temperature monitoring it collect room temp Data and display to monitoring in real time. 

---

AWS Well-Architected Tool 

| Pillar                     | Meaning                                           | SIMI                                                            | Easy Example                                                                          |
| -------------------------- | ------------------------------------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Operational Excellence** | Make sure your app runs smoothly and is monitored | Like **Event Viewer + Task Scheduler** checking logs & tasks    | EC2 server auto-patches and backups run on time; alerts if something fails            |
| **Security**               | Keep data and apps safe                           | Like **Group Policy + Windows Defender + BitLocker**            | Only authorized users can access S3 files; MFA required; data encrypted               |
| **Reliability**            | Keep apps available even if something breaks      | Like **RAID + Shadow Copies + UPS backup**                      | RDS Multi-AZ ensures DB fails over automatically; EC2 auto-recovers if server crashes |
| **Performance Efficiency** | Use computing resources smartly                   | Like **Task Manager & Resource Monitor checking CPU/RAM**       | Auto-scale EC2 servers when web traffic spikes; use CloudFront caching                |
| **Cost Optimization**      | Avoid wasting money                               | Like **Turning off idle VMs or uninstalling unused software**   | Stop unused EC2 instances; delete old snapshots; use cheaper spot instances           |
| **Sustainability**         | Reduce energy and resource waste                  | Like **Shutting down PCs after work hours to save electricity** | Use smaller instance sizes; consolidate workloads to fewer servers                    |


---

AWS Well-Architected Tool - Give you enchament or suggestion to improve base in the six pillars. Simi to my thinking always have an idea to automate things for the better and convenient.

---



