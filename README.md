AWS Cloud Practioner Essentials

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

Business Capabilities

 Business 
 People
 Governance

Technical Capabilities

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

Rehost - Lift and Shift - Move as is (onprem Servers to VMs ) Might due to more scalability elasticity.

Relocate - Already VMs or Container from on Prem changing to Cloud.

Replatform - Lift, Thinker and Shift - Upgrade to more efficient but same Code ex. mysql DB to RDS | Aurora.

Refactor - Rearchitecting - ex Onprem to Cloud due to not possible or lack of featues or resources. 

Repurchase - Drop and Shop - Considering better offers benefits.

Retain - Stays where it lays

Retire - No longer being used


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



