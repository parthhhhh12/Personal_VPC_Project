# 🚀 Building a Secure and Scalable AWS VPC Infrastructure

![AWS Banner](https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg)

## 🌐 Project Overview

This project focuses on designing and deploying a **secure, scalable, and high-availability AWS Virtual Private Cloud (VPC)** environment.  
The goal was to build a production-ready cloud infrastructure that ensures **network isolation, redundancy, secure access, and load balancing** across multiple subnets and availability zones.

---

## 🧩 Key Features

| Feature | Description |
|----------|-------------|
| **VPC Creation** | Custom VPC with 2 public and 2 private subnets spread across different availability zones |
| **Internet & NAT Gateway** | Public subnets connect through an Internet Gateway, and private subnets access the internet securely through a NAT Gateway |
| **EC2 Instances** | Deployed EC2 instances in both public and private subnets for application and bastion host configurations |
| **Bastion Host** | Configured in the public subnet to securely access private instances via SSH tunneling |
| **NGINX Server** | Installed and configured NGINX on private EC2 instances to serve web content and manage traffic efficiently |
| **Application Load Balancer (ALB)** | Distributes incoming requests evenly across multiple EC2 instances in different subnets |
| **Auto Scaling Group (ASG)** | Automatically scales compute resources based on load metrics for cost and performance optimization |
| **Security Groups & NACLs** | Implemented for controlled inbound and outbound traffic at instance and subnet levels |

---

## ⚙️ Implementation Steps

1. **VPC Setup**
   - Created a custom VPC (`10.0.0.0/16`)
   - Added 2 public and 2 private subnets across two availability zones for redundancy

2. **Internet & NAT Gateways**
   - Attached an Internet Gateway to the VPC for public access
   - Configured a NAT Gateway in one of the public subnets for private subnet outbound traffic

3. **EC2 Instance Deployment**
   - Deployed EC2 instances in both public and private subnets
   - Enabled SSH access only via Bastion Host

4. **Bastion Host Configuration**
   - Created a Bastion Host in the public subnet to securely access private EC2 instances using key-based authentication

5. **NGINX Server Setup**
   - Installed and configured NGINX on private EC2 instances to handle web traffic
   - Verified functionality using internal and external endpoints

6. **Application Load Balancer (ALB)**
   - Deployed an ALB in the public subnet to route traffic to EC2 targets across multiple subnets
   - Configured health checks to maintain uptime and traffic distribution

7. **Auto Scaling Group (ASG)**
   - Implemented ASG with a launch template
   - Configured scaling policies based on CPU utilization to handle dynamic workloads

8. **Security & Access Control**
   - Designed Security Groups for granular traffic control
   - Configured NACLs for subnet-level protection
   - Ensured least-privilege principles and disabled direct internet SSH access to private instances

---

VPC (10.0.0.0/16)
├── Public Subnet (AZ1)
│ ├── Bastion Host (EC2)
│ ├── ALB
│ └── NAT Gateway
├── Public Subnet (AZ2)
│ ├── ALB Target
├── Private Subnet (AZ1)
│ ├── App Server 1 (NGINX)
├── Private Subnet (AZ2)
│ ├── App Server 2 (NGINX)
└── Route Tables, Security Groups, and NACLs

---

## 🔒 Security Highlights

- **Private subnets** are isolated from direct internet access  
- **SSH access** limited to Bastion Host via specific IP ranges  
- **HTTPS traffic** only through ALB  
- **IAM roles** follow least-privilege access  
- **Network segmentation** for enhanced control and visibility  

---

## 🧠 Tech Stack

- **Cloud Platform:** Amazon Web Services (AWS)  
- **Services Used:**  
  VPC, EC2, ALB, ASG, Internet Gateway, NAT Gateway, IAM, CloudWatch  
- **Web Server:** NGINX  
- **Operating System:** Amazon Linux 2 / Ubuntu  
- **Access Method:** SSH via Bastion Host  

---

## 📈 Key Learnings

- Designed a **multi-tier AWS architecture** from scratch  
- Gained hands-on experience with **VPC networking, routing, and NAT configurations**  
- Learned to implement **load balancing and auto scaling** for dynamic workloads  
- Enhanced understanding of **security best practices** in AWS cloud environments  

---

## 🚀 Future Improvements

- Automate the setup using **Terraform** or **AWS CloudFormation**  
- Add **CloudWatch metrics and alerts** for proactive monitoring  
- Implement **AWS WAF (Web Application Firewall)** for application-level protection  
- Integrate **Route 53** for DNS-based load balancing  

---

⭐ *If you found this project helpful, please star the repository and connect with me on LinkedIn!* ⭐

