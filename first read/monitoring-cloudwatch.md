---
monitoring: "AWS CloudWatch: monitoring tool for AWS app metrics"
---
# AWS CloudWatch
---
- **key insights:**  ^7382c4
	- monitoring tool for AWS apps
	- Displays metrics 
	- create alarms that watch metrics and send notifications or automatically make changes to the resources you are monitoring when a threshold is breached.
	- metrics repository: services put their metrics here and you get its stats 
		- can add custom metrics 
		- metrics are completely separate between regions
---
## events 
- Deliver near real-time stream of system events that describe changes in AWS resources.
- Events respond to operational changes and take corrective action as necessary: 
	- sending messages to respond to the environment
	- activating functions
	- making changes
	- capturing state information
## alarms
- watches a single metric over a specified time period
- performs one or more specified actions, based on the value of the metric relative to a threshold over time.
## logs
- Query log data
- Monitor logs from EC2 instances in real-time
- Monitor CloudTrail logged events
- By default, logs are kept indefinitely and never expire
- Archive log data
- Log Route 53 DNS queries
## pricing 
- charged per 
	- 1000 metrics requested by CloudWatch API calls
	- alarm metric (Standard/High Resolution)
	- GB log data (collected, archived, analyzed)
	- million custom/cross-account events
	- rule and matching log events
	- 1 million events (events/analysis)
	- per 100k RUM events
	- Logs Insights per query/ingested log data scanned
- monthly charges: 
	- number of metrics  
	- number of dashboards
	- per alarm metric (Standard/High Resolution), 
	- per GB log data (collected, archived, analyzed), 
	- per 100k RUM events, Logs Insights per query/ingested log data scanned.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-cloudwatch/#cloudwatch-events)
# Tags
- #aws-ccp-exam-notes/services/management-monitoring/cloudwatch 