# Deploy Amazon EKS Using Jenkins and Terraform
Provision an Amazon Elastic Kubernetes Service (EKS) cluster using Terraform and automate the deployment through a Jenkins CI/CD pipeline while following Infrastructure as Code (IaC) best practices.

## Project Overview

This project demonstrates how to provision a highly available Amazon Elastic Kubernetes Service (EKS) cluster using Terraform while automating the entire Infrastructure as Code (IaC) deployment process through a Jenkins CI/CD pipeline.

The infrastructure is created entirely from code, including the Virtual Private Cloud (VPC), networking components, security groups, and the EKS cluster. Jenkins automates the Terraform workflow, ensuring every deployment follows a consistent, repeatable, and version-controlled process.

This project showcases real-world DevOps practices such as Infrastructure as Code, Continuous Integration, automation, cloud provisioning, and Kubernetes orchestration on AWS. 

## Architecture Diagram

```text
+----------------------+
|      Developer       |
+----------+-----------+
          |
          | Git Push
          v
+----------------------+
|       GitHub         |
+----------+-----------+
          |
          | Webhook
          v
+----------------------+
|      Jenkins CI      |
+----------+-----------+
          |
   +------+------+
   |             |
   v             v
terraform init   terraform validate
        \         /
         \       /
          v     v
     terraform plan
           |
           v
     terraform apply
           |
           v
+-------------------------------+
|             AWS               |
|-------------------------------|
| VPC                           |
| Public & Private Subnets      |
| Internet Gateway              |
| Route Tables                  |
| Security Groups               |
| Amazon EKS Cluster            |
+-------------------------------+
           |
           v
aws eks update-kubeconfig
           |
           v
kubectl get nodes
           |
           v
Kubernetes Cluster Ready
```

## Objectives
* Automate infrastructure provisioning
* Apply best practices
* Demonstrate a full DevOps workflow

## Technologies Used
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

## Skills Demonstrated

- Infrastructure as Code (Terraform)
- Amazon EKS
- Jenkins CI/CD
- Kubernetes
- AWS Networking
- Git & GitHub
- AWS CLI
- Linux Administration

## Project Outcome

Successfully automated the provisioning of an Amazon EKS cluster using Terraform through a Jenkins CI/CD pipeline. The solution provisions AWS networking resources, deploys a production-ready Kubernetes control plane, and provides a repeatable, version-controlled infrastructure deployment using Infrastructure as Code (IaC) principles.
