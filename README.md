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
```
### 2. Install Maven
```bash

cd /opt
wget https://dlcdn.apache.org/maven/maven-3/3.9.3/binaries/apache-maven-3.9.3-bin.tar.gz
tar -xzvf apache-maven-3.9.3-bin.tar.gz
mv apache-maven-3.9.3 maven

Update ~/.bash_profile:

export M2_HOME=/opt/maven
export M2=$M2_HOME/bin
export JAVA_HOME=/usr/lib/jvm/java-11-amazon-corretto.x86_64
export PATH=$PATH:$HOME/bin:$JAVA_HOME/bin:$M2

Apply changes:
source ~/.bash_profile
mvn -v
```
### 3. Install Apache Tomcat
```bash
cd /opt
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.76/bin/apache-tomcat-9.0.76.tar.gz
tar -xvzf apache-tomcat-9.0.76.tar.gz
mv apache-tomcat-9.0.76 tomcat

Start Tomcat:

/opt/tomcat/bin/startup.sh

Configure users in tomcat-users.xml:

<role rolename="manager-gui"/>
<role rolename="manager-script"/>
<user username="admin" password="admin" roles="manager-gui,manager-script"/>
```
### 4. Configure Jenkins Pipeline

1. Add your GitHub repository URL in the Jenkins job.

2. Configure Poll SCM with:
```bash
* * * * *
```

(checks GitHub every minute for changes)

3. Build Steps:

Clean & Package using Maven

Deploy the .war file to Tomcat automatically
