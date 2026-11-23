# Automated AWS VPC & EC2 Web Server (CloudFormation)

This project demonstrates **Infrastructure as Code (IaC)** using **AWS CloudFormation** to automatically provision a secure, custom network and web server on AWS.

## Architecture & Resources Created
* **Custom VPC** (`10.0.0.0/16`)
* **Public Subnet** (`10.0.1.0/24`) with auto-assign public IP enabled
* **Internet Gateway (IGW)** & Custom Route Table (`0.0.0.0/0 -> IGW`)
* **Security Group** allowing inbound HTTP (Port 80) traffic
* **EC2 Instance (`t3.micro`)** running Amazon Linux 2023 (dynamically fetched via SSM Parameter Store) with an automated Apache web server setup via `UserData`

## How to Deploy
1. Open the **AWS CloudFormation** console.
2. Click **Create stack -> With new resources (standard)**.
3. Upload `vpc-ec2-stack.yaml` and follow the prompts to launch.
4. Access the deployed web page using the `WebsiteURL` link in the **Outputs** tab.
