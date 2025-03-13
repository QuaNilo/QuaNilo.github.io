---
title: "EasyInterview(Softinsa IBM)"
excerpt: "AI-powered microservices platform that automates technical interview question generation, validation, and management for HR professionals.<br/>"
collection: portfolio
---

## Overview

**Easy Interview** is a microservices-based platform designed to automate and enhance the interview process using AI. The system generates, validates, and manages technical interview questions, allowing HR professionals and hiring managers to create customized assessments for candidates. The platform ensures consistency and efficiency in the interview process while leveraging AI for question generation.

<div style="text-align: center; margin-bottom: 20px;">
    <h3>Back Office Portal User Flow</h3>
    <img src="/images/backofficeportal-flow.png" alt="Back Office Portal Workflow" style="width: 100%; max-width: 800px; margin-bottom: 20px;">
</div>


<div style="text-align: center; margin-bottom: 20px;">
    <h3>Front Office Portal User Flow</h3>
    <img src="/images/frontofficeportal.png" alt="Front Office Portal Interface" style="width: 100%; max-width: 800px;">
</div>
## Key Features

- **Automated Question Generation:** Uses OpenAI's LLM models to create relevant interview questions.
- **Question Validation:** Ensures no duplicate or irrelevant questions are generated through keyword overlap detection.
- **Test Management:** HR teams can create, approve, and distribute technical tests.
- **Real-Time Collaboration:** Uses WebSockets for real-time updates on question generation and test editing.
- **Secure Authentication:** Implements Azure AD B2C for Single Sign-On (SSO) and role-based access control.

## System Architecture

<div style="text-align: center; margin-bottom: 20px;">
    <h3>System Architecture - 6 Microservices</h3>
    <img src="/images/diagram.png" alt="System Architecture - 6 Microservices" style="width: 100%; max-width: 800px; margin-bottom: 20px;">
</div>

The platform follows a **microservices architecture**, consisting of the following key components:

1. **Back Office Agent**
   - Generates interview questions using AI models.
   - Prevents duplicate questions by analyzing keyword similarity.
   - Sends real-time updates to the Back Office Portal.

2. **Back Office API**
   - Manages authentication, authorization, and user access.
   - Provides data to the Back Office Portal and handles API requests.
   - Queues requests for AI-generated questions.

3. **Back Office Portal**
   - User interface for HR professionals to manage interview questions.
   - Allows question approval, editing, and test creation.
   - Sends test invitations via email.

4. **Front Office API**
   - Validates candidate test submissions.
   - Grades tests and stores results in the database.

5. **Front Office Portal**
   - User interface for candidates to complete their assigned tests.
   - Implements a timer-based test submission system.

6. **MongoDB Database**
   - Stores validated and unvalidated questions, test records, and user data.

## Technologies Used

- **Frontend:** React, JavaScript
- **Backend:** Python, Flask, FastAPI
- **Database:** MongoDB
- **Authentication & Security:** Azure AD B2C (Single Sign-On)
- **Real-Time Communication:** WebSockets (Flask-SocketIO)
- **DevOps & Deployment:** Docker, Kubernetes, Nginx, Rancher, Bitbucket Pipelines
- **AI & NLP:** OpenAI's LLM models for question generation

## Deployment & Infrastructure

- **Docker & Docker Compose:** Used for containerizing microservices.
- **Kubernetes & Rancher:** Manages deployments and scaling.
- **Bitbucket Pipelines:** Automates CI/CD for testing and deployment.
- **Nginx:** Acts as a reverse proxy for frontend applications.

## Usage Workflow

1. HR users log in using Azure AD SSO.
2. They generate interview questions using AI.
3. The system validates and filters duplicate questions.
4. HR professionals review, edit, and approve questions.
5. Tests are created and assigned to candidates.
6. Candidates complete tests via the Front Office Portal.
7. The system grades responses and provides results.

# DevOps Workflow - Easy Interview

## Overview

The **DevOps pipeline** for Easy Interview ensures smooth CI/CD integration, security checks, and efficient deployment of the microservices architecture. It utilizes **Harbor** for container registry, **SonarQube** for code quality analysis, and **Rancher** for Kubernetes-based deployment, ensuring reliability and scalability.

## Workflow Summary

1. **Code Development & Versioning**  
   - Developers push code to **Bitbucket** following a structured branching strategy.
   - Pull requests undergo reviews before merging into the main branch.

2. **CI/CD Pipeline Execution**  
   - Bitbucket Pipelines automates the build, test, and deployment process.
   - Unit tests are executed to ensure code integrity.
   - **SonarQube** performs static code analysis for security vulnerabilities and code quality.

3. **Containerization & Image Management**  
   - Docker images are built for each microservice.
   - Images are pushed to **Harbor**, an enterprise-grade container registry.

4. **Kubernetes Deployment via Rancher**  
   - Kubernetes manages service orchestration and scaling.
   - **Rancher** simplifies cluster management and deployment updates.

## Technologies Used

- **Containerization & Image Management**
  - **Docker:** Packages microservices into lightweight containers.
  - **Harbor:** Secure container registry for storing and managing Docker images.

- **CI/CD & Code Quality**
  - **Bitbucket Pipelines:** Automates testing, builds, and deployments.
  - **SonarQube:** Scans code for vulnerabilities and quality issues before deployment.

- **Deployment & Orchestration**
  - **Kubernetes:** Manages containerized workloads and scaling.
  - **Rancher:** Provides a user-friendly interface for Kubernetes management.

## Deployment Flow

1. **Code Push & Pipeline Trigger**
   - Developers push changes to Bitbucket.
   - Pipelines run tests and **SonarQube** analysis.

2. **Build & Image Deployment**
   - If tests pass, Docker images are built and pushed to **Harbor**.

3. **Kubernetes Deployment**
   - Rancher retrieves images from Harbor.
   - Services are updated within Kubernetes clusters.

## Security & Compliance

- **Access Control:** Harbor ensures image security with role-based access control (RBAC).
- **Static Code Analysis:** SonarQube enforces secure coding practices.
- **Automated Deployments:** Rancher facilitates seamless updates with minimal downtime.



## Impact

The **Easy Interview** platform enhances the hiring process by reducing manual work, ensuring consistency in interviews, and leveraging AI to generate high-quality technical questions. It streamlines recruitment by providing structured assessments with automated grading.
