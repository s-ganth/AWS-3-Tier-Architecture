# Production-Grade 3-Tier Architecture on AWS

## Project Overview

This project demonstrates a highly available, secure, and scalable 3-tier web application architecture built on AWS using enterprise cloud best practices.

The infrastructure separates:
- Presentation Layer (Application Load Balancer)
- Application Layer (EC2 in Private Subnets with Auto Scaling)
- Database Layer (Amazon RDS Multi-AZ)

Designed to simulate a real-world e-commerce company migrating to AWS.

## Architecture Components

### Networking
- Custom VPC (10.0.0.0/16)
- 2 Public Subnets (Multi-AZ)
- 2 Private App Subnets
- 2 Private DB Subnets
- Internet Gateway
- NAT Gateway
- Route Tables
- Security Groups

### Security
- Bastion Host for SSH
- No public access to private EC2
- RDS restricted to app tier only
- IAM roles for secure access

### Application Layer
- EC2 instances in private subnets
- Launch Template
- Auto Scaling Group (Min:2 | Max:4)
- ALB Target Groups

### Database
- Amazon RDS (Multi-AZ)
- Automated backups
- Failover enabled

### Monitoring
- CloudWatch metrics & alarms
- CPU-based scaling policy
- Health checks monitoring

## Performance Test Results

- Auto Scaling triggered at 70% CPU
- Average response time: ~120ms
- Handled simulated high traffic load
- 99.9% uptime design capability

## Estimated Cost (Monthly - Testing)

| Service | Approx Cost |

| EC2 | $18 |
| ALB | $16 |
| NAT Gateway | $32 |
| RDS Multi-AZ | $30 |
| Data Transfer | $10 |
| **Total** | ~$100–120 |

## Business Use Case

Simulated an e-commerce company experiencing traffic spikes during seasonal sales.  
This architecture ensures:

- High availability
- Fault tolerance
- Secure network isolation
- Automatic scaling
- Reduced downtime risk

## Key Learnings

- Advanced VPC Design
- Private/Public Subnet Isolation
- NAT Gateway Configuration
- Auto Scaling Policies
- Load Balancer Health Checks
- Production Monitoring
