# 🚀 Dockerized Jenkins CI/CD on AWS EC2

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

