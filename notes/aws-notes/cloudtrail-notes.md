# CloudTrail

### Overview
- Who performed what and when on aws resources
- Logs api activity across AWS
- All actions made in AWS Console, CLI, SDK, are essentially making api calls
- Logs higher-level applications such as Cloudformation
- Logs are saved to CloudWatch or S3
  
### Management events: 
-  Control plane of events, records creation/modification of resources
-  Logging on/off automatically turned on
-  Action taken on AWS resources

### Data events:
- Quieries, invocations of lambda functions
- s3:PutObject, s3:GetObject are data events
- Actions taken wihtin AWS resources, data plane
- Not enabled by default

### Insights
- Use machine learning to detect for suspicious events

### Format

**Event Name | Event Time | User | Event Source | Resource Type | Resource Name**
