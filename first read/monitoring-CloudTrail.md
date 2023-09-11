---
monitoring: "AWS CloudTrail: logs all AWS actions as viewable events for auditing"
---

# AWS CloudTrail 
---
- **key insights:**  ^718023
	- logs events across AWS console, CLI, SDKs
	- Always on and used to audit API activity
	- Events viewable in history
	- Records 90 days of activity in CloudWatch logs
	- <span style='color:#fa8231'>CloudTrail Lake</span> for log aggregation, immutable storage, querying via SDKs and CLI
	- <span style='color:#eb3b5a'>CloudTrail Insights</span> identifies unusual account activity like IAM activities, resource provisioning spikes
	- Use <span style='color:#20bf6b'>CloudTrail log file integrity validation</span> to check if log file was modified, deleted, unchanged after delivery
	- First copy of management events free in each region, additional copies charged
	- Data events recorded and charged only for specified [[compute-lambda#^74b901|Lambda]] functions, DynamoDB tables, [[storage-s3#^939999|S3 buckets]]
	- S3 charges apply once CloudTrail trail is set up;  logs deliverd to S3 bucket
--- 
[[storage-s3#^939999|S3 buckets]] 
[[compute-lambda#^74b901|Lambda]] functions
[[database-dynamodb#^fbeb12|DynamoDB]] tables
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-cloudtrail/) 
# Tags
- #aws-ccp-exam-notes/services/management-monitoring/cloudtrail   
---