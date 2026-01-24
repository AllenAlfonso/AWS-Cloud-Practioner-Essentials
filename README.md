# AWS-Cloud-Practioner-Essentials
AWS Cloud Practioner Essentials


Module 12: Migrating to the AWS Cloud

---

Migration Phase

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

Transferring Data Online
---
AWS DataSync - is Simi to OneDrive you can Move or SYNC From onprem to Cloud. also you can sched when the sync or move will be done.
---
AWS Transfer Family - Simi to Shared Drive = EFS using a Protocol FTP Port 21
---
Direct Connect - Move files from on prem to Cloud without using the internet/WIFI because Direct connect is like a lan cable connecting Onprem to Cloud. Instead of upload to cloud it just Moving Files from onprem to cloud.
---
Transferring Data Offline 
---
Snowballs - Simi to Portable HDD/SSD send a hardware copy to onprem then deliver the Portable Storage to Cloud and paste.
---

Module 13 - Well Architected Solutions**

---

AWS CodeBuild - Simi to Visual Studio Code | CodeBuild = cloud compiler + test runner, like NetBeans or Visual Studio, but fully automated and scalable.

---

AWS CodePipeline - Simi to Weekly Downtime summary Excel

Source Stage: Developer pushes the updated Excel file with Macros or Formula to Sharepoint

Build Stage (CodeBuild): CodeBuild runs a script to validate the macros or formula and ensure the Excel file works correctly.

Test Stage: Input data tests check for errors in formulas or macros.

Deploy Stage (CodeDeploy or S3): If the data in the excel file works without error and data is accurate Deploy via Sending via Email.

---

AWS Xray - Simi to EUCT but a tool | Scenario is Excel with macro files experiencing Not responsing state. Using AWS xray it can trace or identify the problem and help to troubleshoot the issue. The issue is having a bottleneck in RAM have a high CPU but 4 gb of ram that cannot handle big excel file with Macros AWS xray Helps decide solutions Ex. Increase RAM,Optimize macro code,Split large Excel files.

---

AWS AppSync - Simi to Montly Top Performers - The creteria is 1. Total Ticket From Marval - Total Number of Call from Genesys APPSync  combining multiple DATA from different Application into One GraphQL API so Developers can Filter the Data or query the ranking of Top performers. It means insted of having 2 API to get the DATA from Marval API and GENESYS API AppSync replaces multiple APIs with one GraphQL API.

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

Amazon WorkSpaces Secure Browser - Simi to PSHR that is internaly hosted local network like you can access only infront of HR or other whitelisted IPs.


---



