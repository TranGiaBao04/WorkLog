---
title: "Week 2 Worklog"
date: 2026-01-12
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives

This week focused on building a solid foundation in access management and network architecture on AWS, covering both basic and more advanced concepts. The main objectives included:

- **IAM Management**:
  - Creating users and groups
  - Attaching appropriate policies
  - Creating and using IAM Roles
  - Practicing **Switch Role**

- **Mastering VPC Networking**:
  - Understanding the overall VPC architecture
  - Comparing **Security Groups and Network ACLs**
  - Preparing the network environment for EC2

- **Deploying EC2**:
  - Launching EC2 instances within a subnet
  - Configuring Security Groups
  - Connecting via SSH using a Key Pair

- **Configuring Hybrid DNS with Route 53 Resolver**:
  - Creating a Key Pair
  - Configuring Security Groups
  - Setting up DNS:
    - Creating an Outbound Endpoint
    - Creating Resolver Rules
    - Creating an Inbound Endpoint
  - Cleaning up resources after completion

- **Setting up VPC Peering**:
  - Learning how Peering works
  - Using CloudFormation to provision infrastructure
  - Creating Security Groups and EC2 instances
  - Updating Network ACLs
  - Establishing the Peering Connection
  - Updating Route Tables
  - Enabling Cross-Peer DNS

- **Deploying AWS Transit Gateway**:
  - Creating a Transit Gateway
  - Creating attachments for VPCs
  - Configuring Route Tables for the Transit Gateway
  - Updating the Route Tables of the VPCs

---

### Work Overview

| Day | Task                                                                                                                                                                          | Start Date | Completion Date | Reference Materials                                                  |
| :-: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------: | :-------------: | -------------------------------------------------------------------- |
|  1  | **Basic IAM & EC2**:<br>- Creating Users and Groups<br>- Attaching Policies<br>- Creating Roles and practicing Switch Role<br>- Launching EC2 and connecting via SSH          | 12/01/2026 |   12/01/2026    | [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj/) |
|  2  | **VPC Networking**:<br>- Understanding VPC fundamentals<br>- Comparing Security Groups and NACLs<br>- Preparing subnets for EC2                                               | 13/01/2026 |   13/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |
|  3  | **Hybrid DNS (Route 53 Resolver)**:<br>- Creating a Key Pair<br>- Configuring Security Groups<br>- Creating Outbound / Inbound Endpoints<br>- Creating Resolver Rules         | 14/01/2026 |   14/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |
|  4  | **VPC Peering**:<br>- Building a CloudFormation Template<br>- Creating EC2 instances and Security Groups<br>- Setting up Peering<br>- Updating Route Tables<br>- Enabling DNS | 15/01/2026 |   15/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |
|  5  | **Transit Gateway**:<br>- Creating a TGW<br>- Attaching VPCs to the TGW<br>- Configuring Route Tables                                                                         | 16/01/2026 |   16/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |

---

### Achievements

#### What Was Completed

- Gained a better understanding of **IAM** authorization mechanisms and successfully practiced **Switch Role**
- Built a solid understanding of **VPC** architecture and Security Group-based protection
- Successfully deployed **EC2** instances and connected to them through SSH
- Successfully configured **Hybrid DNS** with Route 53 Resolver
- Set up **VPC Peering** to connect the Dev and Staging environments
- Deployed **AWS Transit Gateway** as a central hub for connecting multiple VPCs
- Became familiar with **Infrastructure as Code** through CloudFormation
- Performed **resource cleanup** after completing the labs

#### Architecture Summary

- **IAM Authorization Model**: Users → Groups → Policies → Roles
- **VPC Networking**:
  - Security Group: instance-level control
  - NACL: subnet-level control
- **Hybrid DNS**:
  - On-premises ↔ AWS via Route 53 Resolver
- **Network Connectivity**:
  - VPC Peering: point-to-point connection
  - Transit Gateway: hub-and-spoke model
