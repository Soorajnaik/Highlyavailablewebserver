# Highlyavailable_Webserver

## Resources Used 
- Route53-Hosted Zones
- Route53-Health Checks
- EC2-Auto Scaling Group
- EC2-Load Balancer
- EC2-Security Groups
- CloudFormation

## Summary:
- I created 2 Autoscaling groups. Each will give rise to EC2 instances with the 2 different versions of the application each
- Both the Autoscaling groups are attached to their respective Application Load Balancers. If ever were the Auto Scaling create multiple instances the load balancer would distribute the load.
- I have also created a Route53 Health Check which hits https://date.nager.at/ and checks the respective API which I have user whether its live.
- I have a registered domain which I have mapped to the two different load balancer urls using DNS Failover Routing.
- Here if the Health-Check passes we would redirect user http requests to the load balancer attached to the Ec2 instances which host Version 2 of the Application.
- If the Health-Check fails we would redirect user http requests to the load balancer attached to the Ec2 instances which host Version 1 of the Application.





![test](https://sooraj036bucket.s3.us-west-2.amazonaws.com/Untitled+Diagram.drawio+(3).png)


