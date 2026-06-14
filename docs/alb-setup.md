\# Application Load Balancer Setup



\## Target Group



Created:



\* web-target-group



Registered Targets:



\* web-server-1

\* web-server-2



\## Application Load Balancer



Created:



\* web-alb



Configuration:



\* Internet-facing

\* IPv4

\* HTTP Listener (Port 80)



\## Health Checks



Protocol: HTTP



Path: /



\## Verification



Verified traffic routing across multiple EC2 instances.



Verified target health checks.



Verified automatic failover when a target becomes unhealthy.



\## Screenshots



\* target-group.png

\* alb-created.png

\* healthy-targets.png

\* alb-dns-test.png



