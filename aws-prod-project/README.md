<img width="435" alt="image" src="https://github.com/user-attachments/assets/c4ec2aa2-c577-4e8c-a9d6-e5818b82f2a2" />

Steps:
1. Create VPC
2. Create auto scaling group
   
   a. Create a Launch template
   b. Name, Desc, AMI
   c. Network settings > Create security group > Name, Desc, VPC, SG
   d. Create auto scaling group > Launch Template > Select the created template > Next
   e. Select VPC created by you
   f. Availability Zones and subnets - Select private subnets > Next > Create

3. Create bastion host: Mediator between private subnet and public subnet or external.
   Create an EC2 instance in the same VPC, public subnet and add SSH SG.

4. Connect to EC2 Instance.
   Having .pem file is necessary to connect to the instances that are in the private subnet.
   ssh -i ec2-user.pem ubuntu@private_ip_0f_instance_in_private_subnet

   Now, we are logged in to the private ec2 instance.
   Create a index.html file (vi index.html)
   python3 -m http.server 8000

5. Create Application Load Balancer
   Name, Scheme (Internet-facing), VPC, Availability Zones and subnets (Select public subnets), Security groups.
   Ceate target group
   Target type (Instances), Name, VPC, Select instances present in private subnet, Include as pending.
  
6. Copy the DNS (http://aws-prod-project-16328640.eu-north-1.elb.amazonaws.com/) and paste it in browser.
