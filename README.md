# Terraform AWS EC2 with VPC

This project provisions a complete AWS networking environment and launches an EC2 instance using Terraform. The infrastructure is created from scratch, allowing secure SSH access to the EC2 instance using an existing SSH key pair.

## Features

* Create a custom VPC
* Create a Public Subnet
* Create an Internet Gateway
* Create a Route Table
* Associate the Route Table with the Public Subnet
* Create a Security Group
* Import an existing SSH Key Pair
* Launch an Ubuntu EC2 Instance
* Output the EC2 Public IP, Public DNS, and SSH command

## Architecture

```
Internet
    |
Internet Gateway
    |
Route Table
    |
Public Subnet
    |
EC2 Instance
```

## Project Structure

```
terraform-ec2-ssh/
│── main.tf
│── .gitignore
└── README.md
```

## Prerequisites

* AWS Account
* AWS CLI configured
* Terraform installed
* Existing SSH key pair (`id_ed25519`)

## Resources Created

* VPC
* Public Subnet
* Internet Gateway
* Route Table
* Route Table Association
* Security Group
* AWS Key Pair
* Ubuntu EC2 Instance

## Security Group Rules

### Inbound

| Port | Protocol | Purpose |
| ---- | -------- | ------- |
| 22   | TCP      | SSH     |
| 80   | TCP      | HTTP    |

### Outbound

* Allow all traffic

## Commands

Initialize Terraform

```bash
terraform init
```

Validate configuration

```bash
terraform validate
```

Preview the infrastructure

```bash
terraform plan
```

Create the infrastructure

```bash
terraform apply
```

Destroy the infrastructure

```bash
terraform destroy
```

## Connect to EC2

```bash
ssh -i ~/.ssh/id_ed25519 ubuntu@<public-ip>
```

## Technologies Used

* Terraform
* AWS EC2
* AWS VPC
* AWS Internet Gateway
* AWS Route Table
* AWS Security Groups
* Linux
* SSH

## Learning Outcomes

Through this project, I learned how to:

* Provision AWS infrastructure using Terraform
* Create and configure a custom VPC
* Configure public networking for an EC2 instance
* Manage Security Groups
* Use SSH Key Pairs for secure access
* Connect to EC2 instances using SSH
* Manage Infrastructure as Code (IaC)

## Author

**Om*
