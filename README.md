## Automated Ingestion & Response (AIR) Lab 

The Atuomated Ingestion Response lab demonstrates a full cloud security monitoring and automated incident response pipline using **AWS** and **Splunk**. 

Instead of relying on a single telemetry source to respond to threats, the lab shows how logs across the control and data plane can be correlated to provide visibility into adversary tactics and techniques and enable effective, automated mitigation.

This scenario models an external machine launching MITRE-mapped attacks against an internet-facing cloud workload operating within the same AWS account as a private instance and Splunk instance. The attacker will will move laterally from the internet-facing instace to the private instance. 

Activity from the attacker will generate telemetry across AWS API logs, VPC network flow metadata, and host-based Linux logs. These sources are ingested into the Splunk SIEM, where they are normalized, correlated, and analyzed to detect malicious behavior and trigger automated response actions via Lambda Functions.

<img src="aws-splunk.png" width="300" height="300" />

### Core components 
- Amazon Web Services CLI
- Amazon VPC
- VPC Flow Logs 
-	Amazon EC2 
-	AWS CloudTrail
-	S3
-	Amazon CloudWatch
-	Splunk 
-	AWS Lambda
-	Ubuntu
