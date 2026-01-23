
AWS Cloud Practioner Essentials

Module 12: Migrating to the AWS Cloud

Migration Phase

Assess Phase > Mobilize Phase > Migrate and Modernize

Assess Phase - ( Goal is to know if migration is will be worth it )Migration Evaluator - Analyze the current On premises Environment and estimate AWS migration cost help to create a business case.

Mobilize Phase - ( Goal is to Discover resources and to create a detailed migration Plan ) Application Discovery Service - Discover all the Application resources that are connected ex Web server + database - Also it also can help to decide right compute sizing base on raw data using installing Agent in the onprem server or using agentless discover in VMware

AWS Migration Hub - Central dashboard Visibility and tracking the status is which applications are ready, in progress, or completed.

Migrate and Modernize Phase - (Goal is to move workloads to AWS and improve applications) AWS Application Migration Service - Migrates applications from on-premises or cloud environments to AWS. Also you can improve your application ex your application database is always going high utilization due to many workloads and using a mysql database you can modernize change to RDS and add a Read Replica to lessen Main/Primary RDS DB utilization.

AWS CAF - Plan, Migrate, and Optimize - Help Organization why and how move to AWS Cloud

Business Capabilities

Business People Governance

Technical Capabilities

Platform Security Operations

Well-Architected Framework ( WAF) - Help design secure, reliable,high-performing, cost-efficient workloads. (QUALITY)

Operational Excellence Security Reliability Perfomance Efficiency Cost Optimization Sustainability

CAF: Used before migration (planning & readiness)

Well-Architected: Used during/after build

CAF focuses on organizational cloud readiness

Well-Architected focuses on workload design

CAF = strategy, Well-Architected = execution

If the question mentions people, policies, governance = CAF

If it mentions architecture, performance, reliability = Well-Architected

The 7's R

Rehost - Lift and Shift - Move as is (onprem Servers to VMs ) Might due to more scalability elasticity.

Relocate - Already VMs or Container from on Prem changing to Cloud.

Replatform - Lift, Thinker and Shift - Upgrade to more efficient but same Code ex. mysql DB to RDS | Aurora.

Refactor - Rearchitecting - ex Onprem to Cloud due to not possible or lack of featues or resources.

Repurchase - Drop and Shop - Considering better offers benefits.

Retain - Stays where it lays

Retire - No longer being used

Database Migration

AWS Database Migration Service (DMS) - Migrate/move or replicate Onprem to AWS or AZURE/GCP to AWS with minimal downtime.

AWS Schema Conversion Tool - Convert/transform database schemas and application/database code from one database engine to another (ex, MySQL to Amazon RDS, Oracle DB to Aurora).

Transferring Data Online

AWS DataSync - is Simi to OneDrive you can Move or SYNC From onprem to Cloud. also you can sched when the sync or move will be done.

AWS Transfer Family - Simi to Shared Drive = EFS using a Protocol FTP Port 21

Direct Connect - Move files from on prem to Cloud without using the internet/WIFI because Direct connect is like a lan cable connecting Onprem to Cloud. Instead of upload to cloud it just Moving Files from onprem to cloud.

Transferring Data Offline

Snowballs - Simi to Portable HDD/SSD send a hardware copy to onprem then deliver the Portable Storage to Cloud and paste.

Module 13 - Well Architected Solutions

AWS CodeBuild - Simi to Visual Studio Code | CodeBuild = cloud compiler + test runner, like NetBeans or Visual Studio, but fully automated and scalable.

AWS CodePipeline - Simi to Weekly Downtime summary Excel

Source Stage: Developer pushes the updated Excel file with Macros or Formula to Sharepoint

Build Stage (CodeBuild): CodeBuild runs a script to validate the macros or formula and ensure the Excel file works correctly.

Test Stage: Input data tests check for errors in formulas or macros.

Deploy Stage (CodeDeploy or S3): If the data in the excel file works without error and data is accurate Deploy via Sending via Email.

AWS Xray - Simi to EUCT but a tool | Scenario is Excel with macro files experiencing Not responsing state. Using AWS xray it can trace or identify the problem and help to troubleshoot the issue. The issue is having a bottleneck in RAM have a high CPU but 4 gb of ram that cannot handle big excel file with Macros AWS xray Helps decide solutions Ex. Increase RAM,Optimize macro code,Split large Excel files.

AWS AppSync - Simi to Montly Top Performers - The creteria is 1. Total Ticket From Marval - Total Number of Call from Genesys APPSync combining multiple DATA from different Application into One GraphQL API so Developers can Filter the Data or query the ranking of Top performers. It means insted of having 2 API to get the DATA from Marval API and GENESYS API AppSync replaces multiple APIs with one GraphQL API.

AWS Amplify

Amazon Connect vs Genesys Cloud

Feature	Amazon Connect	Genesys Cloud
Type	Fully managed AWS cloud contact center	Fully managed Genesys cloud contact center
Setup	Quick setup via AWS, no servers	Subscription-based, quick cloud setup
Integration	Native AWS integration (Lambda, S3, Lex, Polly, AppSync)	Integrates with many CRMs, APIs, and third-party services
AI / Automation	Optional AWS AI (Lex for chatbots, Polly for voice)	Built-in AI features or integrations (chatbots, workforce management)
Customization	Flexible if you’re already in AWS ecosystem	Flexible but mainly inside Genesys ecosystem
Cost	Pay-as-you-go (per minute/call, per user optional)	Subscription-based (per user/month)
Genesys Cloud: Like a ready-made, subscription-based office phone system in the cloud. You log in, set up agents, and it works.

Amazon Connect: Like Genesys Cloud but built on AWS, with extra flexibility: you can hook into other AWS services, add AI chatbots, or automate things with Lambda.

Amazon Connect and Genesys Cloud are both cloud contact center solutions, but Amazon Connect is AWS-native and integrates deeply with AWS services, while Genesys Cloud is vendor-managed and more standalone.
