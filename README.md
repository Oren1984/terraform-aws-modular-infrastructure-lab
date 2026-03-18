# Terraform Modules Project V2

Minimal Terraform project built from reusable AWS infrastructure modules.

---

## Overview

A simple modular Terraform lab that demonstrates how to compose AWS infrastructure using small, reusable modules such as VPC, EC2, S3, RDS, ALB, and ECS. :contentReference[oaicite:0]{index=0}

---

## Tech Stack

- Terraform
- AWS
- HCL
- CloudWatch

---

## Quick Start

```bash
terraform fmt -recursive
terraform init -upgrade
terraform validate
terraform plan -out=tfplan.bin
terraform apply tfplan.bin
```

---

## Usage

This project includes modular infrastructure for:

- VPC with public subnets

- EC2 web instance

- S3 bucket

- RDS MySQL

- Application Load Balancer

- ECS Fargate service

Common outputs include VPC IDs, subnet IDs, EC2 public IP, S3 bucket name, RDS endpoint, ALB DNS name, and ECS service details.

---

## Cleanup

If needed, empty the S3 bucket first:

```bash
aws s3 rm "s3://<bucket>" --recursive || true
terraform destroy -auto-approve
```

---

## Notes

- Built for learning and modular Terraform practice

- Uses separate reusable modules under modules/

- Validation was completed locally without running a full apply to avoid AWS costs

---
