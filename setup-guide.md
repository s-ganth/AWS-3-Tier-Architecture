# Step-by-Step Setup Guide

## Step 1: Create VPC
- CIDR: 10.0.0.0/16
- Enable DNS Hostnames

## Step 2: Create Subnets
- 2 Public Subnets (Different AZs)
- 2 Private App Subnets
- 2 Private DB Subnets

## Step 3: Internet Gateway
- Attach to VPC
- Update Public Route Table

## Step 4: NAT Gateway
- Create in Public Subnet
- Attach Elastic IP
- Update Private Route Table

## Step 5: Bastion Host
- Launch EC2 in Public Subnet
- Allow SSH from your IP only

## Step 6: Application EC2
- Launch in Private Subnet
- Attach IAM Role
- Install web server

## Step 7: Create Launch Template
- AMI
- Instance Type
- Security Group
- Key Pair

## Step 8: Create Auto Scaling Group
- Min: 2
- Max: 4
- Attach to ALB

## Step 9: Create Application Load Balancer
- Public facing
- Target Group configured

## Step 10: Create RDS (Multi-AZ)
- Private DB Subnets
- No public access
- Allow inbound from App SG only

## Step 11: Configure CloudWatch
- CPU Alarm at 70%
- Scaling policy attached

## Final Validation

- Access website via ALB DNS
- Test scaling by increasing load
- Verify RDS connectivity
- Monitor CloudWatch metrics
