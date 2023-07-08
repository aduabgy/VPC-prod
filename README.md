# VPC-prod
AWS VPC Infrastructure Configuration
This repository contains the Terraform configuration files to provision an AWS VPC (Virtual Private Cloud) infrastructure. The infrastructure includes the setup of subnets, route tables, NAT gateway, and internet gateway. This configuration is designed to be used with Terraform.

Prerequisites
To use this Terraform configuration, you need to have the following:

Terraform installed on your local machine.
An AWS account with appropriate access and credentials.
Usage
Clone this repository to your local machine:

bash
Copy code
git clone <repository-url>
Change into the cloned directory:

bash
Copy code
cd <cloned-directory>
Open the variables.tf file and modify the variable values according to your requirements. This file contains configurable variables such as VPC CIDR block, subnet CIDR blocks, and availability zones.

Initialize the Terraform working directory:

bash
Copy code
terraform init
Review the execution plan to ensure that the changes align with your expectations:

bash
Copy code
terraform plan
If the plan looks correct, apply the changes to create the infrastructure:

bash
Copy code
terraform apply
Terraform will prompt for confirmation before applying the changes. Type yes and press Enter to proceed.

The infrastructure provisioning process will start, and Terraform will display the progress and final outputs once completed.
Resources Created
The Terraform configuration in this repository will provision the following resources in your AWS account:

1 VPC (aws_vpc.production_vpc)
3 public subnets (aws_subnet.public-subnet-1, aws_subnet.public-subnet-2, aws_subnet.public-subnet-3)
3 private subnets (aws_subnet.private-subnet-1, aws_subnet.private-subnet-2, aws_subnet.private-subnet-3)
2 route tables (aws_route_table.public_route_table, aws_route_table.private_route_table)
6 subnet associations with route tables (aws_route_table_association.public-subnet-X-association, aws_route_table_association.private-subnet-X-association)
1 Elastic IP for NAT Gateway (aws_eip.elastic-ip-for-nat-gw)
1 NAT Gateway (aws_nat_gateway.nat-gw)
1 route for NAT Gateway (aws_route.nat-gw-route)
1 internet gateway (aws_internet_gateway.production-IGW)
1 route for public internet gateway (aws_route.public-internet-gw-route)
Customization
You can customize the infrastructure configuration by modifying the values in the variables.tf file. Update the variable values to match your desired configuration.

Clean Up
To destroy the infrastructure created by this Terraform configuration and remove all associated resources, run the following command:

bash
Copy code
terraform destroy
Terraform will prompt for confirmation before destroying the resources. Type yes and press Enter to proceed.
