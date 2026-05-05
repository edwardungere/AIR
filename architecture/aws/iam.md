## Users and roles

### Admin

### Splunk
Splunk permissions
|   S3   |  SQS  |
|------|-------|
|  `Get*`  |  `GetQueueAttributes`  |
|  `List*`  |  `ListQueues`   |
|  `Delete*`  |  `ReceiveMessage`    |
|    | `GetQueueUrl`    |
|    | `DeleteMessage`   |

### Web server

No S3 bucket-level policies or SQS Queue/SNS Topic policies are required since all access remains within one account.
