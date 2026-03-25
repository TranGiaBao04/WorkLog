---
title: "Week 4 Worklog"
date: 2026-01-26
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives

This week focused on operating the system in a more practical, production-ready manner. The main topics included automation, security, reliability, performance, and cost optimization based on the AWS Well-Architected Framework.

- **Operational Excellence**:
  - Automating tasks with AWS Lambda, such as shutting down EC2 instances and sending Slack notifications
  - Building a monitoring system with CloudWatch and Grafana
  - Managing EC2 resources through Tags
  - Automating operations with AWS Systems Manager

- **Security**:
  - Applying IAM Permission Boundaries to control and restrict permissions
  - Performing security checks with AWS Security Hub
  - Protecting applications using AWS WAF

- **Reliability**:
  - Setting up backup mechanisms with AWS Backup
  - Connecting VPCs through VPC Peering
  - Managing centralized network connectivity with Transit Gateway

- **Performance Efficiency**:
  - Containerizing applications with Docker and deploying them on ECS
  - Building a CI/CD pipeline with CodePipeline
  - Storing data with File Storage Gateway

- **Cost Optimization**:
  - Applying Savings Plans and Reserved Instances
  - Performing EC2 right-sizing
  - Monitoring and visualizing usage costs

---

### Work Overview

| Day | Task                                                                                                         | Start Date | Completion Date | Reference Materials                                 |
| :-: | ------------------------------------------------------------------------------------------------------------ | :--------: | :-------------: | --------------------------------------------------- |
|  1  | **Automation & Monitoring**:<br>- AWS Lambda<br>- CloudWatch + Grafana<br>- EC2 Tagging<br>- Systems Manager | 26/01/2026 |   26/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  2  | **Security**:<br>- IAM Permission Boundary<br>- Security Hub<br>- AWS WAF                                    | 27/01/2026 |   27/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  3  | **Reliability**:<br>- AWS Backup<br>- VPC Peering<br>- Transit Gateway                                       | 28/01/2026 |   28/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  4  | **Performance**:<br>- Docker + ECS<br>- CodePipeline<br>- File Storage Gateway                               | 29/01/2026 |   29/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  5  | **Cost Optimization**:<br>- Savings Plans<br>- Reserved Instances<br>- Cost Visualization                    | 30/01/2026 |   30/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |

---

### Achievements

#### What Was Completed

- Automated operational workflows:
  - Automatically shut down EC2 instances and sent notifications using Lambda
  - Built monitoring dashboards with CloudWatch and Grafana
  - Managed resources using Tags and Systems Manager

- Strengthened system security:
  - Applied **IAM Permission Boundaries**
  - Deployed **AWS WAF**
  - Performed security assessments with **Security Hub**

- Improved reliability:
  - Configured automatic backups with **AWS Backup**
  - Established stable network connectivity through **VPC Peering** and **Transit Gateway**

- Enhanced performance:
  - Deployed containerized applications using **Docker and ECS**
  - Built a **CI/CD** pipeline

- Optimized operational costs:
  - Applied **Savings Plans** and **Reserved Instances**
  - Performed **EC2 right-sizing**
  - Monitored and analyzed usage costs

#### Architecture Summary

- **Automation**: Lambda + Systems Manager
- **Monitoring**: CloudWatch + Grafana
- **Security**: IAM Boundary + WAF + Security Hub
- **Networking**: VPC Peering + Transit Gateway
- **Compute**: ECS (Docker containers)
- **CI/CD**: CodePipeline
- **Storage**: File Storage Gateway
- **Cost**: Savings Plans + Cost Monitoring
