# VPC Configuration

## Design descisions

### Admin Access

Admin accesses instances through EIC (EC2 Instance Connect)
This method creates a private tunnel using the EIC endpoint and EIC service

<img src="images/eic-diagram.png" width="500" height="500">

EIC endpoint creates its own session keys with the remote instance, linux will show the endpoint's IP address (`10.0.2.49`)

<img width="1500" height="172" alt="image" src="https://github.com/user-attachments/assets/d2348a24-8a7b-4e60-a101-6c40a1c62162" />


### Internet Access
Internet access is only available to instances via the NAT gateway

Amazon's NAT gateway only allows outbound requests to the internet, and blocks any inboudn intiated requests

<img src="images/vpc-diagram.png" width="500" height="500">
