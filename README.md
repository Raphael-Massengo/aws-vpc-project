# AWS VPC infrastructure project with public/private subnets, EC2, NAT Gateway, and Application Load Balancer

## 🚀 Overview
This project demonstrates the design and deployment of a secure and scalable AWS cloud infrastructure using a multi-tier VPC architecture.

The environment was built to simulate a real-world production setup with secure networking practices, private infrastructure, controlled administrative access, and high availability.

The project combines AWS cloud engineering concepts with networking principles from CCNA, including routing, subnetting, traffic control, and secure access management.

## 🧱 Architecture
- The infrastructure includes:
- Custom AWS VPC (`10.0.0.0/16`)
- Public and Private Subnets across multiple Availability Zones
- Internet Gateway (IGW)
- NAT Gateway
- Bastion Host
- EC2 Instances in private subnets
- Application Load Balancer (ALB)
- Route Tables and Security Groups

## 📊 Architecture Diagram

<img width="848" height="342" alt="architecture drawio" src="https://github.com/user-attachments/assets/80a602c5-bb66-42dd-9efc-d4ab386ca289" />

# ⚙️ AWS Services Used

| Service | Purpose |
|---|---|
| VPC | Isolated cloud network |
| EC2 | Virtual servers |
| Internet Gateway | Public internet access |
| NAT Gateway | Outbound internet for private instances |
| Application Load Balancer | Traffic distribution |
| IAM | Secure access management |
| Security Groups | Firewall and traffic filtering |

# 🔐 Security Design

Several security best practices were implemented:

- EC2 application servers were deployed inside private subnets
- Private instances do not have public IP addresses
- SSH access is restricted through a Bastion Host
- Security Groups were configured using least privilege principles
- Public traffic is routed only through the Load Balancer

# 🌐 Network Design

## Public Subnets
Used for:
- Bastion Host
- Load Balancer
- NAT Gateway

## Private Subnets
Used for:
- Internal EC2 application servers
  
This design improves security by isolating backend infrastructure from direct internet exposure.

# ⚡ High Availability
To improve availability and fault tolerance:
- Multiple Availability Zones were used
- Public and private subnets were distributed across AZs
- Application Load Balancer distributes traffic between EC2 instances
  
# 🛠️ Deployment Steps
## 1. Created Custom VPC
- CIDR block: `10.0.0.0/16`
## 2. Configured Subnets
- Public Subnet 1 → `10.0.1.0/24`
- Public Subnet 2 → `10.0.2.0/24`
- Private Subnet 1 → `10.0.3.0/24`
- Private Subnet 2 → `10.0.4.0/24`

## 3. Configured Internet Gateway
Attached IGW to enable public internet access.

## 4. Created NAT Gateway
Allowed private instances outbound internet access without exposing them publicly.

## 5. Launched EC2 Instances
- Bastion Host in public subnet
- Application EC2 instances in private subnets
  
## 6. Configured Application Load Balancer
Distributed incoming traffic across EC2 targets.

## 📸 Screenshots
<img width="1920" height="1080" alt="Screenshot 2026-05-03 222516" src="https://github.com/user-attachments/assets/f0a1da47-0aaa-4c72-9280-ba34b723914e" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 222532" src="https://github.com/user-attachments/assets/a5b2fcfb-2583-410d-aa9e-5aeb8dc3cd36" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 222815" src="https://github.com/user-attachments/assets/8c6d987d-e8a0-496d-a548-0fdea3395cff" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 222921" src="https://github.com/user-attachments/assets/7d21b6c8-3bb4-4e8f-b521-6970692f0eec" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223014" src="https://github.com/user-attachments/assets/db00d61c-d9e7-4851-8c52-14616908d282" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223111" src="https://github.com/user-attachments/assets/9cd01f2f-3b5d-4b45-8159-83668b5b6c1b" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223128" src="https://github.com/user-attachments/assets/c8c29118-c1f2-42b2-b3a5-9fcccd645475" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223353" src="https://github.com/user-attachments/assets/f1469348-e29a-4f33-aff7-4e45f87bbdd6" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223441" src="https://github.com/user-attachments/assets/08f90478-c7fd-4014-a71f-603f2e765253" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223521" src="https://github.com/user-attachments/assets/96139ca3-7aa5-4ecb-bb9f-ccd8ed4269e0" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223558" src="https://github.com/user-attachments/assets/a6a0541f-6919-4fd7-97fc-ba3d359cdd8c" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223622" src="https://github.com/user-attachments/assets/08891369-e18b-48a0-9e24-7491e3861ee6" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223636" src="https://github.com/user-attachments/assets/17b715fc-3dd0-4da3-a412-12c013af9ceb" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223739" src="https://github.com/user-attachments/assets/0c9256d8-3cad-4123-acd1-38628d06f644" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223755" src="https://github.com/user-attachments/assets/f939f5a1-40ac-42f2-97dd-6d4b2ef46f7e" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223809" src="https://github.com/user-attachments/assets/5f318fb0-6c70-4ec1-866b-9a04f69f4270" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223849" src="https://github.com/user-attachments/assets/55ea1520-e732-44e6-8771-d3ca1a0cfc94" />
<img width="1920" height="1080" alt="Screenshot 2026-05-03 223931" src="https://github.com/user-attachments/assets/ce612777-022b-4bd2-8089-d08a099ad2fd" />

# 🧠 Key Learning Outcomes
Through this project, I gained practical experience with:
- AWS VPC architecture design
- Public vs Private subnet implementation
- Route table configuration
- NAT Gateway functionality
- Load balancing concepts
- Secure cloud networking
- Infrastructure troubleshooting
  
# 🚧 Future Improvements
Planned enhancements:
- Infrastructure as Code using Terraform
- Monitoring with CloudWatch
- Auto Scaling Group integration
- CI/CD deployment pipeline
- HTTPS configuration using ACM

# 👨‍💻 Author
Raphael Massengo
- CCNA Certified
- AWS Cloud Engineering Enthusiast
- Master’s Student in Data Analytics

