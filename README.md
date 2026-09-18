# i-Computers DevOps Project

## 📌 Project Overview

This repository contains the DevOps configuration and automation files
used to deploy the i-Computers full-stack e-commerce application.

The project demonstrates a complete DevOps workflow by connecting
frontend, backend, CI/CD automation, containerization, Docker image
management, and cloud deployment practices.

The system was designed with separate repositories:

-   Frontend Repository - React Application
-   Backend Repository - Node.js / Express API
-   DevOps Repository - CI/CD and Deployment Configuration

------------------------------------------------------------------------

# 🏗️ DevOps Architecture

    Developer
        |
        |
    GitHub Repositories
        |
        |
    Jenkins Pipeline
        |
        |
    Install Dependencies
        |
        |
    Run Tests
        |
        |
    Build Docker Images
        |
        |
    Push Images to Docker Hub
        |
        |
    Docker Compose Deployment
        |
        |
    Production Server

------------------------------------------------------------------------

# 🛠️ Technologies Used

  Technology       Purpose
  ---------------- ------------------------------
  Jenkins          CI/CD automation
  Docker           Application containerization
  Docker Hub       Container image registry
  Docker Compose   Multi-container deployment
  GitHub           Source code management
  Linux Server     Application hosting

------------------------------------------------------------------------

# 📂 Repository Structure

    i-computers-devops
    │
    ├── Jenkinsfile
    │
    ├── docker-compose.yml
    │
    └── README.md

------------------------------------------------------------------------

# 🔄 Jenkins CI/CD Pipeline

The Jenkins pipeline automates the complete deployment workflow.

## Pipeline Stages

### 1. Checkout DevOps Repository

Jenkins downloads DevOps configuration files from GitHub.

------------------------------------------------------------------------

### 2. Clone Frontend Repository

The React frontend source code is cloned automatically.

------------------------------------------------------------------------

### 3. Clone Backend Repository

The Node.js backend source code is cloned automatically.

------------------------------------------------------------------------

### 4. Install Dependencies

Frontend:

    npm install

Backend:

    npm install

------------------------------------------------------------------------

### 5. Run Tests

Backend tests are executed during the pipeline.

------------------------------------------------------------------------

### 6. Build Docker Images

Docker images are created:

Frontend:

    gaurawawickramasinghe/icomputers-frontend:latest

Backend:

    gaurawawickramasinghe/icomputers-backend:latest

------------------------------------------------------------------------

### 7. Push Images to Docker Hub

After successful image creation, images are pushed to Docker Hub.

------------------------------------------------------------------------

### 8. Environment Configuration

Backend environment variables are securely added during deployment.

------------------------------------------------------------------------

### 9. Application Deployment

Docker Compose is used to deploy the application.

Commands executed:

    docker compose down

    docker compose pull

    docker compose up -d

------------------------------------------------------------------------

# 🐳 Docker Compose Configuration

The application consists of two containers.

## Frontend Container

Technology:

-   React
-   Nginx

Port:

    8080:80

------------------------------------------------------------------------

## Backend Container

Technology:

-   Node.js
-   Express.js

Port:

    3000:3000

------------------------------------------------------------------------

# 🚀 Deployment Workflow

    Code Changes
         |
         ↓
    GitHub Push
         |
         ↓
    Jenkins Trigger
         |
         ↓
    Dependency Installation
         |
         ↓
    Testing
         |
         ↓
    Docker Image Build
         |
         ↓
    Docker Hub Push
         |
         ↓
    Docker Compose Deployment
         |
         ↓
    Running Application

------------------------------------------------------------------------

# 🔐 Security Practices

Implemented:

-   Jenkins credential management
-   Docker Hub authentication using Jenkins credentials
-   Environment variable separation
-   Container isolation

Future improvements:

-   HTTPS with SSL certificates
-   Secret management tools
-   Container vulnerability scanning
-   Security monitoring

------------------------------------------------------------------------

# 📊 DevOps Implementation Status

  Component              Status
  ---------------------- -----------------------
  Git & GitHub           ✅ Completed
  Frontend Development   ✅ Completed
  Backend Development    ✅ Completed
  Application Testing    ✅ Completed
  Docker Images          ✅ Completed
  Jenkins Pipeline       ✅ Completed
  Docker Hub Registry    ✅ Completed
  Docker Compose         ✅ Completed
  Cloud Deployment       ✅ Completed
  Monitoring             ⏳ Future Improvement
  Kubernetes             ⏳ Future Improvement
  Advanced SecOps        ⏳ Future Improvement

------------------------------------------------------------------------

# 🎯 Skills Demonstrated

Through this project, I gained practical experience in:

-   CI/CD pipeline development
-   Jenkins automation
-   Docker containerization
-   Docker image management
-   Linux deployment workflow
-   Cloud application deployment
-   Infrastructure automation concepts
-   Production deployment practices

------------------------------------------------------------------------

# 👨‍💻 Author

**Gaurawa Mihiranga**

Computer Engineering Undergraduate

------------------------------------------------------------------------

# 📌 Project Type

Full Stack Application Deployment - DevOps Project
