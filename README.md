# Secure-AWS-VPC-Infrastructure-with-Bastion-Host

# Project Overview
This project demonstrates the design and deployment of a secure AWS Virtual Private Cloud (VPC) using public and private subnets, an Internet Gateway, a NAT Gateway, route tables, Security Groups, Network ACLs, and EC2 instances. The architecture follows AWS best practices by exposing only the Bastion Host to the internet while protecting the Private EC2 instance.

# Project Objectives
•	Create a custom VPC (NB-VPC).
•	Create a Public and Private Subnet.
•	Attach an Internet Gateway.
•	Deploy a NAT Gateway with an Elastic IP.
•	Configure Public and Private Route Tables.
•	Configure Security Groups and Network ACLs.
•	Deploy NB-Public-EC2-Bastion and NB-Private-EC2.
•	Verify secure SSH connectivity and NAT internet access.

# AWS Services Used
•	Amazon VPC
•	Amazon EC2
•	Internet Gateway
•	NAT Gateway
•	Elastic IP
•	Route Tables
•	Security Groups
•	Network ACLs

# Architecture Decisions
•	NB-VPC provides an isolated network.
•	NB-Public-Subnet hosts internet-facing resources.
•	NB-Private-Subnet hosts protected workloads without public IP addresses.
•	NB-Internet-Gateway enables internet connectivity for the public subnet.
•	NB-NAT-Gateway allows outbound internet access from the private subnet.
•	NB-Public-EC2-Bastion provides secure administrative access to NB-Private-EC2.
•	Security Groups enforce instance-level security while Network ACLs provide subnet-level protection.

# Network Configuration
•	VPC CIDR: 10.0.0.0/16
•	Public Subnet: 10.0.25.0/24
•	Private Subnet: 10.0.50.0/24
Connectivity Verification
•	SSH from local computer to NB-Public-EC2-Bastion.
•	SSH from NB-Public-EC2-Bastion to NB-Private-EC2- Bastion.
•	Verified outbound internet access from NB-Private-EC2 using 'sudo yum update -y' or 'sudo dnf update -y'.
•	Confirmed the Private EC2 is not directly accessible from the internet.

# Screenshots of the project
•	VPC
•	Subnets
•	Internet Gateway
•	NAT Gateway
•	Route Tables
•	Security Groups
•	Network ACLs
•	Public EC2
•	Private EC2
•	SSH to Bastion Host
•	SSH to Private EC2
•	NAT Connectivity Test
•	Architecture Diagram
## Architecture Diagram
<img src="Screenshots/Secure VPC.jpg" width="500">


# Challenges Encountered
•	Resolved SSH connectivity issues by correcting Security Group rules.
•	Verified correct route table associations.
•	Used the Bastion Host to securely access the Private EC2.

# Lessons Learned
•	Understood VPC networking.
•	Learned the difference between public and private subnets.
•	Configured secure administrative access using a Bastion Host.
•	Learned how NAT Gateway provides secure outbound internet access.

# Future Improvements
•	Deploy across multiple Availability Zones.
•	Implement Infrastructure as Code using Terraform or AWS CloudFormation.
•	Enable CloudWatch monitoring and VPC Flow Logs.

# Conclusion
•	This project demonstrates a secure AWS networking architecture that follows cloud security best practices through network segmentation, least privilege, and controlled administrative access.

