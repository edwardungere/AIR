## T1552.005 (Unsecured Credentials: Cloud Instance Metadata API)

Query IMDS on private instance for IAM role credentials

A Cloud Instance Metadata API is a service present on many cloud instances that allow users to query for information regarding that instance

This can contain names, security groups, and credentials pertaining to the instance.

AWS used IMDSv1, which has been replaced by IMDSv2. For lab purposes, IMDSv1 is enabled to demonstrate 
full detection and remediation capabilities for a known vulnerability.

Curl is used to retrieve information from IMDS. The standard is to hold IMDS information at `http://169.254.169.254`

<img width="572" height="420" alt="image" src="https://github.com/user-attachments/assets/43dd2404-3ee2-4882-8c48-7f0eb7370365" />
