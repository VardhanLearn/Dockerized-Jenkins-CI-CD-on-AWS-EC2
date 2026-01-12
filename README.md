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

