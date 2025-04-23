Isolated section of the cloud

1. Subnet: Divide VPC into subnets.
2. Routing: Request from application (Route Tables)
3. Load Balancer
4. Internet Gateway (IGW)

VPC > Create VPC > VPC and more
EC2 Instance > Launch an instance > Network settings > Edit > Select VPC

Security group:
1. Operates at Instance level.
2. Stateful (Auto allowed).
3. Denies all inbound and allows all outbound traffic.

Network Access Control List (NACL):
1. Operates at Subnet level.
2. Stateless (Explicitly allowed).
3. Default - Allows all.
