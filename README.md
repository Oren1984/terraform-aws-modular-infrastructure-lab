# Terraform AWS Modular Infrastructure Lab

A modular Terraform infrastructure lab demonstrating how multiple reusable AWS modules can be composed into a complete environment.

---

## Overview

This project demonstrates the implementation of a broad AWS infrastructure stack using independent and reusable Terraform modules.

The repository was created as a hands-on infrastructure engineering lab. Its purpose is to demonstrate modular design, dependency management, Terraform outputs, provider configuration, and the integration of several AWS services within a single project.

This is not intended to represent a minimal production architecture. Individual modules can be selected and adapted according to the requirements of a real environment.

---

## Architecture Components

The project includes reusable Terraform modules for:

- VPC and public networking
- EC2 web instance
- S3 storage
- RDS MySQL database
- Application Load Balancer
- ECS Fargate service
- CloudWatch integration

Modules are stored under the `modules/` directory and are composed through the root Terraform configuration.

---

## Tech Stack

- Terraform
- AWS
- HCL
- Amazon VPC
- Amazon EC2
- Amazon S3
- Amazon RDS
- Application Load Balancer
- Amazon ECS Fargate
- Amazon CloudWatch

---

## Project Structure

```text
.
├── modules/
├── main.tf
├── variables.tf
├── outputs.tf
├── providers.tf
├── versions.tf
├── .terraform.lock.hcl
└── README.md
```

---

## Validation

The Terraform configuration can be formatted and validated locally:

```bash
terraform fmt -recursive
terraform init
terraform validate
```

To review the proposed infrastructure changes:

```bash
terraform plan -out=tfplan.bin
```

A full AWS deployment was intentionally not executed in order to avoid unnecessary cloud costs.

---

## Deployment

To deploy the infrastructure after reviewing the execution plan:

```bash
terraform apply tfplan.bin
```

AWS credentials and the required input variables must be configured before deployment.

---

## Cleanup

Before destroying the environment, ensure that any created S3 bucket is empty:

```bash
aws s3 rm "s3://<bucket-name>" --recursive
terraform destroy
```

---

## Security Notes

Terraform state files, local variable files, generated plans, and local Terraform directories are excluded from version control.

Do not commit:

- AWS credentials
- Terraform state files
- Secret variable files
- Generated plan files
- Sensitive infrastructure outputs

---

## Project Scope

This repository is a portfolio and learning project focused on:

- Terraform module composition
- Infrastructure dependency management
- AWS infrastructure fundamentals
- Reusable Infrastructure as Code design
- Local validation and planning workflows

The project intentionally demonstrates multiple AWS components in one environment. In a production implementation, only the modules required by the approved architecture and business requirements should be deployed.

---

