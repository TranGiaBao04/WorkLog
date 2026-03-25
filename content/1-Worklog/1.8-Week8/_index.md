---
title: "Week 8 Worklog"
date: 2026-03-02
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives

This week marked the beginning of the actual implementation phase of the project. The team started developing the first core parts of the system while integrating essential AWS services into the overall architecture. The focus was not only on writing code, but also on connecting the different layers of the application into a functional workflow.

- **Starting practical project implementation**:
  - Developing the core features of the system
  - Connecting the frontend, backend, and database into a unified structure
  - Establishing the initial technical foundation for the next development stages

- **Integrating AWS services into the system**:
  - Using **Amazon EC2** as the application hosting environment
  - Integrating **Amazon RDS** for relational data management
  - Using **Amazon S3** to store static files and user resources
  - Applying **AWS Map** to support map visualization and location-based data

- **Testing and refinement**:
  - Verifying the interaction flow between integrated components
  - Fixing issues that appeared during the integration process
  - Improving the project structure to make future development more manageable

---

### Work Overview

| Day | Task                                                                                                                       | Start Date | Completion Date | Reference Materials                                 |
| :-: | -------------------------------------------------------------------------------------------------------------------------- | :--------: | :-------------: | --------------------------------------------------- |
|  1  | **Project Development Setup**:<br>- Initializing the project structure<br>- Starting implementation of core features       | 02/03/2026 |   02/03/2026    | Internal                                            |
|  2  | **Backend and Database Integration**:<br>- Connecting the backend to RDS<br>- Handling basic data operations               | 03/03/2026 |   03/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  3  | **S3 Integration**:<br>- Setting up S3<br>- Uploading and managing static assets                                           | 04/03/2026 |   04/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  4  | **Map Service Integration**:<br>- Connecting AWS Map<br>- Displaying location data on the interface                        | 05/03/2026 |   05/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  5  | **EC2 Deployment and Testing**:<br>- Deploying the application to EC2<br>- Testing the full integration flow of the system | 06/03/2026 |   06/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |

---

### Achievements

#### What Was Completed

- Moved the project from the planning stage into **actual development**
- Built the initial integration foundation between the **frontend, backend, and database**
- Successfully connected **Amazon RDS** for data storage
- Configured and used **Amazon S3** for static asset storage
- Integrated **AWS Map** to support location display features
- Deployed a test version of the application on **Amazon EC2**
- Verified the system’s basic end-to-end flow after integration

#### Architecture Summary

- **Compute**: Amazon EC2 serves as the runtime environment for the application
- **Database**: Amazon RDS stores the system’s relational data
- **Storage**: Amazon S3 is used for file storage and static assets
- **Map Service**: AWS Map supports map rendering and location-based data
- **Application Flow**: Frontend ↔ Backend ↔ AWS Services
