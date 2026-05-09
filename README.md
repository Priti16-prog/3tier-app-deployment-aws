# 3-Tier Architecture Application Deployment on AWS

## Project Overview

Designed and deployed a highly available and secure 3-tier web application architecture on AWS using VPC, EC2, RDS MySQL, Internal & External Application Load Balancers, Auto Scaling Groups, Route53, ACM, Nginx, and Node.js.

The entire infrastructure was deployed using the AWS Management Console without Terraform or CloudFormation.

---

# Architecture

```text
Users
   ↓
Route53
   ↓
External ALB (HTTPS)
   ↓
Web Tier (Nginx)
   ↓
Internal ALB
   ↓
Application Tier (Node.js)
   ↓
RDS MySQL
```

---

# AWS Services Used

- VPC
- EC2
- RDS MySQL
- Application Load Balancer (ALB)
- Auto Scaling Group (ASG)
- Route53
- ACM
- IAM Role
- AWS Systems Manager (SSM)
- S3
- Nginx
- Node.js

---

# Infrastructure Configuration

## Networking
- Custom VPC: `192.168.0.0/16`
- 2 Public Subnets
- 4 Private Subnets
- NAT Gateway
- Internal & External Load Balancers

## Security Groups
- Web ALB Security Group
- Web Server Security Group
- App Internal ALB Security Group
- App Server Security Group
- Database Security Group

## Database
- Amazon RDS MySQL
- Private DB Subnet Group
- Encrypted Storage
- No Public Access

---

# Deployment Workflow

## Application Tier
- Deployed Node.js backend application
- Configured PM2 process manager
- Connected application to RDS MySQL
- Configured Internal ALB with health checks

## Web Tier
- Configured Nginx reverse proxy
- Integrated frontend with internal application load balancer
- Configured External ALB for internet traffic

## Security & Access
- HTTPS enabled using ACM
- Domain configured using Route53
- Private EC2 access using AWS Systems Manager Session Manager
- Application code stored in private S3 bucket

## Auto Scaling
- Created Launch Templates for Web and App tiers
- Configured Auto Scaling Groups across multiple Availability Zones

---

# Key Features

- Highly Available Architecture
- Scalable Infrastructure
- Secure Private Networking
- HTTPS Enabled
- Internal & External Load Balancing
- Auto Scaling Support
- Session Manager Access without Bastion Host

---

# Project Outcome

Successfully designed and deployed a production-style 3-tier architecture on AWS with secure networking, load balancing, auto scaling, HTTPS integration, and private database connectivity using only AWS Console services.
