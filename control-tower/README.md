# Control Tower Setup

## What is Control Tower?

It is an AWS service that facilitates creation and management of secure multi-account AWS environment based on many security best practices standards.

If there are multiple accounts and distributed teams working on several applications, it is very difficult to setup and manage accounts and security compliances. Control Tower solves this problem.

## Benefits of Control Tower

* Can automate the setup of AWS environment with best practices blueprints for multi-account structure, IAM and account provisioning workflow
* Easily setup and manage rules for security and compliance
* Identity management using AWS SSO directory and access management using AWS SSO
* Enables central logging and security audits across multiple accounts 
* Enables guardrails for governance and prevention of non-compliant resource deployment
* Uses AWS CloudFormation for baseline, AWS Organizations Service Control Policy to prevent config changes and AWS Config rules to detect non-compliance
* Provides visibility through the dashboard. Gives status of the resources that don’t comply with the rules enabled through preventive and detective guardrails.

## Pre-requisite Understanding

* AWS Organizations
* AWS Landing Zone
* Guardrails, Service control policies and Config rules
* Basic Understanding of IAM, User, Group and Role
* Basic understanding of AWS Single Sign-On

## Key Features

- Landing zone automation along with best practices blueprints
- Guardrails for policy management
- Account factory for user account management
- Built in identity and access management
- Pre-configured log archive and audit access to accounts
- Dashboard for visibility and actions
- Built-in monitoring and notifications
- Centralized billing for all accounts

## Key Steps

* Set up an AWS Landing Zone
* Establish guardrails
* Automate compliant account provisioning 
* Centralized Identity and Access Management

### Step-1
From AWS Control Tower console, click on 'Setup Landing Zone'

<img width="1240" alt="Screenshot 2022-06-20 at 10 27 13 PM" src="https://user-images.githubusercontent.com/104984822/174810828-372fd2a0-8e0c-4883-ac76-5f9fd7ebb9f0.png">

### Step-2
Select a home region for the control tower.

<img width="1060" alt="Screenshot 2022-06-20 at 10 28 41 PM" src="https://user-images.githubusercontent.com/104984822/174811877-2649a066-af68-44a3-81eb-87ad9c2e4600.png">

### Step-3
Select additional regions to add governance. All guardrails will be applied to accounts in the additional regions.
<img width="917" alt="Screenshot 2022-06-20 at 10 28 55 PM" src="https://user-images.githubusercontent.com/104984822/174812273-70c0d219-3e80-4ea0-9517-f73f82b818b8.png">

### Step-4
Configure organizational unit. This is required for Security OU to store shared accounts for log archive and audits and Sandbox OU is optional for storing other accounts for dev, staging or prod environments. Additional OUs can be created after the landing zone setup.

<img width="1062" alt="Screenshot 2022-06-20 at 10 29 37 PM" src="https://user-images.githubusercontent.com/104984822/174814025-25eba5fc-4ae2-4c09-814a-594064be9957.png">

### Step-5
Configure shared accounts for log archive and audit accounts. Provide unique email ids for these accounts.
<img width="1044" alt="Screenshot 2022-06-20 at 10 37 51 PM" src="https://user-images.githubusercontent.com/104984822/174814375-aa7d0922-efd8-4c92-aa1a-f972b0c394a3.png">

<img width="793" alt="Screenshot 2022-06-20 at 10 38 27 PM" src="https://user-images.githubusercontent.com/104984822/174814430-4115660b-5624-41ec-a686-2b1ab16c2da5.png">

### Step-6
Review the details and setup landing zone
<img width="1067" alt="Screenshot 2022-06-20 at 10 56 15 PM" src="https://user-images.githubusercontent.com/104984822/174814545-f2e28148-b07f-4d05-b010-43183c30e85a.png">

<img width="762" alt="Screenshot 2022-06-20 at 10 59 27 PM" src="https://user-images.githubusercontent.com/104984822/174814618-37dd2de3-c12b-43f7-aec4-3ea90dbfeab1.png">

### Step-7
Wait for the setup to be completed. It takes about 15-20 mins to complete.
<img width="1384" alt="Screenshot 2022-06-20 at 11 00 14 PM" src="https://user-images.githubusercontent.com/104984822/174814769-5bb43939-60b4-4d28-9a7a-ea4b33e60399.png">

### Step-8
Once the setup is completed, should see the results with the details of all the resources created
<img width="1385" alt="Screenshot 2022-06-21 at 12 43 42 PM" src="https://user-images.githubusercontent.com/104984822/174814942-55238c31-c925-4ac8-ba05-a4a4d3047c4d.png">

Verify if the OUs, shared accounts, and guardrails are setup
<img width="1393" alt="Screenshot 2022-06-21 at 11 54 47 AM" src="https://user-images.githubusercontent.com/104984822/174815796-ade2f512-c8b5-45fe-a01a-08ec023a5d3d.png">

Start the exercises after completing the setup.

## Exercise 1

* Create a new Organizational Unit 'Dev' under Root
* Add 1 member account using the 'Create Account' feature in Account Factory
* Associate the account with 'Dev' OU
* Check if the mandatory guardrails are enabled for the new OU and Account
* Check the status of the OU. Should be 'Compliant'


## Exercise 2

* Create a new Organizational Unit 'Staging' under Root
* Add 1 member account using the 'Create Account' feature in Account Factory
* Associate the account with 'Staging' OU
* Check if the mandatory guardrails are enabled for the new OU and Account
* Check the status of the OU. Should be 'Compliant'
* Add a new guardrail to 'Dev' OU
* Search for 'Detect whether any Amazon VPC subnets are assigned a public IP address' and open the details
* Enable this guardrail for 'Dev' OU
* Verify if this guardrail is added to 'Dev' OU
* Check if the status of the OU is 'Compliant.
* Navigate back to 'Staging' OU and check if the guardrail is added. Should not see this guardrail






