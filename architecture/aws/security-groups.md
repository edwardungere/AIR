## Security groups
Instance-level firewalls that cover each instance: <br>
### Splunk instance SG <br>
**Inbound Rules**
| Type | Protocol | Port Range |Source| Note |
|--------|--------|--------|--------|--------|
|SSH|TCP|22|10.0.2.49|EIC SSH| 
|Custome TCP|TCP|9997|10.0.4.193|Web server logs|
|Custom TCP|TCP|8000|alb-sg|ALB forwarding|

Splunk needs to be able to:
- Allow acess from EC2 Instance Connect Endpoint located in 10.0.2.0/24
- Forward its Web server on 8000 over an Application Load Balancer to the face the internet
- Recieve logs in port 9997 from Splunk Forwarder agents from the web server
- Have full outbound access through NAT gateway

### Web server SG <br>
**Inbound Rules**
| Type | Protocol | Port Range |Source| Note |
|--------|--------|--------|--------|--------|
|SSH|TCP|22|10.0.2.49|EIC SSH| 
|All ICMP - IPv4|ICMP|All|64.99.120.14/32|Vulnerable SSH|
|SSH|TCP|22|64.99.120.14/32|Vulernable reconnaissance|
|HTTP|TCP|80|0.0.0.0|Web page|

The web server needs to be able to:
- Allow access from EC2 Instance Connect Endpoint located in 10.0.2.0/24
- Allow open ICMP traffic for port scanning **Specifically to personal IP address**
- Allow open SSH (password authentication) **Specifically to personal IP address**
- Server its web page to the internet over port 80
- Full outbound access through NAT gateway
  
### EIC Endpoint SG <br>
**Outbound Rules**
| Type | Protocol | Port Range |Source| Note |
|--------|--------|--------|--------|--------|
|SSH|TCP|22|10.0.0.0/16|EIC SSH| 

The eic endpoint needs to be able to:
- SSH into any instance within the VPC
- Automatically authenticates with AWS user, no inbound rules needed

### ALB SG <br>
**Inbound Rules**
| Type | Protocol | Port Range |Source| Note |
|--------|--------|--------|--------|--------|
|HTTP|TCP|80|64.99.120.14/32|http access to Splunk web| 

The alb endpoint needs to be able to:
- Allow access to Splunk web to personal IP address

