# terraform
#AWS VPC Creation with Terraform

This project will create a VCP with Internet Gateway, subnets accross 2 AZs: one public and one one private.

From there terraform will deploy a bastion host in the public subnet in AZ1 and a second host in the private subnet in AZ2, which can connect to the internet via a NAT gateway created as part of the VPC.

An SSH key pair is dynamically generated as well, and the private key is copied over to the bastion host.

The ec2 instance in the public subnet is assigned a security group with access from the the intenret via port 22 (for ssh).

The ec2 instance in the private subnet is assigned to a security group that only allows ssh access only from connections in the public subnet.

Both security groups are dynamically created in the network module.


