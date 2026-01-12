# 🚀 Dockerized Jenkins CI/CD on AWS EC2

<img width="1536" height="1024" alt="ChatGPT Image Jan 12, 2026, 08_31_18 PM" src="https://github.com/user-attachments/assets/31d03708-1b02-45ff-8f8d-594e452366f9" />


This project demonstrates a complete **CI/CD Pipeline** using:

✅ AWS EC2 (Ubuntu 22.04)  
✅ Docker  
✅ Docker Compose  
✅ Jenkins (running inside Docker)  
✅ Node.js sample application  
✅ Jenkins Pipeline as Code (Jenkinsfile)  

---

## 📌 Project Goal

Deploy a Node.js app automatically on AWS EC2 using Jenkins CI/CD pipeline.

Whenever Jenkins pipeline runs:
1. Pulls code from GitHub
2. Builds Docker Image
3. Stops old container
4. Runs updated container

---

## 📂 Project Structure

Dockerized-Jenkins-CICD-on-AWS-EC2/
│
├── app/
│ ├── Dockerfile
│ ├── package.json
│ └── index.js
│
├── Jenkinsfile
├── docker-compose.yml
├── .gitignore
└── README.md


---

## 🧰 Requirements

### AWS
- EC2 Instance: `t2.medium` (recommended)
- OS: Ubuntu 22.04
- Storage: 15GB+
- Security Group Rules:
  - SSH: `22`
  - Jenkins: `8080`
  - App Port: `3000`

---

## ⚙️ Setup Instructions (EC2)

### 1️⃣ Install Docker

```bash
sudo apt update -y
sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker ubuntu
newgrp docker
----------------------------------------------------------------------------------------------------
2️⃣ Install Docker Compose

sudo apt install docker-compose -y
----------------------------------------------------------------------------------------------------

🧩 Run Jenkins in Docker
Start Jenkins

docker-compose up -d
---------------------------------------------------------------------------------------------------
Get Jenkins Initial Password
docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
===================================================================================================
Open Jenkins UI
http://<EC2_PUBLIC_IP>:8080
---------------------------------------------------------------------------------------------------

🔧 Jenkins Setup
Install Suggested Plugins

During first-time setup choose:
✅ "Install Suggested Plugins"

🏗️ Configure Pipeline Job

Open Jenkins Dashboard

New Item

Select Pipeline

**Pipeline Definition:**

✅ Pipeline script from SCM

SCM: Git

Repo URL: Your GitHub repo

Branch: main

Script Path: Jenkinsfile

Save & Build.

✅ **Verify App Deployment**

After successful pipeline build:

App runs on:
http://<EC2_PUBLIC_IP>:3000

=====================================================================================================
Example output:
{
  "message": "✅ CI/CD Deployment Successful using Jenkins + Docker on AWS EC2",
  "endpoint": "/",
  "timestamp": "2026-01-12T..."
}

=====================================================================================================

👤 Author

Vardhan Kandregula DevOps Engineer | AWS | Docker | Kubernetes | CI/CD

📌 This project is part of my DevOps learning and portfolio.

⭐ If you like this project

Give it a ⭐ on GitHub and feel free to fork or contribute!


