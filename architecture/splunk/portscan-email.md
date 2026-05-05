## Active Scanning Detection (Email)

#### What it does
Sends an email everyday at noon, with a list of both external and internal addresses that attempted an unusual active scan of over 1000 port.
Identifies and enumerates any adveraries that may try to scan services or machines on the network.

<img width="705" height="525" alt="image" src="https://github.com/user-attachments/assets/0a1c4895-b1e7-4594-992e-20e7c50477d9" />
<br>
<img width="547" height="500" alt="image" src="https://github.com/user-attachments/assets/febf04aa-38b8-48a8-b775-1c72cfa4b54b" />
<br>

### Associated Search: 

`index="aws" sourcetype=aws:vpcflow` <br>
`| stats dc(dest_prt) as unique_ports count by src_ip, dest_ip` <br>
`| where unique_ports >= 1000` <br>
`| table src_ip, unique_ports, dest_ip` <br>
`| sort -unique_ports`
