---
title: "Proposal"
date: 2026-03-24
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# EV Charging Station Management System

## Intelligent Backend Platform for Charging Operations and Digital Payments

### 1. Executive Summary

The EV Charging Station Management System is a centralized backend platform designed to support the entire lifecycle of EV charging operations. The system covers core functionalities such as station discovery, slot management, booking creation and confirmation, charging session tracking, invoice generation, payment processing, and driver compliance management within a unified platform.

The system is deployed on a modern AWS Cloud architecture following a layered model (Edge Layer – Application Layer – Data Layer – Observability & Security), ensuring high performance, security, and scalability.

The architecture leverages CloudFront CDN combined with AWS WAF for content delivery and protection, Application Load Balancer with Auto Scaling Group for dynamic traffic handling, and Amazon RDS Multi-AZ for high availability of data. Additionally, services such as AWS Secrets Manager, KMS, CloudWatch, CloudTrail, and SES enhance security, monitoring, and operational reliability in a production environment.

This solution is suitable for large-scale EV systems requiring high availability, scalability, and enterprise-grade security.

---

### 2. Problem Statement

#### What are the current challenges?

With the rapid growth of the EV market, charging station management systems face several challenges:

- Difficulty scaling as user traffic increases
- System overload due to lack of load balancing
- Database acting as a single point of failure
- Lack of security layers (WAF, secrets management)
- Backend exposed directly to the Internet, increasing security risks
- Lack of monitoring and logging systems

#### Proposed Solution

The proposed solution is to build a production-ready backend system on AWS with the following architecture:

- Route 53 + CloudFront + WAF for the Edge Layer
- Amazon S3 for frontend storage (private with OAC)
- ALB + EC2 in private subnets + Auto Scaling for backend
- NAT Gateway for outbound traffic
- RDS Multi-AZ for database high availability
- Secrets Manager + KMS for security
- CloudWatch + CloudTrail for monitoring and auditing
- Amazon SES for email services
- AWS Systems Manager (SSM) for secure administration

---

### 3. Solution Architecture

The system is designed using a layered architecture deployed within a VPC across multiple Availability Zones to ensure high availability and scalability.

![EV Charging System Architecture](/images/2-Proposal/AWS-architecture.png)

#### AWS Architecture Flow

**(1) User → Internet**  
Users access the system via browser or client application.

**(2) Internet → Route 53**  
Route 53 resolves DNS and routes the request.

**(3) Route 53 → CloudFront + WAF**  
CloudFront delivers content, while WAF filters and protects against attacks.

**(4) Frontend → Amazon Location Service**  
Frontend requests map data for station visualization.

**(5) CloudFront → Amazon S3 (Frontend)**  
CloudFront retrieves static assets securely via Origin Access Control (OAC).

---

**(6) CloudFront → ALB**  
API requests are forwarded to the Application Load Balancer.

**(7) ALB → EC2 (Private Subnet - AZ1)**  
ALB distributes traffic to EC2 instances.

**(8) Auto Scaling Group (AZ1 ↔ AZ2)**  
EC2 instances scale automatically and run across multiple AZs.

---

**(9) EC2 → Amazon RDS (Primary/Standby)**  
Backend interacts with RDS Multi-AZ database.

---

**(10) EC2 → NAT Gateway → Internet**  
EC2 instances access external services (e.g., VNPay, third-party APIs).

**(11) EC2 (AZ2) → RDS**  
Secondary AZ ensures high availability and failover capability.

---

**(12) NAT Gateway → Internet Gateway**  
Outbound traffic is routed through Internet Gateway.

**(13) Internet Gateway → Internet**  
Allows communication with external systems.

---

### Data Layer

- Amazon RDS for SQL Server (Multi-AZ)
- No public access
- Automatic failover

---

### Observability & Security Layer

**(14) EC2 → Amazon SES**  
Send system emails (OTP, booking confirmation, notifications).

**(15) EC2 → AWS Secrets Manager + KMS**  
Retrieve secrets and decrypt sensitive data.

**(16) Admin → AWS Systems Manager (SSM)**  
Secure EC2 access without SSH.

**(17) Response → CloudFront → User**  
Response is returned to the end user.

---

| Component      | Service / Technology |
| -------------- | -------------------- |
| DNS            | Route 53             |
| CDN            | CloudFront           |
| Security       | WAF                  |
| Frontend       | S3                   |
| Backend        | EC2 (Private Subnet) |
| Load Balancing | ALB                  |
| Scaling        | Auto Scaling Group   |
| Database       | RDS Multi-AZ         |
| Monitoring     | CloudWatch           |
| Logging        | CloudTrail           |
| Secrets        | Secrets Manager      |
| Encryption     | KMS                  |
| Email          | SES                  |
| Admin Access   | AWS SSM              |

---

### 4. Technical Implementation

#### Business Logic Approach

The system uses a centralized backend architecture with Spring Boot and JWT-based authentication.

System flow:

1. User request → Route 53 → CloudFront
2. CloudFront checks WAF
3. CloudFront serves frontend from S3
4. API request → ALB → EC2
5. Backend verifies JWT
6. Backend processes business logic
7. Backend queries RDS
8. Backend calls external services via NAT Gateway
9. Backend sends emails via SES
10. Response returns via CloudFront → User

#### Technical Requirements

- Frontend: S3 + CloudFront
- Backend: Spring Boot (Java 17)
- Authentication: JWT
- Database: RDS SQL Server
- Load balancing: ALB
- Scaling: Auto Scaling
- Security: WAF + Secrets Manager + KMS
- Monitoring: CloudWatch + CloudTrail
- Email: SES
- Administration: AWS SSM

---

### 5. Implementation Plan

- Week 7–8: AWS architecture design + VPC setup
- Week 8–9: Backend + database development
- Week 9–10: Payment + email + map integration
- Week 10–11: Security, monitoring, and scaling setup
- Week 12: Production deployment

---

### 6. Cost Estimation

| Component  | Service             | Cost Level    |
| ---------- | ------------------- | ------------- |
| Frontend   | S3 + CloudFront     | Low           |
| Backend    | EC2 + ALB           | Medium        |
| Database   | RDS Multi-AZ        | Medium – High |
| Security   | WAF + KMS + Secrets | Low           |
| Monitoring | CloudWatch          | Low           |
| Email      | SES                 | Low           |

---

### 7. Risk Assessment

#### Risks

- System overload
- Payment failures
- Secret leakage
- Misconfiguration

#### Mitigation

- Auto Scaling
- Retry mechanisms
- Secrets Manager
- CloudWatch monitoring

---

### 8. Expected Outcomes

#### Technical Improvements

- High availability
- Secure architecture
- Scalable system
- Full monitoring capability

#### Long-term Value

- Production-ready system
- Easy scalability
- Improved user experience
