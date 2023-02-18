# Week 0 — Billing and Architecture

W0 – Material 1 - Live Streamed Video
Project Scenario
Join first day of startup, called crudder something like microblogging or engineer.
Tony is interviewed me, and tell who's gonna be involved as a team and so on.
The founder name is Sam.
The CTO team mentioned about microblogging, platform, expiring post, community, trust and safety users.
Tony mentioned that cruddur will be the first ephemeral? (It's a time limited content) microblogging platform, it's an expiring post social media platform.
It's like twitter w/ dumpster fire? and snapchat but more community focused that aim to share a lot of content but it won't track your privacy.
Hope that it will attract users include a lot of transactions.
Investor spent a lot of money to hire marketing team, but the platform not quite there yet. So they hire me to it the ground running pretty quickly.
Marketing team generating a ton of content right now, they still not decided who the target market is, is it going to be high school student, university student, or only young professionals, or expanded to the other user types and how they authenticate age and if they limit age content and things like that and marketing team also want me to get involved that might be a bit technical also.
Tony explains that the app is targeted to, pitched it to busy professionals students and everyone who doesn’t want to maintain a permanent presence online. This means that we want to reduce the amount of trust and safety issues that the company have to deal with the limiting users personal information that’s might leaked out online. The hope is also to improve user experience by having a more engaging and interesting thing than just following and lurking around.
Tony want to tell you about tech app. Tony explain about two months ago Sam has an idea, he had a wireframe so Tony hire a web development firm to take the wireframe and turn into mock up but there’s some code and stuff out there. Have an AWS account setup.
The investor called AB.co, funded six months of my salary, a fractional CTO , this office space and that whole marketing team. Fractional CTO is somebody who is partly committed to your company but also split their time between consulting gig that they do on their own and advise other startup, also CTO is a part time teacher too, so CTO have a teacher mentality.
So I ask Tony,
What is my authority?
Tony explains that I have the choice to work with dev firm, created all start over or do kind of a mix and match of both components or existing parts.
So the CTO splitting their time between teaching and advising startup. Sam is here and Aaron is fractional CTO talking about projection and planning. You get introduced to them and they talk fast, and mentioned about ORM (Object-Relational Mapping) about monolithic application, functional components or functional requirements.
Aaron mentioned about a good technical roadmap, they have kind of a plan of Sprints and agile methodologies that you’ll divide out this work and do it in chunks. So they have roadmap but it’s all up to me how to deliver things in certain increments.
What is monolithic application?
Well it’s like all-in-one application where you have the entirely of your app stack in one place. UI, business logic, data access layer all in one place. The opposite one what we’re trying to do here name as microservice architecture. Microservice architecture is decoupling all of the components and making them interoperable and reusable parts so I could reuse the parts from UI to different function and services. So it will be easier to moved part and reuse it for later use.
So the goal from the entire company and with microservices is to offload as much that complexity to the cloud as possible. So avoid the monolith and go toward the microservices.
I should have use monolithic as below,
•	User Interface
•	Business Logic
•	Data Access
So separate data based on the category, so it wont go down in case something goes wrong on one and another.
We are using AWS as microservices and think that each different AWS account as different microservices that can stick together.
Investors chime in to the talking and say that investors funded six months of salary and have a budget for infrastructure make as low as possible or cost efficient.
Aaron talk about iron triangle of project management. This essentially is a budget timeline to have more focus on which area.
 
If focusing more to the quality, then it would cost more on the cost and timeframe to produce.
The requirements, the front end is Js using React, and the backend is Python using Flask. There is an API, noSQL or SQL databases on ORM.

Notes to self,
•	Ephemeral first micro-blogging platform
•	Fractional CTO
•	Partly developed app – keep or rebuild?
•	How to monetize the platform
•	Frontend = Js using React
•	Backend = Python using Flask
•	API only
•	Be careful of budget
•	Microservices not monolith
•	User content (upload?)
•	Users – College students, younger students, professionals
o	User validation?
o	Age limit?
•	AWS
o	What services? Containers?
o	Set up budget monitoring
•	User engagement
•	Technical report due to investors
o	Architecture
o	Budget
o	Ongoing cost estimate

User Persona
•	Tony – continuity and context
•	Web dev group = current state
•	Investors = cost and timing
•	CTO = technical requirements and future state

Lesson learned
•	Not all context is relevant
•	No true “greenfield”
•	Manage time and effort
•	Trade offs for all projects
•	Learn, iterate, and show back

W0 – M2 - AWS Pricing Basics and Free Tier
By: Chirag Nayyar

Topics
•	AWS Bill Walkthrough (Free Tier Usage)
•	Billing Alert (CloudWatch Alarm & Budget)
•	Cost Explorer
•	Calculate AWS Estimates Cost of Service
•	Check AWS Credits (If Have a Voucher)
•	Cost Allocation Tags
•	Free Forever vs Free For 12 Months

Assign the billing to IAM user so it can see the billing data. To know the billing data, need to be a root user.
The Billing Path -> AWS Billing Dashboard
AWS Free Tier (will show the usage)
To setup billing alert, there are 2 different methods which are old method and new method.
•	For old method,
o	Preferences -> Billing preferences: Tick on PDF Invoice by email.
o	At Cost Management Preferences Tick Receive Free Tier Usage Alerts and fill the email.
o	Save preferences.
•	For new method,
o	At Billing preferences: Click Manage Billing Alerts and will redirect to CloudWatch page.
o	Click on Alarms -> In Alarm and Click Create Alarm. 
o	At Metric options, click Select Metric -> Billing -> Total Estimated Charge -> Select Method.
o	At Specify metric and conditions, change the Metric name as desired, i.e. AWS Bootcamp Billing Alert.
o	At Specify metric and conditions, adjust the amount billing to be alert, i.e. $10 will alerting when it near to $10. Next.
o	At Configure Actions, if there’s no SNS topic config before then create one and fill the email address to be alerted. Click add topic and Next.
o	At Add name and description, for Alarm name rename as desired. I.e. Billing Alert.
Utilize AWS Budgets.
•	Click on Budgets and click create budget.
•	At Templates -new, click on Monthly cost budget. 
•	Change the name of Budget, i/e/ My AWS Bootcamp Budget.
•	Set the budget, I.e $10.
•	Fill email recipients with targeted email.
•	Save the config.

Different between AWS budget and alarm is that alarm represents only the amount have been charged. But for budget, it can alarm based on forecasted charges, which can give a head up to figure out before hit excessive bill usage.

Cost Allocation Tags.
The function of this feature is to differentiate if there are multiple use of resources that deploy infrastructure that need to be track in terms of cost. I.e. at the bootcamp, there is a production_app and dev_app then create tags to be track on billing console.

Cost Explorer.
To track how much the services plan with 

Credits.
If there is a credit, redeem voucher there.

AWS Pricing Calculator.
To know how much the AWS cost before to deploy.

W0 – Material 3 - Security Considerations
By: Ashish Rajan

What’s the goal the cyber security in an organization?
To identity and inform on any technical risk that the business maybe exposed to.

What is cloud security?
Cybersecurity that protects the data, applications, and services associated with cloud environments from both external and internal security threats.

Why care about cloud security?
•	Reducing impact of breach
•	Protecting networks, applications, services in cloud environments against malicious data theft
•	Reducing the human error responsible for data leaks

Why cloud security requires practice?
•	Complexity
•	Always chasing our tail with new services announced through the year
•	Bad hackers are improving their game

The step.
1.	STEP ONE – Add MFA to Root User
Why enable MFA for Root Account?
Root user is the most powerful user in AWS environment with access to creating users. Incase of compromise happen, this account is the same as domain admin in cloud world = game over.

Sign in to the console
From Resources or search for IAM (Identity Access Management)
At Identity and Access Management (IAM), Security Credentials and Assign for MFA
Add identity in Device Name, use MFA device such as authenticator app, secure usb and hardware TOTP token. Follow the instructions/
2.	STEP TWO – Create an Organization Unit
Organization unit used to group multiple AWS account that have different purposes which user have. It helps manages security policies, billing policies, cost policies, and many more in one central account.
The root access should not be having any application and only use to create organizational unit, and underneath create another AWS account as a standalone. There is no cost to use organizational unit.

Sign in to the console
From Resources or search for AWS Organizations
Click Create an Organization
Under Organizational Structure, tick box which user want to create the organization unit
Click drop down button Actions on the right panel and click Create New
Fill the name of organizational unit and tags unit

At this case, we create 2 different organizational unit.
1.	Active Account
2.	Standby Account
At the larger organizational unit, when create a multiple AWS account need some time to be active. So organization usually register and make it on standby account until when needed they move it to the active account organizational unit.
Organization also made unit name at their organization discretion, some only use 2 different organizational which are active and standby and some use name of different department.
3.	STEP THREE – Enable AWS Cloud Trail
It’s auditing function on AWS platform, which everything you do is being recorded on AWS log cloud files.

Sign in to the console
From Resources or search for Cloud Trail
Click Create a Trail
Name the Trail Log Bucket (only lowercase)
Name the Tags as your desired, i.e. AuditLog and the value as ChatGPT
(The option below may show up if the organizational unit has a more user in it)
At Choose Log Events, event type by default only for management events. When the organization become larger then there’s an option for Data Events and Insight Events.
4.	STEP FOUR – Create IAM Users
Identity Access Management is user management who have credential login to access their AWS account under the same organizational unit. AWS has 3 different role of users, which are root user, system users, and federated users. Always apply MFA for all users and set up the privileges for each users.
Root users:
System users:
Federated users:

Sign in to the console
From Resources or search for IAM
Click Users and set up the name of the users and follow the instructions
(!!! On security practices, root account will not be use and only use the desired account on daily basis !!!)
When setup finish, it will show the credentials login of the user creates
Go to login page and setup like having AWS first time such as setting MFA, and so on.
5.	STEP FIVE – Create AWS IAM Roles
IAM Roles and IAM Policies itself is different, there are two types of IAM roles and IAM policies which provide by AWS. The differences between those two is IAM roles is a permission to what can or can’t do in AWS account and to differentiate between roles and policies of the users, and for IAM policies it can be attached to a group of user, individuals, or admin users.

Sign in to the console
From Resources or search for IAM
Click Roles and you may see some roles on the list
(by default, you may see a different roles has been assigned on AWS roles list. But for security purposes at the first time create the roles make it very simple.)
To create a new role, click create role on the right button
At Trusted Entity Type, select AWS Service and checkmark the EC2 or Lambda depend on the user need
For the permissions, find AdministratorAccess to get admin access for the user role
At Role Details, name the role as desired. I.e. Admin_Role_ChatGPT
At Role Details, name the tag as desired. I.e. Tags = Role and Value = ChatGPT
Click create

For the Policies, Ashish mentioned about ReadOnly = SecurityAudit, then for the configuration walkthrough.
Sign in to the console
From Resources or search for IAM
(you may skip 2 steps above if still in the same page after editing roles level)
Click Policies and search for SecurityAudit on the policies list
Select SecurityAudit and click Attach under Actions dropdown button
Assign the name of users / roles / groups and click create

Another policies recommend to implement is using User Group.
Sign in to the console
From Resources or search for IAM
(you may skip 2 steps above if still in the same page after editing policies)
Click User Groups, click Create Group Button on the right side
Give a group name and add the users to the group and attach permission as desired. I.e. User A and B grouped to Engineering Group and assign policy as AmazonEC2FullAccess
Create group

The point is for the beginning give different group of access based on their level.
Users = A list of user created under the same AWS account
Roles = Permissions that can be assigned to an actual of resources which basically an AWS services
Policies = Can be assigned to a roles or users or a group of users so can regulate much easier for larger organizations
6.	STEP SIX – Enable AWS Organization SCP
Understand the region vs availability zone vs global services concepts in service and shared responsibility between the user and AWS.
Sign in to the console
From Resources or search for SCP (Search Control Policy) right under IAM or under AWS Organization
(at this point, we manage to under AWS Organization)
Click policies and select Service control policies (by default it’s still disable. So get it enable to use the services)

What policies should I make besides of what AWS has already create in default after enabling the feature?
Ashish has a repo to which best policies to be implemented on https://github.com/hashishrajan/aws-scp-best-practice-policies
When apply the policies from the repo, make sure to convert the YAML format to JSON and applied it to the AWS Tags

Summary Security Best Practices
1.	Data protection & residency In accordance to security policy
2.	Identity & access management with least privilege
3.	Governance & compliance of AWS services being used
o	Global vs regional services
o	Compliant services
4.	Shared responsibility of threat detection
5.	Incident response plans to include cloud
