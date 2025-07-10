# AWS CloudFormation – 3-Tier Web App (EC2 + VPC)

This project deploys a basic 3-tier web application using AWS CloudFormation. It includes:

- A custom VPC
- A public subnet
- An EC2 instance with Apache web server
- An internet gateway and security group for public access

##  Services Used

- EC2
- VPC
- Subnet
- Internet Gateway
- Security Groups
- Route Table
- CloudFormation

##  How to Deploy

### Requirements

- AWS account
- Existing EC2 Key Pair (for SSH access)

### Deployment Steps

1. Clone this repo:
   ```bash
   git clone https://github.com/yourusername/aws-3tier-cfn.git
   cd aws-3tier-cfn
