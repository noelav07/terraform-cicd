# Terraform AWS Infrastructure CI/CD Pipeline

A GitHub Actions workflow that automates Terraform planning for AWS EKS and VPC infrastructure deployment with automatic plan file commits.

##What is done here; 

- **Automated Terraform Planning**: Triggers on every push to main branch
- **AWS EKS & VPC Deployment**: Provisions complete EKS cluster with VPC infrastructure
- **Plan File Persistence**: Automatically commits plan files back to repository

##  Workflow Process

1. **Trigger**: Push to main branch
2. **Checkout**: Retrieves latest code
3. **AWS Authentication**: Configures credentials
4. **Terraform Setup**: Installs Terraform v1.6.0
5. **Infrastructure Validation**: 
   - `terraform init`
   - `terraform validate`
6. **Plan Generation**: Creates execution plan
7. **Plan Display**: Shows plan output in workflow logs
8. **Auto-Commit**: Commits `plan_output.txt` to repository
