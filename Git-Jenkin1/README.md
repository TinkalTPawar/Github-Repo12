readme_content = """# Jenkins CloudFormation Deployment Pipeline

This project demonstrates how to deploy an AWS CloudFormation stack using a Jenkins pipeline. The stack is defined in the `network-ec2.yaml` template and provisions a VPC, Subnet, Internet Gateway, Route Table, Security Group, and an EC2 instance.

---

## 📁 Project Structure

- `network-ec2.yaml`: CloudFormation template defining the infrastructure.
- `Jenkinsfile`: Jenkins pipeline script to build, deploy, and test the stack.

---

## ✅ Prerequisites

- AWS account with permissions to create CloudFormation stacks and EC2 resources.
- IAM user with programmatic access (Access Key ID and Secret Access Key).
- Jenkins installed and configured.
- AWS CLI installed on Jenkins machine.
- GitHub repository containing the template and Jenkinsfile.

---

## 🔐 AWS IAM Setup

1. Go to AWS Console → IAM → Users → Add User.
2. Enable 'Programmatic Access'.
3. Attach policies:
   - `AmazonEC2FullAccess`
   - `AmazonVPCFullAccess`
   - `CloudFormationFullAccess`
4. Save the Access Key ID and Secret Access Key securely.

---

## ⚙️ Jenkins Configuration

1. Go to Jenkins → Manage Jenkins → Credentials → Global → Add Credentials.
2. Add AWS credentials:
   - Kind: Username and Password
   - ID: `aws-access-key-id` and `aws-secret-access-key`
3. Ensure Jenkins has AWS CLI installed and configured.

---

## 🚀 Pipeline Stages

### 1. Checkout
Clones the GitHub repository containing the CloudFormation template and Jenkinsfile.

### 2. Build
Validates the CloudFormation template using AWS CLI.

### 3. Deploy
Deploys the CloudFormation stack using the `network-ec2.yaml` template.

### 4. Test
Describes the EC2 instance created by the stack to verify deployment.

