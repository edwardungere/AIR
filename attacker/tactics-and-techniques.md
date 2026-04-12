# MITRE ATT&CK-Mapped Tactics and Techniques

| Tactic | Description | Technique | Technique ID | 
| ----------- | ----------- | ----------- | ----------- |  
| Reconnaissance | Scanning cloud instances, finding open ports, banner grabbing | Active Scanning | T1595 |
| Initial Access | Exploiting exposed SSH/FTP services | Exploit Public Facing Application | T1190 | 
| Execution | Running commands via SSH sessions | Command and Scripting Interpreter | T1059 |
| Persistence | Adding SSH keys, creating accounts | Local Account | T1136.001 |
| Privilege Escalation | Abusing misconfigurations/least privelege to gain root | Abuse Elevation Control | T1548.003 |
| Credential Access | Stealing stored credentials, keys | Unsecured Credentials: Cloud Instance Metadata API | T1552.005 |
| Discovery | Listing cloud resources | Cloud Infrastructure Discovery | T1580 |
| Lateral Movement | SSH from one instance to another | SSH | T1021.004 |
| Collection | Gathering files/data of interest | Data from Cloud Storage | T1530 |
| Exfiltration | Transferring data out to external cloud account | Transferring Data to Cloud Account | T1537 |

   

