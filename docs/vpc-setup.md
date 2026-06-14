\# VPC Setup



\## Created VPC



Name: project-vpc



CIDR:

10.0.0.0/16



\## Created Public Subnets



\### public-subnet-1



CIDR: 10.0.1.0/24

Availability Zone: ap-south-1a



\### public-subnet-2



CIDR: 10.0.2.0/24

Availability Zone: ap-south-1b



\## Internet Gateway



Created Internet Gateway:

project-igw



Attached Internet Gateway to:

project-vpc



\## Route Table



Created Route Table:

public-route-table



Added Route:



0.0.0.0/0 → Internet Gateway



Associated Subnets:



\* public-subnet-1

\* public-subnet-2



\## Purpose



Provide internet connectivity to EC2 instances deployed in public subnets and support Application Load Balancer traffic.



