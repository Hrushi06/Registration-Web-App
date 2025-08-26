# Registration Web Application – CI/CD Pipeline Project

This project demonstrates the development and deployment of a **Registration Web Application** using a fully automated **CI/CD pipeline** with **Jenkins, Maven, Tomcat, and GitHub**.  

The goal of the project is to show how modern DevOps practices can automate the build, test, and deployment process, ensuring faster and reliable delivery of web applications.

---

## 🚀 Project Overview
- Implemented an **automated CI/CD pipeline** for a Java-based Registration Web Application.  
- Configured **Jenkins** to integrate with **GitHub** for automatic build triggers whenever code is pushed.  
- Used **Maven** as the build tool to package the application into a `.war` file.  
- Automated deployment of the application onto an **Apache Tomcat Server**.  
- Ensured end-to-end automation from **code commit → build → deployment**.  

---

## 🛠️ Technologies Used
- **Jenkins** – Continuous Integration & Continuous Deployment (CI/CD)
- **Maven** – Build Automation Tool
- **Apache Tomcat** – Application Deployment Server
- **Git & GitHub** – Version Control & Source Code Repository
- **Java** – Programming Language
- **AWS EC2 (Linux)** – Deployment Environment

---

## ⚙️ Setup & Installation

### 1. Install Jenkins
```bash
sudo yum update -y
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum install java-11-amazon-corretto -y
sudo yum install jenkins -y
sudo systemctl enable jenkins
sudo systemctl start jenkins

Access Jenkins at:

http://<EC2-Public-IP>:8080
