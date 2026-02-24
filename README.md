# 🚀 MEAN Stack DevOps Assignment

This project demonstrates containerization, CI/CD automation, and cloud deployment of a full-stack **MEAN (MongoDB, Express, Angular, Node.js)** application.

The application is Dockerized and deployed on an Ubuntu VM (AWS EC2) using Docker Compose with automated CI/CD via GitHub Actions.

---

# 📌 Project Overview

This project includes:

- Angular Frontend
- Node.js + Express Backend
- MongoDB Database
- Docker containerization
- Docker Compose deployment
- GitHub Actions CI/CD automation
- Nginx Reverse Proxy (Port 80)
- Cloud Deployment on AWS EC2 (Ubuntu)

---

# 🏗️ Architecture

```
User (Browser)
        ↓
Nginx (Port 80)
        ↓
Frontend (Angular - Docker Container)
        ↓
Backend (Node + Express - Docker Container)
        ↓
MongoDB (Docker Container)
```

---

# 🐳 Docker Configuration

## Backend
- Base Image: Node
- Exposes Port: 8080
- Runs: server.js

## Frontend
- Multi-stage build (Angular → Nginx)
- Exposes Port: 80

## MongoDB
- Official MongoDB Docker image
- Configured via Docker Compose

---

# ⚙️ Docker Compose Setup

Services configured:

- frontend
- backend
- mongo

Run command:

```bash
docker-compose up -d
```

---

# ☁️ Cloud Deployment (AWS EC2 - Ubuntu)

### Steps Performed:

1. Created Ubuntu EC2 instance
2. Installed Docker
3. Installed Docker Compose
4. Pulled Docker images from Docker Hub
5. Deployed application using docker-compose
6. Configured Nginx reverse proxy on port 80

Application accessible at:

```
http://<EC2_PUBLIC_IP>
```

---

# 🔁 CI/CD Pipeline (GitHub Actions)

Workflow Location:

```
.github/workflows/mean-ci-cd.yml
```

### Pipeline Workflow:

On every push to `main` branch:

1. Checkout repository
2. Login to Docker Hub
3. Build backend Docker image
4. Build frontend Docker image
5. Push images to Docker Hub
6. SSH into EC2 server
7. Pull latest images
8. Restart containers automatically

CI/CD runs successfully on every push.

---

# 🛠️ Technologies Used

- Angular
- Node.js
- Express
- MongoDB
- Docker
- Docker Compose
- GitHub Actions
- Nginx
- AWS EC2 (Ubuntu)

---

# 🔄 CI/CD Status

✔ GitHub Actions workflow builds successfully  
✔ Docker images pushed to Docker Hub  
✔ Application auto-deploys on EC2  
✔ Reverse proxy configured on port 80  

---

# 📌 Notes

- Infrastructure is kept active for demonstration.
- Server can be restarted if required for live demonstration.
