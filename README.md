# 🚀 MEAN Stack DevOps Assignment

This project demonstrates containerization, CI/CD automation, and cloud deployment of a full-stack **MEAN (MongoDB, Express, Angular, Node.js)** application.

The application has been fully Dockerized and deployed on an Ubuntu VM using Docker Compose with GitHub Actions CI/CD automation.

---

# 📌 Project Overview

This assignment includes:

- 🔹 Angular Frontend
- 🔹 Node.js + Express Backend
- 🔹 MongoDB Database
- 🔹 Docker containerization
- 🔹 Docker Compose deployment
- 🔹 GitHub Actions CI/CD pipeline
- 🔹 Nginx Reverse Proxy (Port 80)
- 🔹 Cloud Deployment on Ubuntu (AWS EC2)

---

# 🏗️ Architecture
User (Browser)
↓
Nginx (Port 80)
↓
Frontend (Angular Container)
↓
Backend (Node + Express Container)
↓
MongoDB (Docker Container)


---

# 🐳 Docker Configuration

## Backend Dockerfile
- Uses Node base image
- Installs dependencies
- Exposes port 8080
- Runs server.js

## Frontend Dockerfile
- Builds Angular app
- Uses Nginx to serve static files
- Exposes port 80

## MongoDB
- Official MongoDB Docker image
- Runs as a service inside Docker Compose

---

# ⚙️ Docker Compose Setup

The application is deployed using Docker Compose with three services:

- frontend
- backend
- mongo
☁️ Cloud Deployment (Ubuntu VM - AWS EC2)
Steps Performed

Created Ubuntu EC2 instance

Installed Docker

Installed Docker Compose

Pulled Docker images from Docker Hub

Deployed using docker-compose

Configured Nginx reverse proxy on port 80

Application is accessible via:

http://<EC2_PUBLIC_IP>
🔁 CI/CD Pipeline (GitHub Actions)

CI/CD is implemented using GitHub Actions.

Pipeline Workflow:

When code is pushed to the main branch:

Checkout code

Login to Docker Hub

Build backend Docker image

Build frontend Docker image

Push images to Docker Hub

SSH into EC2 server

Pull latest images

Restart containers automatically

Workflow file location:

.github/workflows/mean-ci-cd.yml


# 🛠️ Technologies Used

Angular

Node.js

Express

MongoDB

Docker

Docker Compose

GitHub Actions

Nginx

AWS EC2 (Ubuntu)


## 🔄 CI/CD Status

GitHub Actions workflow successfully builds and deploys on every push to main branch.
