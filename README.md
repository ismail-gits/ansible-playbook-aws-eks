# Ansible Playbook for AWS EKS

## Overview

This repository contains Ansible playbooks and Terraform configurations for deploying and managing an AWS EKS (Elastic Kubernetes Service) cluster along with applications. The infrastructure setup includes provisioning the EKS cluster using Terraform and deploying applications to the cluster using Ansible.

## Directory Structure

### ansible-playbook-aws-eks
- **terraform-aws-eks**: Terraform configurations for provisioning the EKS cluster.
  - `eks-cluster.tf`: Defines the EKS cluster configuration including node groups, addons, and permissions.
  - `terraform.tfvars`: Variables file specifying AWS region and VPC/subnet CIDR blocks.
  - `vpc.tf`: Terraform module for creating the VPC.
- **outside terraform-aws-eks directory**:
  - `ansible-playbook.yaml`: Ansible playbook for deploying applications to the EKS cluster.
  - `ansible.cfg`: Ansible configuration file specifying settings like inventory and interpreter.
  - `nginx-kubernetes.yaml`: YAML file defining a Kubernetes Deployment and Service for Nginx.

## Usage

### Terraform Setup
1. Navigate to the `terraform-aws-eks` directory.
2. Update the `terraform.tfvars` file with your desired AWS region and subnet configurations.
3. Run `terraform init` to initialize the Terraform working directory.
4. Run `terraform apply` to apply the Terraform configuration and provision the EKS cluster.

### Ansible Playbook Execution
1. Ensure Ansible is installed on your local machine.
2. Navigate to the root directory containing `ansible-playbook.yaml`.
3. Run `ansible-playbook ansible-playbook.yaml` to deploy applications to the EKS cluster.

## Notes
- Ensure you have necessary AWS credentials configured for Terraform and Ansible.
- Customize the Kubernetes deployment (`nginx-kubernetes.yaml`) as per your application requirements.
- Modify the Ansible inventory (`ansible.cfg`) and playbook (`ansible-playbook.yaml`) if needed.