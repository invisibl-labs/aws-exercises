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




