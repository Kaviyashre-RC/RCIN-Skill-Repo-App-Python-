# RCIN Skill Repository App (Cloud-Native Backend)

A cloud-native, backend-driven Skill Repository Platform designed to centralize, manage, and analyze employee skills within an organization.

This project is a pro-code evolution of an internal low-code application built using Power Apps, re-engineered using modern backend technologies and Azure cloud services.

## Problem Statement

Organizations often lack a scalable and centralized system to:
* Track employee skills and proficiency levels
* Maintain consistent and validated skill data
* Enable real-time updates and visibility
* Support data-driven capability planning

Existing solutions (e.g., static forms or SharePoint lists) are:
* Manual and inefficient
* Inconsistent in data quality
* Not extensible for analytics or AI

## Objective
To build a production-ready backend system that:
* Enables structured skill management
* Supports approval workflows for new skills
* Provides insights into organizational skill distribution
* Is scalable, modular, and cloud-native
* Can be extended with AI capabilities

## System Overview
This project focuses on building a backend-first architecture, exposing REST APIs that can be consumed by any frontend or external system.

## Core Modules
1. Skill Master Management
2. User Skill Management
3. Skill Request & Approval Workflow
4. Admin Analytics
5. Notification & Scheduler

## Tech Stack
- Backend
- Python (FastAPI)
- Database
- PostgreSQL
- Cloud & Deployment
  - Microsoft Azure
  - Azure Container Apps
- Docker
- Infrastructure
- Bicep (Infrastructure as Code)
- Monitoring
  - Azure Monitor + Application Insights

## API Overview
+ Auth / User Context
  + GET /me → Get current user details

+ Skills (Master Data)
  + GET /skills → Fetch all skills
  + POST /skills → Create new skill
  + PUT /skills/{id} → Update skill
  + PATCH /skills/{id}/status → Activate/Deactivate
  
+ User Skills
  + GET /users/{id}/skills → Get user skills
  + POST /users/{id}/skills → Add skill
  + PUT /users/{id}/skills/{skillId} → Update proficiency
  + DELETE /users/{id}/skills/{skillId} → Remove skill

+ Skill Requests
  + POST /skill-requests → Request new skill
  + GET /skill-requests → View requests
  + PATCH /skill-requests/{id}/approve → Approve
  + PATCH /skill-requests/{id}/reject → Reject

+ Analytics
  + GET /analytics/skills/distribution → Skill distribution
  + GET /analytics/skills/{id}/users → Users per skill

## Development Approach
Current Phase
Backend API development using dummy/local data
Modular architecture (routes → services → repositories)
API contract-first development

## Cloud Architecture
* Azure Container Apps → Backend hosting
* Azure Database for PostgreSQL → Data storage
* Azure Container Registry → Image storage
* Azure Monitor → Logging and observability
* Infrastructure will be provisioned using Bicep templates for reproducibility.

## Future Enhancements
🔐 Azure Active Directory (Entra ID) integration <br>
⏰ Scheduled reminders using Azure Functions <br>
📊 Advanced analytics dashboards <br>
📄 Resume auto-generation from skills <br>
🤖 AI-based skill recommendations (Azure OpenAI / Foundry) <br>
📂 Certification upload and parsing <br>

