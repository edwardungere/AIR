# Data Flow
AIR uses an <a href="../aws/sqs-configuration.md">SQS-Based S3</a> pulling method.
This method of retrieving logs involves Splunk being notified by an SNS -> SQS Fanout. <br>
This is followed by SQS queue messages notifying Splunk once new logs have been created. <br> If any messages are lost they are stored in a DLQ (Dead Letter Queue) <br>

<img src=images/data-flow-diagram.png height="500" width="600">

Other retrieval messages include:

