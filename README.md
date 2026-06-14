\# AWS Load Balanced Web Application



\## Project Overview



This project demonstrates the deployment of a highly available and scalable web application on AWS using Amazon EC2, Application Load Balancer (ALB), CloudWatch Monitoring, and SNS Email Alerts.



The application is deployed across multiple public subnets and uses an Application Load Balancer to distribute traffic across multiple EC2 instances, ensuring high availability and fault tolerance.



\## Architecture



!\[Architecture Diagram](architecture/architecture-diagram.png)

           Internet
                        │
                        ▼
         Application Load Balancer (web-alb)
                        │
                        ▼
            Target Group (web-target-group)
                        │
           ┌────────────┴────────────┐
           ▼                         ▼
     web-server-1              web-server-2
        (Nginx)                   (Nginx)

────────────────────────────────────────────
VPC: project-vpc (10.0.0.0/16)

  public-subnet-1          public-subnet-2
     10.0.1.0/24             10.0.2.0/24

Internet Gateway
Route Table
Security Groups
────────────────────────────────────────────

CloudWatch Metrics
        │
        ▼
CPU Alarm
        │
        ▼
SNS Email Alerts




\## AWS Services Used



\* Amazon VPC

\* Public Subnets

\* Internet Gateway

\* Route Tables

\* Security Groups

\* Amazon EC2

\* Application Load Balancer (ALB)

\* Target Groups

\* Amazon CloudWatch

\* Amazon SNS



\## Architecture Components



\### Networking



\* VPC: `project-vpc`

\* Public Subnet 1: `10.0.1.0/24`

\* Public Subnet 2: `10.0.2.0/24`

\* Internet Gateway: `project-igw`

\* Route Table: `public-route-table`



\### Compute



\* web-server-1

\* web-server-2



\### Load Balancing



\* Application Load Balancer: `web-alb`

\* Target Group: `web-target-group`



\### Monitoring



\* CloudWatch Metrics

\* CPU Utilization Alarm



\### Notifications



\* SNS Email Alerts



\## Features



\* High Availability Architecture

\* Load Balancing Across Multiple EC2 Instances

\* Health Checks and Automatic Failover

\* Secure Access Using Security Groups

\* CloudWatch Monitoring

\* SNS Email Notifications

\* Public Web Access Through ALB



\## Deployment Steps



1\. Created Custom VPC

2\. Created Public Subnets

3\. Configured Internet Gateway

4\. Configured Route Tables

5\. Created Security Groups

6\. Launched EC2 Instances

7\. Installed and Configured Nginx

8\. Created Target Group

9\. Registered EC2 Instances

10\. Created Application Load Balancer

11\. Configured Health Checks

12\. Configured CloudWatch Monitoring

13\. Created CloudWatch Alarm

14\. Configured SNS Email Notifications



\## Screenshots



\### VPC Setup



!\[VPC](screenshots/vpc-created.png)



\### Public Subnets



!\[Subnets](screenshots/subnets-created.png)



\### Internet Gateway



!\[Internet Gateway](screenshots/internet-gateway.png)



\### Route Table



!\[Route Table](screenshots/route-table.png)



\### EC2 Instances



!\[EC2 Instances](screenshots/ec2-instance-list.png)



\### Application Load Balancer



!\[ALB](screenshots/alb-created.png)



\### Target Group



!\[Target Group](screenshots/target-group.png)



\### CloudWatch Monitoring



!\[CloudWatch](screenshots/cloudwatch-metrics.png)



\## Project Structure



```text

aws-load-balanced-webapp/

│

├── README.md

│

├── architecture/

│   └── architecture-diagram.png

│

├── screenshots/

│

├── docs/

│   ├── vpc-setup.md

│   ├── ec2-setup.md

│   ├── alb-setup.md

│   └── cloudwatch-setup.md

```



\## Troubleshooting Experience



During implementation, SSH access initially failed because the public subnets were not associated with the custom route table containing the Internet Gateway route (`0.0.0.0/0`). After associating the subnets with the correct route table, internet connectivity and SSH access were restored successfully.



\## Author



Shubham Shewale



AWS | Linux | Docker | Kubernetes | DevOps



