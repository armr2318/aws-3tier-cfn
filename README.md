# AWS CloudFormation 3-Tier Web Application Infrastructure

This repository contains an AWS CloudFormation template that deploys a scalable, secure 3-tier web application architecture, including:

- Custom VPC with public and private subnets  
- EC2 instance running Apache web server in the public subnet  
- RDS MySQL database instance in the private subnet  
- Necessary networking components (Internet Gateway, Route Tables, Security Groups)

---

## Architecture Overview

The deployed infrastructure includes:

- **VPC** containing two subnets:
  - **Public Subnet**:
    - EC2 instance running Apache web server
    - Security Group allowing HTTP (80) and SSH (22) access
  - **Private Subnet**:
    - RDS MySQL database instance
    - Security Group allowing MySQL (3306) access only from the EC2 security group

---

## Deployment

### Prerequisites

- AWS account with sufficient permissions  
- Existing EC2 Key Pair in your AWS region  
- AWS CLI installed and configured (optional for CLI deployment)

### Deploy via AWS Management Console

1. Navigate to [AWS CloudFormation Console](https://console.aws.amazon.com/cloudformation/).  
2. Click **Create stack** > **With new resources (standard)**.  
3. Upload `template.yaml`.  
4. Provide a stack name (e.g., `aws-3tier-webapp`).  
5. Enter your EC2 Key Pair name when prompted.  
6. Review and create the stack.  
7. Wait for the stack status to become `CREATE_COMPLETE`.  
8. In the **Outputs** tab, find the public IP of the EC2 instance and the RDS endpoint.

### Deploy via AWS CLI

1. Update `deploy.sh` with your EC2 key pair and preferred AWS region.  
2. Make the script executable:
   ```bash
   chmod +x deploy.sh
Cleanup

To delete all resources and avoid charges:

    Via Console: Delete the stack in CloudFormation.

    Via CLI:

    aws cloudformation delete-stack --stack-name aws-3tier-webapp --region your-region

Notes

    The RDS password is hardcoded for demonstration purposes; use AWS Secrets Manager or Parameter Store for production workloads.

    Verify the AMI ID in template.yaml matches your region.
