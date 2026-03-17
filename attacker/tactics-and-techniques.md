# MITRE ATT&CK-Mapped Tactics

| Tactic | Description |
| ----------- | ----------- |
| Reconnaissance | Scanning cloud instances, finding open ports, banner grabbing |
| Initial Access | Exploiting exposed SSH/FTP services |
| Execution | Running commands via SSH sessions |
| Persistence | Adding SSH keys, creating accounts |
| Privilege Escalation | Abusing misconfigurations/least privelege to gain root |
| Defense Evasion | Using legitimate tools to avoid detection |
| Credential Access | Stealing stored credentials, keys |
| Lteral Movement | SSH from one instance to another |
| Collection | Gathering files/data of interest |
| Exfiltration | Transferring data out via FTP, SCP, etc. |


Map each detection to an ATT&CK technique:
	•	SSH brute-force → T1110
	•	IAM privilege escalation → T1098
	•	CloudTrail modification → T1562.008
	•	Port scanning → T1046

   
Data exfiltration

	Flow logs > Cloudwatch
		Unusual outbound connections on port 20/21 
		Large data transfers between instances

	Forwarder
		FTP auth logs showing connections
		/var/log/vsftpd.log capturing file transfers

Infiltration

	Forwarder
		SSH brute force in /var/log/auth.log

Lateral movement

	VPC flow logs > Cloudwatch
		IP addresses 
		Meta data on instances
		
Persistence
	
	Cloudtrail > S3
		IAM changes
		Security group changes
		Access to S3, other services
 
Reconnaissance - learn as much as possible before launching an attack 

Ping scan

	
Scanning - discover which posts are open 

Enumeration - determine services and versions that are exposed 

Attack - send exploit to target 

Post-Attack - obtain a shell, install backdoor rootkit, and remove evidence 

This enables:
	•	Credential theft via IMDS
	•	API abuse detection
	•	Realistic cloud attack simulation
Internal workload has access to internal aws services
