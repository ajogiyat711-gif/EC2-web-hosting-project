# AWS EC2 Web Hosting Project

## Project Overview

This project demonstrates how to deploy and host a static website on AWS using an EC2 instance running Amazon Linux.

The objective of this project was to understand the end-to-end process of deploying infrastructure manually in AWS while following operational best practices such as secure access configuration, web server installation, service validation, logging, and backup planning.

---

## Architecture

Internet
↓
AWS Security Group (HTTP + SSH access)
↓
Amazon EC2 Instance (Amazon Linux 2023)
↓
Nginx Web Server
↓
Static Website Files (HTML)

---

## AWS Services Used

* Amazon EC2
* Security Groups
* IAM
* Amazon Machine Image (AMI)
* EBS Volume

---

## Technologies Used

* Linux (Amazon Linux 2023)
* Nginx
* SSH
* HTML

---

## Deployment Steps

### 1. Launch EC2 Instance

Created an EC2 instance using Amazon Linux 2023.

Instance configuration:

* t3.micro
* Public IP enabled
* Proper resource tagging

---

### 2. Configure Security Group

Allowed inbound traffic.

Rules configured:

* Port 22 → SSH access
* Port 80 → HTTP web traffic
* Port 443 → HTTPS web traffic


### 3. Connect to Server

Connected using SSH client.

Verified remote access and instance availability.

Example:

ssh -i key.pem ec2-user@public-ip

---

### 4. Update System

Updated packages before installing software.

sudo dnf update -y


Reason:

Applying latest security patches.


### 5. Install Web Server

Installed Nginx.

sudo dnf install nginx -y

Enabled service.

sudo systemctl enable nginx
sudo systemctl start nginx

### 6. Verify Service Status

Checked service status.

systemctl status nginx

Tested locally.

curl localhost


### 7. Validate Public Access

Accessed website using EC2 public IP address.

Confirmed successful web hosting.


### 8. Backup Strategy

Created AMI from configured instance.

Purpose:

* Disaster recovery
* Reusable server template
* Faster provisioning

---

## Key Concepts Learned

* EC2 instance deployment
* Linux server management
* Web server installation
* AWS security groups
* Service management using systemctl
* Infrastructure troubleshooting
* Server logging
* Basic backup strategy with AMI


## Future Improvements

* Automate deployment using EC2 User Data
* Deploy infrastructure using Terraform
* Configure HTTPS using SSL certificate
* Deploy behind Load Balancer
* Create CI/CD pipeline for automatic deployment


## Screenshots

* EC2 running instance
* Security Group configuration
* Remote connection
* Nginx running status
* Website accessible in browser


## Lessons Learned

This project helped me understand how cloud infrastructure is deployed manually and what operational steps are required to securely host an application in AWS.

It also reinforced Linux administration, troubleshooting, networking, and infrastructure management concepts.
