# Kill Chain

## Stage 1 
- Attack: SSH brute force. Kali machine to hammer SSH.
- Detection: Splunk detects multiple failed SSH attempts followed by a success in VPC flow logs and auth.log.
- Response: Lambda updates the security group to block the source IP.

## Stage 2 
Discovery Attack: From the compromised public instance, run AWS CLI enumeration commands — aws s3 ls, aws ec2 describe-instances, aws iam get-user. These are all legitimate binaries, pure living off the land.
Splunk detects: CloudTrail logs show a burst of read-only API calls from an EC2 instance role — unusual enumeration pattern.
Response: Alert fires, no automated response needed here, just detection visibility.

## Stage 3 
Credential Theft via IMDS Attack: Query the instance metadata service to steal the IAM role credentials attached to the EC2 instance.
curl http://169.254.169.254/latest/meta-data/iam/security-credentials/
This is T1552.005 — one of the most well documented cloud TTPs.
Splunk detects: CloudTrail shows API calls being made with EC2 instance role credentials but from an unusual context or in unusual volume.
Response: Lambda revokes the temporary credentials by updating the IAM role's policy inline.

## Stage 4 
Lateral Movement Attack: Use the stolen credentials to access the private EC2 instance or escalate within the AWS environment. Could be assuming another role, or using the credentials to interact with services the attacker shouldn't have access to.
Splunk detects: CloudTrail shows AssumeRole or cross-service API calls that don't match normal baseline behavior.
Response: Lambda isolates the source instance by modifying its security group to deny all outbound traffic.

## Stage 5 
Collection Attack: From the compromised instance, access the S3 backup bucket and enumerate its contents — aws s3 ls s3://your-bucket and aws s3 cp to pull down the zip archives.
Splunk detects: CloudTrail S3 data events show GetObject calls on the backup bucket from the EC2 role — T1530.
Response: Lambda applies a bucket policy blocking further access from that role.

## Stage 6 
Exfiltration Attack: Use the AWS CLI to copy files out — either to an attacker-controlled S3 bucket or via curl to an external endpoint. T1537 — Transfer Data to Cloud Account.
Splunk detects: Unusual outbound data volume in VPC Flow Logs, or CloudTrail showing PutObject to an external bucket.
Response: 

<img width="2380" height="2644" alt="image" src="https://github.com/user-attachments/assets/d0fa1568-18b2-4fd3-b936-fd148c314ad3" />
