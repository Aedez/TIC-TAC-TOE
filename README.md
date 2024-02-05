<h1 align="center">TIC-TAC-TOE-GAME</h1>

# Project Name: CI/CD Pipeline for EKS Deployment

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## Summary

This project sets up a Continuous Integration/Continuous Deployment (CI/CD) pipeline for deploying applications to Amazon Elastic Kubernetes Service (EKS). The pipeline includes the following steps:

### Step 1A: Launch an EC2 Instance

1. Sign in to AWS account.
2. Access EC2 dashboard.
3. Launch an instance with Ubuntu 22.04 AMI and t2.medium type.
4. Configure instance details, storage, tags, and security group settings.
5. Review settings, create/select key pair, and launch the instance.
6. Connect to the instance via SSH using the key pair.

### Create an IAM ROLE

1. Navigate to AWS Console.
2. Search for "IAM" and click "Roles."
3. Create a role for EC2 service.
4. Add necessary permissions policies.
5. Provide a role name (e.g., Jenkins-cicd).
6. Add the role to the EC2 instance.

### Step 1B: Add a Self-hosted Runner to EC2

1. Go to GitHub Settings > Actions > Runners.
2. Click "New self-hosted runner."
3. Select Linux and Architecture X64.
4. Connect to EC2 instance.
5. Run commands to add a self-hosted runner.

### Step 2A: Install Docker and Run Sonarqube Container

1. Connect to EC2 instance.
2. Install Docker on the instance.
3. Pull the SonarQube Docker image and run it.

### Step 2B: Integrating SonarQube with GitHub Actions

1. Manually set up SonarQube project on the dashboard.
2. Generate an overview of the project and provide instructions.
3. Add SonarQube secrets to GitHub.

### Step 2C: Installation of Other Tools

1. Run the provided script to install Java 17, Trivy, Terraform, kubectl, AWS CLI, Node.js 16, and npm.

### EKS Provision

1. Clone the repository onto the EC2 instance.
2. Change directory to EKS terraform files.
3. Update S3 bucket in the backend file.
4. Initialize, validate, plan, and apply Terraform for EKS cluster creation.

### Deploy to EKS

1. Install npm dependencies.
2. Add remaining steps.
3. Build, analyze, scan, and deploy to EKS using GitHub Actions.

### SLACK Integration

1. Create a Slack channel for notifications.
2. Set up Slack app, generate webhook URL.
3. Add Slack webhook URL as a GitHub secret.
4. Add Slack notification step to the workflow.

### Complete Workflow

1. Run the complete workflow on GitHub Actions.

### Destruction Workflow

1. Run the destruction workflow to stop and remove resources.

### Cleanup

1. Stop the self-hosted runner.
2. Delete the EKS cluster.
3. Delete DockerHub token.
4. Terminate the EC2 instance.
5. Delete IAM role.
6. Delete secrets from GitHub.

Make sure to adapt and customize the checklist based on your specific requirements and configurations.

## License

This project is licensed under the [MIT License](LICENSE).

