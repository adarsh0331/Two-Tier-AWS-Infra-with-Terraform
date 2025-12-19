# 🏗️ Two-Tier AWS Infrastructure with Terraform  

![Two-Tier Architecture](https://imgur.com/X4dGBg6.gif)

## 📌 Overview  

This project demonstrates a **Two-Tier architecture on AWS** using **Terraform** for Infrastructure as Code (IaC). It follows a modular and security-enhanced approach to create a **scalable, secure, and maintainable** infrastructure.  

### ✅ Key Features  

- **Modular Architecture** – Reusable Terraform modules for better management  
- **Infrastructure as Code (IaC)** – Automate AWS resource provisioning  
- **Security Best Practices** – IAM roles, policies, and WAF integration  
- **Scalability & High Availability** – Auto Scaling, Load Balancing, and Route 53  
- **Database Integration** – Managed Amazon RDS deployment  
- **SSL & CDN Optimization** – Secure connections and content acceleration  

---

## 📖 Step-by-Step Guide  

📌 **Read the full tutorial with screenshots**:  
# Deploying a Secure Two-Tier Architecture on AWS using Terraform

In the world of cloud computing, **Infrastructure as Code (IaC)** plays a pivotal role in automating the deployment and management of resources. This project provides a step-by-step guide to creating a **Two-Tier architecture** on AWS using **Terraform**. The setup ensures high availability, security, and scalability for hosting a static website.

We adopt a **modular approach** with enhanced security measures. The infrastructure is organized into dedicated modules for better scalability, maintainability, and security.

## Architecture Overview

This two-tier setup includes:
- **Web Tier**: Auto Scaling Group with EC2 instances behind an Application Load Balancer (ALB), served via CloudFront CDN.
- **Database Tier**: RDS cluster in private subnets.
- Additional components: VPC, Security Groups, WAF, ACM, Route53, IAM roles.
## Directory Structure

```
DevOps Project-11/
├── backend.tf                  # Terraform backend configuration (S3 state storage)
├── main.tf                     # Main orchestration file
├── variables.tf                # Variable definitions
├── variables.tfvars            # Variable values
└── modules/
    ├── alb-tg/                 # ALB and Target Group module
    ├── aws-autoscaling/        # Auto Scaling Group module
    ├── aws-iam/                # IAM roles and policies
    ├── aws-rds/                # RDS cluster module
    ├── aws-vpc/                # VPC and networking module
    ├── aws-waf-cdn-acm-route53/# WAF, CloudFront, ACM, Route53 module
    └── security-group/         # Security Groups module
```
This modular design promotes reusability and clarity.

## Prerequisites

- An AWS account
- Terraform installed locally
- AWS Access Key and Secret Key configured (`aws configure`)
- A registered domain name (with name servers updated at your provider)

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/adarsh0331/Two-Tier-AWS-Infra-with-Terraform
```

2. Navigate to the project:

```bash
cd Two-Tier-AWS-Infra-with-Terraform
```

## Deployment

Run these Terraform commands:

```bash
terraform init
terraform plan -var-file=variables.tfvars
terraform apply -var-file=variables.tfvars --auto-approve
```

The deployment creates resources in this order:
- VPC & Networking
- Security Groups
- EC2 Launch Template & Auto Scaling Group
- Target Group & ALB
- RDS Subnet Group & Cluster
- Route53, ACM, WAF, CloudFront
- IAM Roles & Instance Profiles
- Terraform state stored in S3 with locking

After deployment, access your domain in a browser to verify the static website is running.




## Clean Up

To avoid costs, destroy the resources:

```bash
terraform destroy -var-file=variables.tfvars --auto-approve
```

(Optional) Remove the local repository:

```bash
rm -rf DevOps-Projects
```

## Conclusion

This project demonstrates deploying a secure, scalable **Two-Tier architecture** on AWS using Terraform's modular best practices. It covers key services for high availability and security, ideal for hosting static websites or as a foundation for more complex applications.
  
---

## 🏗️ Project Architecture Highlights  

### 🔹 **Networking & Security**  

✅ **VPC & Subnets** – Securely isolated environment for your application  
✅ **IAM & Role-Based Access Control** – Fine-grained security permissions  
✅ **AWS WAF** – Protect against common web threats  

### 🔹 **Compute & Scaling**  

✅ **Auto Scaling Group** – Dynamic scaling based on demand  
✅ **Application Load Balancer (ALB)** – Efficient traffic distribution  
✅ **EC2 Instances** – Reliable computing power  

### 🔹 **Storage & Database**  

✅ **Amazon RDS** – Managed database for scalability and reliability  
✅ **S3 Buckets** – Secure storage for application assets  

### 🔹 **Networking & Optimization**  

✅ **Amazon Route 53** – Scalable domain name system (DNS)  
✅ **Amazon CloudFront (CDN)** – Faster content delivery worldwide  
✅ **SSL/TLS Encryption** – Secure communication with ACM  

---

## ⭐ Support the Project  

If you found this helpful, consider **starring** ⭐ the repository and sharing it with your network! 🚀  
