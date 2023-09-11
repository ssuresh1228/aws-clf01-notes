
---
Table of Contents:

---
# cloudtrail vs cloudwatch 
---
- **key insights:**
	- CloudWatch is for application monitoring
	- CloudTrail is for logging AWS account activity 
---
- CloudWatch monitors AWS resources/apps, tracks metrics, logs, alarms. Default basic monitoring for EC2, EBS, RDS DB instances. 
- CloudTrail records API activity, logs requester, services used, actions, parameters, responses. 
	- Logs stored in S3 bucket/specified CloudWatch Logs group. 
	- Detailed monitoring available for extra cost. 
- CloudTrail provides free copy of management event logs per region, charges for data event logs. Ensures compliance, regulatory standards. 
- <mark style="background: #00FF266B;">CloudWatch Logs for application logs, CloudTrail for AWS account activity</mark>. 
- <mark style="background: #6800FFBF;">CloudWatch Events for system events, CloudTrail for API calls</mark>. 
- CloudTrail delivers event within 15 minutes of API call. 
- CloudWatch delivers metric data in 5/1 minute periods, log data every five seconds.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-cloudtrail-vs-amazon-cloudwatch/)
# Tags
- #aws-ccp-exam-notes/services/management-monitoring/cloudtrail 
- #aws-ccp-exam-notes/services/management-monitoring/cloudwatch 


	

