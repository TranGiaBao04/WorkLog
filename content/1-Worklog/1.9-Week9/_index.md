---
title: "Week 9 Worklog"
date: 2026-03-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives

This week, the team focused on moving the project into a test deployment phase, performing end-to-end system validation, and addressing issues discovered during development and testing. The main goal was to make sure the application was stable enough for a demo or the next release stage.

- **Deploying the system to a test environment**:
  - Launching the application on EC2 to evaluate it in a more realistic environment
  - Setting up and aligning related services such as RDS, S3, and Map
  - Verifying communication across all system components

- **Testing the full system flow**:
  - Running tests on the main application features
  - Reviewing the interface and user experience
  - Confirming data consistency between the frontend and backend

- **Fixing issues and refining the system**:
  - Identifying and resolving bugs found during testing
  - Enhancing both performance and application stability

- **Finalizing the system for presentation**:
  - Ensuring the application runs smoothly
  - Preparing for the demo or the upcoming release phase

---

### Work Overview

| Day | Task                                                                                                 | Start Date | Completion Date | Reference Materials                                 |
| :-: | ---------------------------------------------------------------------------------------------------- | :--------: | :-------------: | --------------------------------------------------- |
|  1  | **Deployment Setup**:<br>- Deploying the application to EC2<br>- Configuring the runtime environment | 09/03/2026 |   09/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  2  | **System Testing**:<br>- Testing key features<br>- Checking the data flow                            | 10/03/2026 |   10/03/2026    | Internal                                            |
|  3  | **Bug Fixing**:<br>- Identifying and resolving issues<br>- Debugging the system                      | 11/03/2026 |   11/03/2026    | Internal                                            |
|  4  | **Optimization**:<br>- Refining the codebase<br>- Improving performance                              | 12/03/2026 |   12/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  5  | **Final Testing**:<br>- Rechecking the full system<br>- Preparing for the demo                       | 13/03/2026 |   13/03/2026    | Internal                                            |

---

### Achievements

#### What Was Completed

- Successfully deployed the test system on **Amazon EC2**
- Established stable integration with:
  - **Amazon RDS**
  - **Amazon S3**
  - **AWS Map**
- Verified the full flow of the application’s core features
- Detected and resolved issues encountered during testing
- Improved runtime performance and user experience
- Brought the system to a **demo-ready** state

#### Architecture Summary

- **Compute**: EC2 for application deployment and execution
- **Database**: RDS (SQL Server) for data storage
- **Storage**: S3 for static assets
- **Map**: AWS Map for location-based functionality
- **Flow**: Frontend → Backend → AWS Services
- **Stage**: Testing / Pre-production
