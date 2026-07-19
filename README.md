# Deploy Amazon EKS Using Jenkins and Terraform

Provisioning an Amazon EKS cluster with Terraform, automated by a Jenkins CI/CD pipeline following IaC best practices.

## Objectives
* Automate infrastructure provisioning
* Apply best practices
* Demonstrate a full DevOps workflow

## Architecture
Developer pushes to GitHub -> Jenkins triggers Terraform init, validate, plan, and apply -> AWS resources created (VPC, subnets, etc.) -> EKS cluster comes up.

## Technologies
* AWS
* EKS
* Terraform
* Jenkins
* GitHub
* Kubernetes
* AWS CLI

## Repository Structure
* Jenkinsfile
* eks-cluster.tf
* vpc.tf
* variables.tf
* outputs.tf
* providers.tf
* terraform.tfvars
* versions.tf
* .gitignore
* README.md

## Workflow
1. Push code changes to GitHub.
2. Jenkins pipeline runs Terraform init, validate, plan, and apply.
3. AWS infrastructure is provisioned and the EKS cluster is created.

## Prerequisites
* AWS account with required IAM permissions
* AWS CLI
* Terraform
* Jenkins
* kubectl

## Deployment Steps
1. Clone the repository: `git clone <repo-url>`
2. Run `terraform init`
3. Run `terraform validate`
4. Run `terraform plan`
5. Run `terraform apply`
6. Configure kubectl: `aws eks update-kubeconfig --region <region> --name <cluster-name>`
7. Verify nodes: `kubectl get nodes`
