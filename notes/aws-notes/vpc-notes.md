# Virtual Private Cloud (VPC)

AWS creates a default VPC in every region and a default public subnet in every availability zone (AZ)
- Virtual private cloud (VPC)
- Logically isolated cloud within AWS
- Spans across AZ not regions
- Multiple can exist within a region at once
- Each VPC has a block of addresses

# Subnets
- Smaller networks within a VPC
- By default, all subnets within the same vpc can talk to each other
- Each vpc has one virtual router managed by AWS. Route tables are then configured and attached to a subnet

## Other definitions
- VPC Peering: Direct connection between two vpc's
- VPC Endpoint: Private ip connection to public AWS resources
- NAT Instance vs NAT Gateway: Allows private instances internet access. Managed by you vs AWS
- Virtual private gateway & Customer gateway: Allow for VPN connection from private network over the internet
- Direct connect: Private connection to on-premise without internet connection
- Network ACL (NACL): Subnet-level firewall
- Security group: Instance-level firewall
