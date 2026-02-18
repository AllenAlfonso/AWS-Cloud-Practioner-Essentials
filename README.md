AWS Cloud Practioner Essentials

---
# Module 2 -Compute in the Cloud


---

# Amazon EC2 – Flexible, On-Demand Servers

Amazon EC2 is like having **virtual servers in the cloud** that you can launch, scale, and stop anytime. It’s **faster, more flexible, and cheaper** than managing physical on-premises servers because you **pay only for what you use**.


EC2 = **Rent servers by the hour → scale up/down → stop when done**

---

# Why EC2 is Useful

* Launch **as many or as few servers** as needed
* Configure **security, networking, and storage**
* Scale automatically for **high traffic or heavy compute tasks**
* Reduce **upfront hardware costs and delays**


EC2 = No waiting for delivery → build & run apps quickly

---

# On-Premises vs Cloud

### On-Premises Challenges

* Buy hardware upfront → expensive
* Wait for delivery & setup → slow
* Fixed capacity → hard to handle spikes in demand
* Maintain everything yourself → time-consuming


On-prem = Buy, install, wait, hope capacity matches demand

---

### Cloud Benefits with EC2

* Launch servers in **minutes**
* **Pay only while running**
* **Scale up/down** instantly based on traffic
* Stop servers when not needed → save money


EC2 = Instant servers → pay per use → scale anytime

---

# How EC2 Works

AWS manages all the **complex infrastructure**, giving you **on-demand compute power**. You just:

1. Request an EC2 instance
2. Choose size, OS, and region
3. Launch and start using within **minutes**


EC2 = **Click → Server ready → Run your app

---

# **Key Takeaway**

EC2 gives you **flexibility, speed, and cost efficiency** compared to traditional servers. It’s perfect when you want **fast deployment, easy scaling, and pay-as-you-go** without managing physical hardware.


---

# **EC2 Instance Types – Pick the Right Server**

Amazon EC2 gives you **different types of instances** depending on what your workload needs. Whether it’s a simple website or heavy data processing, there’s an instance for it.

---

### 1. General Purpose

* Balanced CPU, memory, and networking
* Good for **web servers, small apps, and dev/test environments**

 All-rounder → decent at everything

---

### 2. Compute Optimized

* High CPU performance
* Great for **batch processing, gaming servers, or high-performance computing**

 CPU power → for number-crunching apps

---

### 3. Memory Optimized

* Lots of RAM
* Best for **databases, in-memory caches, and analytics**

 Memory-heavy → RAM hungry apps

---

### 4. Accelerated Computing

* Uses **GPU or FPGA** for special workloads
* Perfect for **AI/ML training, simulations, or graphics rendering**

 GPU power → smart or graphics-heavy apps

---

### 5. Storage Optimized

* High disk throughput and IOPS
* Ideal for **big data, NoSQL databases, and large file storage**

 Disk-focused → data-heavy apps

---

# **Key Takeaway**

Instance types = **Pick the right tool for the job** → CPU, RAM, GPU, or storage optimized depending on your workload.

** tip:**

* General = all-rounder
* Compute = CPU heavy
* Memory = RAM heavy
* Accelerated = GPU/FPGA
* Storage = Disk heavy



---

# Interacting with AWS Services – How You Control AWS

Everything you do in AWS works through **APIs (Application Programming Interfaces)**. You can interact with AWS services using **three main ways**:

---

### 1. AWS Management Console

* Web-based dashboard (browser access)
* Easy point-and-click interface
* Best for **beginners, admins, and manual configuration**


Console = **AWS website control panel**

---

### **2. AWS CLI (Command Line Interface)**

* Use commands in terminal / PowerShell
* Faster automation & scripting
* Best for **sysadmins, automation, scripting**


CLI = **Command prompt for AWS**

---

### 3. AWS SDK (Software Development Kit)

* Use programming languages like Python, Java, C#, Node.js
* Build apps that directly talk to AWS


SDK = **Programmatic access for developers**

---

# **Simple View**

| Method  | Best For                  |
| ------- | ------------------------- |
| Console | Manual setup & monitoring |
| CLI     | Automation & scripting    |
| SDK     | Application development   |

---

# Compute & Shared Responsibility Model

AWS follows the **Shared Responsibility Model**, meaning **security is shared between AWS and the customer**.

### AWS Responsibility – Security *of* the Cloud

AWS handles:

* Data center security
* Physical servers
* Networking infrastructure
* Hardware
* Global infrastructure


AWS = **Secures the building & hardware**

---

### **Customer Responsibility – Security *in* the Cloud**

You handle:

* OS patching
* Applications
* Data security
* IAM users & permissions
* Firewall rules (Security Groups, NACLs)

**Simi:**
Customer = **Secures what’s inside the server**

---

# **EC2 Example – Unmanaged Service**

Amazon EC2 is an **unmanaged compute service**, meaning:

You must manage:

* Operating system updates
* Firewall rules
* Security patches
* Installed software
* Server hardening

AWS only manages:

* Physical servers
* Network
* Storage hardware
* Datacenter


EC2 = **You rent a server → you manage everything inside**

---

# **Key Takeaway (Exam Friendly)**

AWS secures the **cloud infrastructure**, while customers secure **applications, data, and access inside the cloud**. Unmanaged services like EC2 require **full customer responsibility** for OS patches, and security configuration.



---

# **Amazon Machine Image (AMI) – Server Template**

An AMI is a **pre-built server template** that contains everything needed to launch an EC2 instance. Instead of building a server from scratch every time, you can **reuse the same setup again and again**.


AMI = **Golden Image / Server Template / Clone of a server**

---

# **What’s Inside an AMI**

An AMI includes:

* Operating System (Windows / Linux)
* Storage configuration
* CPU architecture type
* Security permissions
* Pre-installed software & applications


AMI = **Complete ready-to-run server blueprint**

---

# **How You Can Use AMIs**

### **1. Create Your Own AMI**

* Build your own customized server
* Install apps, security patches, tools
* Save it as an AMI
* Launch multiple identical servers


Custom AMI = **Build once → deploy many**

---

### **2. Use AWS Pre-Built AMIs**

* Ready-made Windows & Linux images
* Already optimized and maintained by AWS


AWS AMI = **Plug-and-play servers**

---

### **3. Use AWS Marketplace AMIs**

* Pre-installed licensed software from vendors
* Firewalls, monitoring tools, databases, apps


Marketplace AMI = **Pre-installed enterprise software servers**

---

# Why AMIs Are Important 

AMIs make deployment **fast, consistent, and error-free**.

* Same configuration every time
* No manual setup mistakes
* Faster scaling
* Easier testing & troubleshooting


AMI = **Clone server → same setup → no surprises**

---

# Real-Life Example

Company builds a **secure, patched Windows Server with antivirus + monitoring tools**, saves it as AMI → launches **100 identical EC2 servers** for production.

---

# **Key Takeaway**

AMI is a **server blueprint** that helps you **deploy identical EC2 servers quickly, consistently, and at scale**.

---



# AWS EC2 Pricing Options 

AWS gives you **multiple pricing models** so you can **match cost with your workload pattern**. Choosing the right option helps **reduce cloud cost and avoid wasting money**.

Pricing options = **Choose how you want to pay for servers**

---

# **Main EC2 Pricing Types**

---

### **1. On-Demand Instances – Pay As You Go**

* No long-term commitment
* Pay only when the instance is running
* Highest flexibility, highest price

**Good for:**

* Testing
* Short-term workloads
* Unpredictable traffic

On-Demand = **Rent per hour → stop anytime**

---

### **2. Reserved Instances (RI) – Long-Term Discount**

* Commit for **1 or 3 years**
* Get **up to 75% discount**
* Best for **steady workloads**

**Good for:**

* Databases
* Production systems
* Always-on servers

RI = **Prepay → big discount**

---

### **3. Spot Instances – Cheapest but Unstable**

* Use **unused AWS capacity**
* Up to **90% cheaper**
* Can be **terminated anytime**

**Good for:**

* Batch jobs
* CI/CD pipelines
* Big data processing
* Non-critical workloads

Spot = **Cheap but can disappear anytime**

---

### **4. Savings Plans – Flexible Long-Term Discount**

* Commit to **hourly compute usage**
* Works across:

  * EC2
  * Fargate
  * Lambda
  * SageMaker
* Up to **72% discount**

**Good for:**

* Predictable workloads
* Mixed compute environments

Savings Plan = **Commit to usage, not instance type**

---

### **5. Dedicated Hosts – Full Physical Server**

* You get **entire physical server**
* Full control over placement
* Required for **compliance & licensing**

**Good for:**

* Regulated industries
* BYOL (Bring Your Own License)
* Strict compliance needs

Dedicated Host = **Entire server only for you**

---

### **6. Dedicated Instances – Isolated but No Server Control**

* Physically isolated from others
* No control which server you run on

**Good for:**

* Compliance needing isolation but not full control

**Simi:**
Dedicated Instance = **Private room inside shared building**

---

# **Dedicated Host vs Dedicated Instance **

| Feature         | Dedicated Host | Dedicated Instance |
| --------------- | -------------- | ------------------ |
| Physical Server | 100% yours     | Shared             |
| Server Control  | Full control   | No control         |
| Isolation       | Yes            | Yes                |
| Cost            | Higher         | Lower              |

Dedicated Host = **Own house**


Dedicated Instance = **Private apartment**

---

# **Advanced Cost Optimization Options**

---

### **Savings Plans**

**Good for:** Predictable workloads

* Commit to **hourly compute spend**
* Flexible across services
* Big long-term discounts


Savings Plan = **Monthly subscription discount**

---

### **Capacity Reservations**

**Good for:** Mission-critical workloads

* Reserve capacity in a **specific AZ**
* Ensures servers are **always available**
* Charged even if unused

Capacity Reservation = **Seat reservation in airplane**

---

### **Reserved Instance Flexibility**

**Good for:** Stable workloads

* Discount applies **across instance sizes & AZs**
* More flexibility than fixed-size RIs

RI Flexibility = **Same family → automatic discount sharing**

---

# **Simple Cost Strategy **

| Workload               | Best Option                      |
| ---------------------- | -------------------------------- |
| Testing / short term   | On-Demand                        |
| Steady production      | Reserved Instance / Savings Plan |
| Batch / big data       | Spot                             |
| Compliance / licensing | Dedicated Host                   |
| Mission critical       | Capacity Reservation             |

---


AWS pricing options let you **balance flexibility, stability, and cost**, helping you **pay less while meeting performance and business needs**.

---


# **AWS EC2 Pricing – Discount & Savings Comparison **

| Pricing Model                       | Max Discount  | Commitment   | Most Savings When                       |                                  |
| ----------------------------------- | ------------- | ------------ | --------------------------------------- | -------------------------------- |
| **On-Demand**                       | **0%**        | None         | Short-term, testing                     | Pay as you go                    |
| **Spot Instances**                  | **Up to 90%** | None         | Flexible, interruptible jobs            | Cheapest but unstable            |
| **Standard Reserved Instance (RI)** | **Up to 75%** | 1 or 3 years | Fixed workload, long-running servers    | Prepay → biggest stable discount |
| **Convertible Reserved Instance**   | **Up to 54%** | 1 or 3 years | When flexibility is needed              | Change instance types later      |
| **Savings Plans – Compute**         | **Up to 72%** | 1 or 3 years | Mixed workloads, EC2 + Lambda + Fargate | Most flexible long-term          |
| **Savings Plans – EC2 Instance**    | **Up to 72%** | 1 or 3 years | Same instance family                    | Flexible but EC2-only            |
| **Dedicated Instances**             | ~0–10%        | None         | Isolation required                      | Private VM                       |
| **Dedicated Hosts**                 | ~0–10%        | None         | Compliance + licenses                   | Full physical server             |

---

# **Standard Reserved vs Savings Plans – Which Saves More?**

| Scenario                               | Best Choice                    | Why                            |
| -------------------------------------- | ------------------------------ | ------------------------------ |
| Fixed EC2 type, always running         | **Standard Reserved Instance** | **Highest EC2 discount (75%)** |
| Mixed EC2 sizes & regions              | **Savings Plans**              | More flexible                  |
| EC2 + Lambda + Fargate                 | **Compute Savings Plan**       | Cross-service discount         |
| Need to change instance families later | **Convertible RI**             | More flexibility               |
| Unpredictable workloads                | **On-Demand / Spot**           | No commitment                  |

---

# **Who Saves You More?**

👉 **Maximum stable discount:** **Standard RI (75%)**


👉 **Most flexible discount:** **Savings Plans (72%)**


👉 **Absolute cheapest:** **Spot (90%)**

---

Remember

> **Spot = 90% → RI = 75% → Savings Plans = 72% → On-Demand = 0%**

---

# Real-Life Example

Company has **24/7 database server running all year**
➡ Best choice = **Standard Reserved Instance** → **Save 75%**

Company runs **EC2 + Lambda + containers + mixed workloads**
➡ Best choice = **Compute Savings Plan** → **Save 72% with flexibility**

Company runs **batch jobs overnight only**
➡ Best choice = **Spot Instances** → **Save 90%**

---

# **Final Exam Tip**

If the question says:

* **Predictable / steady workload → RI or Savings Plan**

  
* **Cheapest possible → Spot**

  
* **No commitment → On-Demand**

  
* **Compliance / license → Dedicated Host**




---

# Module 3 - Exploring Compute Services

---


# AWS Responsibility Model 

AWS services are grouped based on **how much work AWS does vs how much you manage**.

👉 **More managed = less work for you**
👉 **Less managed = more control but more responsibility**

---

# Three Types of AWS Services

## 1️⃣ Unmanaged Services – You Manage Almost Everything

AWS manages:

* Data centers
* Physical servers
* Networking

You manage:

* OS installation
* Security patching
* Software setup
* Monitoring
* Scaling
* Application management


Bare metal / empty apartment → You build everything inside

### 🔹 Unmanaged AWS Services

* Amazon EC2
* Amazon EC2 Auto Scaling
* Amazon EBS
* Amazon VPC
* Elastic Load Balancer (ELB – classic setup)

---

## 2️⃣ Managed Services – Shared Responsibility

AWS manages:

* Infrastructure
* OS patching (mostly)
* Scaling
* High availability
* Backups

You manage:

* Application
* Configuration
* Security policies
* Users & permissions


Fully furnished apartment → **Less setup, less headache**

### 🔹 Managed AWS Services

* Amazon RDS
* Amazon Aurora
* Amazon ECS
* Amazon EKS
* AWS Elastic Beanstalk
* Amazon EMR
* Amazon Redshift
* Amazon OpenSearch
* Amazon MQ

---

## 3️⃣ Fully-Managed / Serverless – AWS Handles Almost Everything

AWS manages:

* Servers
* Scaling
* High availability
* Maintenance
* OS
* Infrastructure

You manage:

* Code
* Data
* Permissions


Hotel stay → **Just use the service, no maintenance**

### 🔹 Fully-Managed / Serverless AWS Services

* AWS Lambda
* Amazon DynamoDB
* Amazon S3
* Amazon CloudFront
* Amazon API Gateway
* AWS Step Functions
* Amazon SNS
* Amazon SQS
* AWS Fargate
* Amazon EventBridge

---

# Responsibility Comparison Table

| Type              | AWS Handles           | You Handle                     | Effort    |
| ----------------- | --------------------- | ------------------------------ | --------- |
| **Unmanaged**     | Hardware only         | OS + Security + Apps + Scaling | 🔴 High   |
| **Managed**       | Infra + OS + Scaling  | Config + App + Security        | 🟡 Medium |
| **Fully Managed** | Everything infra-side | Only code + access             | 🟢 Low    |

---

Remember

> EC2 = You build
>
> 
> RDS = AWS helps
>
> 
> Lambda = AWS does almost everything

---

# Real-Life Example

### Running a Website:

EC2 (Unmanaged)
→ You install OS → web server → patches → updates → backups

RDS (Managed)
→ AWS manages database engine, patching, backup

Lambda (Fully-managed)
→ You upload code → AWS runs it → auto scales → auto recovers

---

# Responsibility Diagram 

```
Unmanaged     →     Managed      →     Fully Managed
More Work     →     Balanced      →     Very Less Work
EC2           →     RDS           →     Lambda
```

---

# Exam Tip 

If AWS exam asks:

> Which service reduces operational overhead the most?

✅ **Answer: Fully-managed / Serverless services (like Lambda, DynamoDB)**

---



# AWS Lambda – Serverless Compute 

AWS Lambda is a **serverless compute service** that lets you run code **without creating or managing servers**. You just upload your code, set the trigger, and AWS will automatically handle **infrastructure, scaling, availability, and execution**.

You **only pay when your code runs**, billed per millisecond.

Simi:
Lambda is like **a smart automatic worker** — you give it a task, it runs it, and disappears when done. No servers to manage.

---

# How Lambda Works 

Event happens → Lambda triggers → Code runs → Task completed → Lambda stops → You only pay for execution time

**Triggers examples:**

* API Gateway (web requests)
* S3 upload
* DynamoDB update
* EventBridge (scheduled jobs)
* SNS / SQS messages

---

# How Long Can Lambda Run?

Maximum execution time: 15 minutes (900 seconds)



Lambda is designed for **short-running workloads**, not long-running tasks.



Lambda = **Microwave** → Fast jobs


EC2 / ECS = **Slow cooker** → Long jobs

---

# Lambda Execution Limits 

| Feature           | Limit           |
| ----------------- | --------------- |
| Max runtime       | **15 minutes**  |
| Min runtime       | Milliseconds    |
| Auto scaling      | Yes             |
| Server management | None            |
| Billing           | Per millisecond |

---

# **When Lambda is Perfect**

Use Lambda when tasks are:

* Short
* Event-driven
* On-demand
* Auto-scaling required

**Examples:**

* Image resizing after upload
* Login authentication logic
* API backend logic
* File processing
* Email notifications
* Automation scripts

---

# **When Lambda is NOT Ideal**

Avoid Lambda if:

* Task runs **more than 15 minutes**
* Heavy processing workloads
* Long batch processing
* Video rendering
* Big data workloads

Use instead:

* EC2
* ECS / EKS
* AWS Batch
* Step Functions + ECS

---

# Real-Life Example

### **Scenario: Image Upload System**

User uploads image → Lambda resizes image → Saves thumbnail → Done

Perfect use case ✔

---

### Scenario: Video Rendering (30 mins)

❌ Lambda → Timeout
✅ EC2 / AWS Batch → Correct choice

---

# Enterprise Design Tip 

If a process is long:

Use **Lambda + Step Functions**
→ Break big job into **small tasks**

---

# One-Liner 

> AWS Lambda is a serverless compute service for short, event-driven workloads with a maximum execution time of 15 minutes.

---


# Key Takeaways – Solving Deployment Challenges 

Containers are a smart way to package applications** together with all their needed files, libraries, and settings into **one portable unit**. This makes applications **secure, reliable, easy to move, and easy to scale

Simi:
Containers are like **packing your entire working PC setup into one folder**, so wherever you run it — laptop, server, or cloud — it behaves exactly the same.

---

# Containers vs Virtual Machines (VMs)

### Containers

* Lightweight
* Fast startup (seconds)
* Share the same OS
* Use fewer resources
* Easier to move and scale


Containers = Portable apps inside one folder

---

### Virtual Machines (VMs)

* Heavy
* Slower startup (minutes)
* Each VM runs a **full OS**
* Higher resource usage
* More complex to manage


VMs = Full PC inside a PC

---

### Simple Comparison

| Containers    | Virtual Machines |
| ------------- | ---------------- |
| Lightweight   | Heavy            |
| Fast startup  | Slow startup     |
| Share OS      | Separate OS      |
| Lower cost    | Higher cost      |
| Easy to scale | Harder to scale  |

---

# Why Containers Fix Deployment Problems

### **Problem Before Containers**

* App works in **Developer PC**
* Fails in **Test / Production**
* Different OS, libraries, or versions
* Hard to troubleshoot

---

### Solution with Containers

* Same environment everywhere
* No more **"It works on my PC" problem**
* Faster deployment
* Easier troubleshooting


Containers make Dev → Test → Prod environments identical

---

# Scaling Containers – Why Orchestration Is Needed

When applications grow, you might have:

* 10 containers → 100 → 1000 containers

Managing them manually becomes very hard.

This is where **orchestration tools** come in.

They automatically handle:

* Deployment
* Scaling
* Load balancing
* Restarting failed containers
* Monitoring


Orchestration tools = Traffic enforcer + auto manager for containers

---

# AWS Container Services 

AWS container tools fall into **3 main categories:**

1. **Orchestration** → ECS, EKS
2. **Registry (Image Storage)** → ECR
3. **Compute (Where containers run)** → EC2, Fargate

---

# **Amazon ECS – Elastic Container Service**

AWS-native container orchestration service.

Used to **run and manage Docker containers easily.**

---

### ECS Launch Types

### 1. ECS + EC2

* You manage EC2 servers
* Full control over OS and hardware
* More configuration
* More responsibility

Best for:
Companies needing **custom setups or special hardware**


Like owning your own servers

---

### 2. ECS + Fargate (Serverless)

* No server management
* AWS handles infrastructure
* Auto scaling
* Pay only for usage

Best for:
Startups, web apps, unpredictable workloads

Simi:
Like **renting a fully managed server automatically**

---

# Amazon EKS – Elastic Kubernetes Service

Fully managed **Kubernetes service on AWS**.

Used when you want **open-source Kubernetes power** with AWS infrastructure.

---

### EKS Launch Types

### 1. EKS + EC2

* Full infrastructure control
* Deep customization
* Best for complex enterprise workloads


Like **custom-built datacenter with Kubernetes**

---

### 2. EKS + Fargate

* Kubernetes + serverless
* No server management
* Fast scaling
* Lower ops overhead


Like Kubernetes without server headaches

---

# Amazon ECR – Elastic Container Registry

Where you store your container images.


Amazon ECR = **Docker Hub but inside AWS**

Used to:

* Push images
* Pull images
* Store versions
* Manage access

---

# AWS Fargate – Serverless Compute for Containers

Fargate is where containers actually run.

You do NOT:

* Create servers
* Patch OS
* Manage instances

You only:

* Deploy containers
* Pay for CPU + RAM used

Works with:

* ECS
* EKS


Fargate = Lambda for Containers

---

# Simple Architecture View

ECR → stores images
ECS / EKS → manages containers
Fargate → runs containers (serverless compute)

---

# Quick Exam Summary (High Value)

| Service | Purpose                            |
| ------- | ---------------------------------- |
| ECS     | AWS-native container orchestration |
| EKS     | Kubernetes orchestration           |
| ECR     | Container image registry           |
| Fargate | Serverless container compute       |

---

# One-Liner Summary

> Containers provide fast, consistent, portable deployments, while ECS, EKS, ECR, and Fargate allow AWS to run, manage, store, and scale containers easily without server management.

---



# Additional Compute Services

AWS also provides special-purpose compute services for different business needs — from easy web app deployment, batch processing, simple VPS hosting, to extending AWS into your on-prem datacenter.

Think of these as **ready-made tools for specific IT scenarios**, so you don’t always have to build everything from scratch.

---

# Elastic Beanstalk – Auto Web App Deployment Platform

Elastic Beanstalk is a **fully managed platform** where you just **upload your code**, and AWS automatically:

* Creates servers
* Sets up load balancers
* Handles scaling
* Monitors app health
* Manages deployments

You still get **full control of AWS resources**, but AWS removes most of the operational work.

Supports:** Java, .NET, Python, Node.js, PHP, Docker, etc.

Simi:
Elastic Beanstalk = **Upload code → AWS builds & runs everything for you**

Good for:

* Web applications
* REST APIs
* Mobile backend services
* Microservices
* Auto-scaling production apps

---

# AWS Batch – Large Job Processing System

AWS Batch is a **fully managed service for running big batch workloads**. It automatically:

* Schedules jobs
* Chooses compute size
* Scales servers up & down
* Optimizes resource usage

Simi:
AWS Batch = **Job scheduler + auto compute scaling for heavy workloads**

Good for:

* Scientific simulations
* Financial calculations
* Video rendering / media transcoding
* Big data processing
* Machine learning model training
* Genomics research

---

# Amazon Lightsail – Simple VPS Hosting

Lightsail is simple AWS hosting with predictable monthly pricing.

It provides:

* Virtual servers (VPS)
* Storage
* Databases
* Networking

All with **easy setup & simple dashboard**.

Simi:
Lightsail = **DigitalOcean / GoDaddy VPS but inside AWS**

Good for:

* Small business websites
* Low traffic web apps
* Blogs
* Dev & test environments
* Learning AWS

---

# AWS Outposts – AWS Inside Your Own Datacenter

Outposts is AWS hardware installed inside your own on-prem datacenter.

You get:

* AWS services
* Same AWS console
* Same APIs
* Same tools

But **running locally in your building**.

Simi:
Outposts = **AWS Cloud physically inside your office**

Good for:

* Low-latency workloads
* Local data processing
* Regulatory compliance
* Data residency requirements
* Hybrid cloud setups

---

Comparison Table

| Service           | What It Does             | Best For                  |
| ----------------- | ------------------------ | ------------------------- |
| Elastic Beanstalk | Auto deploy & scale apps | Web apps, APIs            |
| AWS Batch         | Run heavy batch jobs     | Big compute workloads     |
| Lightsail         | Simple VPS hosting       | Small websites & dev      |
| Outposts          | AWS in your datacenter   | Hybrid cloud & compliance |

---

# One-Line Summary 

> AWS provides Elastic Beanstalk for easy app deployment, AWS Batch for large job processing, Lightsail for simple VPS hosting, and Outposts for running AWS services inside on-premises environments.

---





---


# Module 4- Going Global


---

## How to Choose an AWS Region 

Choosing the right AWS Region is **very important** because it affects **performance, cost, compliance, and availability**.

**Think of it like:**
Choosing the best **data center location** for your servers based on **who uses it, legal rules, and cost.**

---

## **Main factors when choosing a Region**

### **1. Latency (Performance) – Closest to users = faster**

* Pick a Region **nearest to your users** for low delay.
* This improves **website speed, app response time, and user experience**.

**Example:**
Users in the Philippines → choose **Singapore (ap-southeast-1)** or **Jakarta (ap-southeast-3)**
Not US or Europe → too far = slow response

---

### **2. Cost – Prices vary by Region**

* Some Regions are **cheaper than others**.
* Data transfer, compute, and storage pricing **depends on Region**.

**Example:**
Singapore Region may cost more than Mumbai → choose cheaper region if latency is not critical.

---

### **3. Compliance & Data Residency – Legal requirements**

* Some countries require **data to stay inside their country**.
* You must choose a Region that **meets government or company compliance rules**.

**Example:**
Healthcare data → must stay in a specific country
Banking data → must follow regulatory requirements

---

### **4. Service Availability – Not all services exist in all Regions**

* Some AWS services or features **are not available in every Region**.
* Always check if the service you need is supported.

**Example:**
A new AI service may be available only in **US regions first**

---

### **5. High Availability & Disaster Recovery**

* Choose Regions that allow **multi-AZ setups**
* For DR: choose **another Region far away**

**Example:**
Primary: Singapore
DR: Tokyo or Sydney

---

## Example

A company with users in Asia:

* Choose **Singapore Region**
* Why?

  * Low latency
  * Meets compliance
  * Good service availability
  * Balanced cost

---

Remember

> **Choose AWS Region based on:**
> **Latency → Cost → Compliance → Services → DR strategy**

---




# Designing Highly Available Architectures

To build **reliable and always-online systems**, AWS allows you to deploy your resources across **multiple Regions and multiple Availability Zones (AZs)**.

**Think:**
Don’t put all your servers in one place — **spread them out** so if one fails, the others continue working.

---

## **Multi-Region & Multi-AZ Deployment**

* **Multi-Region** → Deploy resources in different geographic locations
* **Multi-AZ** → Deploy resources across multiple data centers inside the same Region

By doing this, you:

* Avoid **single point of failure**
* Improve **uptime**
* Keep applications **running even during failures**

**Example:**
If one data center goes down → traffic automatically moves to another → **users don’t notice downtime**

---

# **Why AWS Global Infrastructure is Powerful**

AWS is built to give **High Availability, Agility, and Elasticity**

Let’s break it down simply:

---

## **High Availability – Always Online**

**Meaning:**
Your system keeps running **even if parts fail**.

**In AWS:**
If one server, AZ, or even Region fails → **other resources automatically take over**

**Think:** Backup systems always ready.

---

## **Agility – Move Fast**

**Meaning:**
You can **deploy, change, and update systems quickly**.

**In AWS:**
You can launch servers, databases, and apps in **minutes instead of weeks**

**Think:** Fast setup + fast changes.

---

## **Elasticity – Auto Scale Up & Down**

**Meaning:**
Your system **automatically adjusts capacity** based on traffic.

**In AWS:**
More users → scale up
Less users → scale down

**Think:** You only use and pay for **what you actually need**

---

# **Edge Locations – Faster Access for Users**

Besides Regions and AZs, AWS also has **Edge Locations** around the world.

**Purpose:**
Deliver content **closer to users** → **faster loading → lower latency**

These locations are placed in major cities like:

* Atlanta, USA
* Shanghai, China
* and many more worldwide

They are mainly used by **Amazon CloudFront (CDN)** and networking services.

---

## **Simple example**

You host a website in Singapore.
A user from China accesses it:

Without Edge → request goes to Singapore → slower
With Edge → content served from Shanghai → **much faster**

---

Remember

> **Multi-Region + Multi-AZ = High Availability**
> **Edge Locations = Speed + Performance**



---


**CloudFormation** is a service that lets you **build and manage your AWS infrastructure using code instead of doing everything manually**.

You simply write a **template (script)** that describes what resources you want — like **EC2, VPC, subnets, load balancers, databases**, etc. Then **CloudFormation automatically creates, configures, and connects everything for you**.

**Think SIMI:**
Like **installing software using an installer script instead of clicking next-next manually**.

---

## **Why CloudFormation is useful**

* Automates infrastructure setup
* Reduces human error
* Makes deployments **fast, repeatable, and consistent**
* Easy to recreate environments (dev, test, prod)

---


Instead of:

* Manually creating VPC
* Creating subnets
* Creating EC2
* Configuring security groups

You:

* Write **1 template**
* Run CloudFormation
* AWS builds **everything automatically**

---

Remember

> **CloudFormation = Infrastructure as Code (IaC) for AWS**

---

# **How You Interact with AWS Resources**

To manage AWS services, you must use **AWS APIs**. You can interact with these APIs in multiple ways:

---

## **1. AWS Management Console (Web UI)**

* Browser-based interface
* Best for beginners
* Manual clicking

**Think:** AWS website dashboard

---

## **2. AWS CLI (Command Line Interface)**

* Terminal-based commands
* Faster automation
* Used by admins and engineers

**Think:** PowerShell / Linux terminal for AWS

---

## **3. AWS SDKs (Software Development Kits)**

* Use AWS inside your code (Python, Java, Node.js, etc.)
* Used in application development

**Think:** AWS inside your program

---

## **4. Infrastructure as Code (IaC) – CloudFormation**

* Automate full infrastructure deployment
* Best for **large environments and automation**

---

## **Simple Flow**

Console → Manual
CLI → Commands
SDK → Application
CloudFormation → Full automation

---

## **Real-Life Example**

Setting up 1 server manually → OK
Setting up **100 servers repeatedly** → Use **CloudFormation automation**

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



