# AWS CloudFormation – 3-Tier Web Application Infrastructure

This project defines 3-tier AWS architecture using [CloudFormation](https://aws.amazon.com/cloudformation/) It includes:

- A custom VPC with public and private subnets
- An EC2 web server with Apache installed
- An RDS MySQL database in a private subnet
- Secure networking components (IGW, security groups, route tables)

---

# AWS Services Used

- VPC, Subnets (Public + Private)
- EC2 with UserData (Apache install)
- RDS (MySQL, private subnet)
- Internet Gateway, Route Tables, and Security Groups
- CloudFormation (YAML template)

---

# How to Deploy

# Prerequisites
- AWS account with sufficient permissions
- A valid EC2 Key Pair in the deployment region
- (Optional) AWS CLI installed if deploying via terminal

---

# Deploy via AWS Console

1. Log in to the [AWS CloudFormation Console](https://console.aws.amazon.com/cloudformation/)
2. Click **Create Stack** → **With new resources (standard)**
3. Upload the `template.yaml` file from this repo
4. Click **Next**, then enter:
   - **Stack name** (e.g. `ThreeTierAppStack`)
   - **KeyName** = Your EC2 Key Pair name
5. Accept defaults → Acknowledge IAM warnings → Click **Create Stack**
6. Wait for `CREATE_COMPLETE`
7. Go to the **Outputs tab** of the stack:
   - Copy and visit the EC2 **public IP** in your browser
   - Save the **RDS endpoint** for backend use

---

