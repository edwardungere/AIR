## DET0817 (Detection of Scanning IP Blocks)
**Detection of Scanning IP Blocks**

Monitor the content for unusual activity or active scanning attempts. Try to identify repeated connection attempts, unusual scanning behaviors, or probing activity targeting a single or multiple IP addresses in a network.

<img width="2848" height="596" alt="image" src="https://github.com/user-attachments/assets/ed58c7e2-eb53-46db-807a-9bfd60f263ab" />

### Associated Search 

`index="aws" sourcetype="aws:vpcflow" NOT src_ip=10.0.* dest_prt=22`

`| stats count by src_ip `

`| where count >=10 `

`| sort -count`

### What it does

Filters the 'aws' index, for VPC Flow logs, and filters for any logs containing a source address originating from outside the local network attempting to reach port 22

