
AWS EC2 Server Setup Documentation (Windows & Linux)

📌 Project Overview

This documentation explains how to launch and configure AWS EC2 instances for both Linux and Windows operating systems. It includes instance creation, security group setup, SSH/RDP connection, basic server configuration, package installation, and GitHub project structure.


---

☁️ AWS EC2 Linux Server Setup

🔹 Step 1: Login to AWS Console

1. Open AWS Management Console.


2. Search for EC2 service.


3. Click Launch Instance.




---

🔹 Step 2: Configure EC2 Instance

Instance Details

Name: Linux-Server

AMI: Ubuntu Server 22.04 LTS

Instance Type: t2.micro (Free Tier)

Key Pair: Create new key pair (.pem)



---

🔹 Step 3: Configure Security Group

Allow these inbound rules:

Type	Port	Purpose

SSH	22	Linux Remote Access
HTTP	80	Web Server
HTTPS	443	Secure Website



---

🔹 Step 4: Connect to Linux EC2

Using Terminal

chmod 400 mykey.pem
ssh -i mykey.pem ubuntu@<PUBLIC-IP>


---

🔹 Step 5: Update Linux Server

sudo apt update && sudo apt upgrade -y


---

🔹 Step 6: Install Apache Web Server

sudo apt install apache2 -y
sudo systemctl start apache2
sudo systemctl enable apache2

Verify Service

systemctl status apache2


---

🔹 Step 7: Install Git

sudo apt install git -y

Check Git Version

git --version


---

🔹 Step 8: Clone GitHub Repository

git clone https://github.com/username/project.git


---

🔹 Step 9: Firewall Configuration

sudo ufw allow 22
sudo ufw allow 80
sudo ufw allow 443
sudo ufw enable


---

🔹 Step 10: Check Public Website

Open browser:

http://<PUBLIC-IP>

Apache default page should appear.


---

🪟 AWS EC2 Windows Server Setup

🔹 Step 1: Launch Windows Instance

1. Go to EC2 Dashboard.


2. Click Launch Instance.


3. Select:

Microsoft Windows Server 2022 Base

t2.micro



4. Create/download key pair (.pem)




---

🔹 Step 2: Configure Security Group

Type	Port	Purpose

RDP	3389	Remote Desktop
HTTP	80	Web Access
HTTPS	443	Secure Access



---

🔹 Step 3: Get Administrator Password

1. Select instance.


2. Click Connect.


3. Choose RDP Client.


4. Click Get Password.


5. Upload .pem key.


6. Decrypt password.




---

🔹 Step 4: Connect Using Remote Desktop

Open Remote Desktop Connection.

Enter Public IP.

Username: Administrator

Paste decrypted password.



---

🔹 Step 5: Install IIS Web Server

Open PowerShell as Administrator:

Install-WindowsFeature -name Web-Server -IncludeManagementTools


---

🔹 Step 6: Verify IIS

Open browser:

http://localhost

IIS default page should appear.


---

🔹 Step 7: Install Git on Windows

1. Download Git from official website.


2. Install Git.


3. Open Git Bash.



Verify Installation

git --version


---

🔹 Step 8: Clone GitHub Repository

git clone https://github.com/username/project.git


---

🔐 EC2 Security Best Practices

Never share PEM key files.

Use strong passwords.

Restrict inbound traffic.

Enable automatic updates.

Use IAM roles instead of root account.

Regularly monitor logs.



---

📂 Recommended GitHub Repository Structure

EC2-Setup-Project/
│
├── Linux-Setup/
│   ├── install-apache.sh
│   ├── firewall-config.sh
│   └── README.md
│
├── Windows-Setup/
│   ├── iis-install.ps1
│   └── README.md
│
├── screenshots/
│   ├── ec2-dashboard.png
│   ├── ssh-login.png
│   └── rdp-login.png
│
└── README.md


---

📜 Sample Linux Automation Script

install-apache.sh

#!/bin/bash
sudo apt update -y
sudo apt install apache2 git -y
sudo systemctl enable apache2
sudo systemctl start apache2


---

📜 Sample Windows PowerShell Script

iis-install.ps1

Install-WindowsFeature -name Web-Server -IncludeManagementTools


---

🚀 Skills Covered

AWS EC2

Linux Administration

Windows Server Administration

SSH & RDP Access

Apache & IIS Setup

Git & GitHub

Cloud Security Basics

Firewall Configuration



---

🎯 Resume Project Description

Configured and managed AWS EC2 Linux and Windows servers. Performed remote access setup using SSH and RDP, installed Apache/IIS web servers, configured firewall rules, integrated GitHub repositories, and implemented basic cloud security practices.


---

📘 README.md File

# AWS EC2 Windows & Linux Server Setup

## 📌 Overview
This project demonstrates the setup and configuration of AWS EC2 instances for both Linux and Windows operating systems. It includes remote access configuration, web server installation, GitHub integration, firewall setup, and basic cloud security implementation.

---

# 🚀 Technologies Used
- AWS EC2
- Ubuntu Linux
- Windows Server 2022
- Apache Web Server
- IIS Web Server
- Git & GitHub
- SSH
- RDP
- PowerShell
- Bash Scripting

---

# 📂 Project Structure

```text
EC2-Setup-Project/
│
├── Linux-Setup/
│   ├── install-apache.sh
│   ├── firewall-config.sh
│   └── README.md
│
├── Windows-Setup/
│   ├── iis-install.ps1
│   └── README.md
│
├── screenshots/
│   ├── ec2-dashboard.png
│   ├── ssh-login.png
│   └── rdp-login.png
│
└── README.md


---

🐧 Linux EC2 Setup

Connect Using SSH

ssh -i mykey.pem ubuntu@<PUBLIC-IP>

Update Server

sudo apt update && sudo apt upgrade -y

Install Apache

sudo apt install apache2 -y

Install Git

sudo apt install git -y


---

🪟 Windows EC2 Setup

Connect Using RDP

Download RDP file from AWS Console

Use Administrator credentials

Login using Remote Desktop Connection


Install IIS

Install-WindowsFeature -name Web-Server -IncludeManagementTools


---

🔐 Security Configuration

Enabled SSH (22)

Enabled RDP (3389)

Enabled HTTP (80)

Enabled HTTPS (443)

Configured firewall rules

Used PEM key authentication



---

📜 Automation Scripts

Linux Script

#!/bin/bash
sudo apt update -y
sudo apt install apache2 git -y

PowerShell Script

Install-WindowsFeature -name Web-Server -IncludeManagementTools


---

🎯 Skills Demonstrated

AWS Cloud Administration

Linux Server Management

Windows Server Management

GitHub Integration

Web Server Deployment

Cloud Security Basics



---

📌 Resume Description

Configured and managed AWS EC2 Linux and Windows servers with remote access setup using SSH and RDP. Installed Apache/IIS web servers, integrated GitHub repositories, configured firewall rules, and implemented cloud security best practices.


---

⭐ Author

Shashikant Patel Cybersecurity & Cloud Security Enthusiast

---

# 📌 Conclusion
This project demonstrates practical cloud administration skills using AWS EC2 instances on both Linux and Windows environments. It provides hands-on experience with deployment, remote access, server configuration, and GitHub integration.