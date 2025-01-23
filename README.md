# Rent Avenue - 3-Tier Dynamic Web Application Project

A modern Car Hire platform deployed on AWS ECS using Terraform, Docker and GitHub Actions.

## Architecture Overview

### Infrastructure Tiers
- **Presentation Tier**: Frontend application in ECS
- **Application Tier**: Backend services in ECS
- **Data Tier**: RDS Database

### AWS Services Used
- ECS (Elastic Container Service)
- RDS (Relational Database Service)
- ALB (Application Load Balancer)
- VPC (Virtual Private Cloud)
- Route 53
- S3
- NAT Gateway
- Security Groups

## Repository Structure

```plaintext
.
├── .github/
│   └── workflows/
│       └── deploy_pipeline.yml
├── application-codes/
│   └── rentzone.zip
├── infra/
│   ├── acm.tf                # SSL Certificate
│   ├── alb.tf                # Load Balancer
│   ├── asg.tf                # Auto Scaling Group
│   ├── backend.tf            # Backend Configuration
│   ├── data-source.tf        # Data Sources
│   ├── ecs-role.tf          # ECS IAM Roles
│   ├── ecs.tf               # ECS Cluster/Service
│   ├── locals.tf            # Local Variables
│   ├── nat-gateway.tf       # NAT Gateway
│   ├── outputs.tf           # Output Values
│   ├── providers.tf         # AWS Provider
│   ├── rds.tf              # Database
│   ├── route-53.tf         # DNS Configuration
│   ├── s3.tf               # S3 Bucket
│   ├── security-group.tf   # Security Groups
│   ├── terraform.tfvars    # Terraform Variables
│   ├── variables.tf        # Variable Definitions
│   └── vpc.tf              # VPC Configuration
├── sql/
│   └── V1_rentavenue-db.sql # Database Migrations
├── .gitignore
├── AppServiceProvider.php
├── Dockerfile
└── README.md
```

## Prerequisites

- AWS Account
- GitHub Account
- Terraform installed
- AWS CLI configured
- Docker installed
- Git Installed

## Setup Instructions

1. **Clone Repository**
```bash
git clone https://github.com/Your-me/Rent_Avenue_GitHub_Actions_Terraform_ECS_Project.git
```

2. **Configure AWS Credentials**
- Add AWS credentials to GitHub Secrets
  - AWS_ACCESS_KEY_ID
  - AWS_SECRET_ACCESS_KEY
  - AWS_REGION

3. **Initialize Terraform**
```bash
cd infra
terraform init
```

4. **Deploy Infrastructure**
- Push to main branch to trigger GitHub Actions pipeline
- Or manually:
```bash
terraform plan
terraform apply
```

## Infrastructure Components

- **VPC**: Isolated network with public/private subnets
- **ECS**: Container orchestration for application
- **RDS**: MySQL database
- **ALB**: Load balancer for traffic distribution
- **Route 53**: DNS management
- **S3**: Static file storage
- **Security Groups**: Network access control

## CI/CD Pipeline

The GitHub Actions workflow (`deploy_pipeline.yml`) handles:
- Infrastructure deployment with Terraform
- Application building
- Container image creation and pushing to ECR
- ECS service updates

## Database Migrations

Database migrations are managed through:
- `sql/V1__rentavenue-db.sql`
- Flyway migration tool

## Security

- SSL/TLS encryption
- Private subnets for sensitive components
- Security group restrictions
- IAM roles and policies


## License

[Your chosen license]

## Contact

[akinmoladunabayomi@gmail.com]

## Acknowledgments

- AWS Documentation
- Terraform Documentation
- GitHub Actions Documentation
