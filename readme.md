# Auto Scaling Lab

## Overview

Demonstrate automatic scaling by CloudFormation to deploy an Apache web server that dynamically adjusts its capacity based on CPU load. When an instance exceeds a 50% CPU utilization threshold, the Auto Scaling Group (ASG) launches a new instance to distribute traffic. Each instance responds with its unique IP address and instance ID, verifying load distribution.

## Task 1: Auto Scaling Group (ASG)

#### a. Configuration:

- Minimum Capacity: 1 instance
- Desired Capacity: 1 instance
- Maximum Capacity: 3 instances

#### b. Scaling Policy:

- Trigger a scale-out action when the CPU utilization of an instance exceeds 50%.

## Task 2: Apache Web Server

#### a. Functionality:

- Display a message: "Hello from [IP Address] / [Instance ID]" for the instance serving the request
- Include an interactive button on the webpage that, when clicked, artificially stresses the CPU of the hosting instance.

## Task 3: Networking Setup

#### a. Private Subnet:

- Deploy the ASG within a private subnet to host the Apache web server instances securely

#### b. Public Subnet:

- Deploy an Application Load Balancer (ALB) in a public subnet using a round-robin algorithm to distribute incoming traffic across the instances

## Task 4: Deployment Automation

- a. Use an AWS CloudFormation Git Sync to deploy resources.
- b. The template will define all necessary resources (ASG, scaling policies, load balancer, subnets, etc.) and use EC2 User Data to install Apache Web Server and Web Application

## Screenshots

### Infrastructure Composer

<img width="959" alt="Image" src="https://github.com/user-attachments/assets/5050d80e-f341-42aa-ba3c-70c176ac182f" />

### Deployed ALB

<img width="959" alt="Image" src="https://github.com/user-attachments/assets/a61be273-3b89-4bc4-9fe4-5af2b0abe2f6" />

### Auto Scaling of EC2 on stress

<img width="959" alt="Image" src="https://github.com/user-attachments/assets/6b828249-33b9-4d9c-9399-790b96775022" />

### Pull Request from Git Sync

<img width="958" alt="Image" src="https://github.com/user-attachments/assets/31072c9a-ecc3-4ff3-a1aa-4ef34f313b43" />

### Git Synced Stack

<img width="959" alt="Image" src="https://github.com/user-attachments/assets/ab707501-b0db-48cb-a1f9-0c8834bf1cb7" />
