# Secure-VPC-Multi-Tier-Architecture-on-AWS
Designed and implemented a secure multi-tier AWS VPC architecture with public and private subnets, NAT Gateway, Internet Gateway, and EC2 instances using best practices for cloud networking and security.

##  Overview
This project demonstrates the design and implementation of a secure and scalable AWS network architecture using Amazon VPC.

The architecture follows a multi-tier approach by separating public-facing resources from private backend resources to enhance security and control traffic flow.

---

##  Architecture

The infrastructure includes:

- Amazon VPC with custom CIDR block
- Public and Private Subnets
- Internet Gateway (IGW)
- NAT Gateway for secure outbound internet access
- Route Tables for traffic control
- EC2 instances (Public & Private)
- Security Groups for controlled access
- AWS Systems Manager Session Manager for secure connectivity

---

##  Key Features

- Public subnet allows controlled internet access
- Private subnet is fully isolated from direct internet exposure
- NAT Gateway enables outbound traffic for private instances
- Security Groups enforce least privilege access
- No SSH exposure (used Session Manager instead)

---

##  Architecture Diagram

<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/6b3f5368-7c06-4a84-bd61-695042f20fe2" />

---

##  Implementation Steps

### 1. VPC Creation
- Created VPC with CIDR block 10.0.0.0/16
- Enabled DNS hostnames

### 2. Subnet Configuration
- Public Subnet: 10.0.0.0/24
- Private Subnet: 10.0.2.0/23

### 3. Internet Connectivity
- Attached Internet Gateway to VPC
- Configured public route table → IGW

### 4. NAT Gateway Setup
- Deployed NAT Gateway in public subnet
- Allocated Elastic IP
- Routed private subnet traffic → NAT

### 5. Security Configuration
- Public SG 
- Private SG

### 6. EC2 Deployment
- Public EC2 (Web Server)
- Private EC2 (Isolated backend)
- Used user data for Apache setup

### 7. Secure Access
- Connected using AWS Session Manager
- No SSH keys or open ports used

---

##  Validation

- Accessed public web server 
- Verified outbound internet access -private instance by curl
- Tested internal communication 

---

##  Screenshots

| Description | Image |
|------------|------|
|01-vpc-overview.png | 
|02-public-subnet-setup.png |
|03-private-subnet-setup.png |
|04-internet-gateway.png |
|05-route-table-public.png |
|06-route-table-private.png |
|07-nat-gateway.png |
|08-public-ec2-running.png |
|09-web-server-output.png |
|10-private-instance-curl-test.png |



