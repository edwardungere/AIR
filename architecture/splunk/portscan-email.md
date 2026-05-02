## Active Scanning Detection (Email)

Sends an email everyday at noon, with a list of both external and internal addresses that attempted an unusual active scan of over 1000 port

<img width="705" height="525" alt="image" src="https://github.com/user-attachments/assets/0a1c4895-b1e7-4594-992e-20e7c50477d9" />
<br>
<img width="705" height="525" alt="image" src="https://github.com/user-attachments/assets/51e3e085-6b9f-4f71-b14e-86f2e78da995" />
<br>

Search: 

`index="aws" sourcetype=aws:vpcflow` 

`| stats dc(dest_prt) as unique_ports count by src_ip, dest_ip`

`| where unique_ports >= 1000`

`| table src_ip, unique_ports, dest_ip`

`| sort -unique_ports`
