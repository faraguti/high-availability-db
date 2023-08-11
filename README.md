<p align="center">
  <img src="https://github.com/faraguti/Terraform-Website-S3/assets/5418256/6db52534-33ee-4edd-99ef-db5468e7390d" height="100%" width="100%">
</p>

# Automated 3-Tier VPC Deployment on AWS with Terraform

This project demonstrates the automated deployment of a 3-tier Virtual Private Cloud (VPC) using Terraform. The VPC consists of public and private subnets, internet gateways, NAT gateways, and route tables. The configuration files provided in this repository allow you to easily deploy the infrastructure on AWS.

## Prerequisites

Before you begin, ensure you have the following:

- AWS account and credentials configured
- Terraform installed on your local machine

## Project Structure

- `00-S3-terraform-state.tf`: Configures an S3 bucket to store Terraform state and enables versioning and encryption.
- `01-vpc.tf`: Defines the Virtual Private Cloud (VPC) with public and private subnets.
- `02-igw.tf`: Establishes Internet Connectivity (Internet Gateway) and attaches it to the VPC.
- `03-subnets.tf`: Creates public and private subnets in two availability zones.
- `04-eips.tf`: Allocates Elastic IPs for NAT Gateways.
- `05-nat-gateways.tf`: Configures NAT Gateways to provide outbound internet access for private subnets.
- `06-routing-tables.tf`: Defines route tables for public and private subnets.
- `07-route-table-association.tf`: Associates subnets with appropriate route tables.
- `backend.tf`: Configures the backend for storing Terraform state in an S3 bucket with DynamoDB locking.
- `outputs.tf`: Defines outputs for various resources.
- `provider.tf`: Configures the AWS provider and version.
- `variables.tf`: Defines variables for customization of the VPC.

## Usage

1. Clone this repository to your local machine.
2. Create a `terraform.tfvars` file and provide values for the required variables.
3. Initialize Terraform: `terraform init`
4. Plan the infrastructure deployment: `terraform plan`
5. Apply the plan to create the resources: `terraform apply`

## Important Note

Don't forget to create a `terraform.tfvars` file to provide values for variables defined in `variables.tf`. This file should contain sensitive information such as AWS access keys, so make sure to keep it secure and don't commit it to version control.

## Contributing

Contributions are welcome! Feel free to open issues or pull requests if you find any improvements or have suggestions.
