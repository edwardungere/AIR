## T1552.005 (Unsecured Credentials: Cloud Instance Metadata API)

Query IMDS on private instance for IAM role credentials

A Cloud Instance Metadata API is a service present on many cloud instances that allow users to query for information regarding that instance

This can contain names, security groups, and credentials pertaining to the instance.

AWS used IMDSv1, which has been replaced by IMDSv2. For lab purposes, IMDSv1 is enabled to demonstrate 
full detection and remediation capabilities for a known vulnerability.

Curl is used to retrieve information from IMDS. The standard is to hold IMDS information at `http://169.254.169.254`

<img width="572" height="420" alt="image" src="https://github.com/user-attachments/assets/43dd2404-3ee2-4882-8c48-7f0eb7370365" /> 

<br> Using curl `http://169.254.169.254/latest/meta-data/iam/security-credentials/` allows us to access retrieve the name of the instance's iam role

`http://169.254.169.254/latest/meta-data/iam/security-credentials/web-role` returns the role's Acccess Key ID, Secret Access Key, 
and the session token

We can now export these credentials into enviromental variables:  `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, and `AWS_SESSION_TOKEN`

Amazon STS is the service that issues temporary credentials. Querying the service will give you information about your currrent role <br>

<img width="656" height="93" alt="image" src="https://github.com/user-attachments/assets/56ea04dc-7cf6-4a0a-a7d8-1631b0940273" />
