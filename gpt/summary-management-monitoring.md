---
gpt-summary: "aws ccp: management/monitoring"
---
# GPT summary: AWS management/monitoring 
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	-  [[management-monitoring-overview]]
--- 
## AWS SNS: (Simple Notification Service):
- <span style='color:#eb3b5a'>use case:</span>
  - Send notifications to users via SMS, email, or push notifications.
- <span style='color:#0fb9b1'>overview:</span>
  - AWS service for sending messages to multiple subscribers.
- <span style='color:#8854d0'>pricing:</span>
  - Pay-as-you-go pricing based on message delivery.
## Amazon SQS:
- <span style='color:#eb3b5a'>use case:</span> 
	- enables independent systems or components to communicate by sending and receiving messages while maintaining loose coupling.
- <span style='color:#0fb9b1'>overview:</span> 
	- hosted queue service that allows messaging between systems or components.
	- supports server-side encryption using AWS KMS.
	- can be accessed via VPC without using public IP/internet.
- <span style='color:#8854d0'>pricing:</span> 
	- pay per 1 million SQS requests; pricing depends on the queue type used.
	- 1 GB free data transfer per month, then pay per TB per month.
## AWS License Manager
- <span style='color:#eb3b5a'>use case:</span>
	- Centrally manage software licenses in AWS/on-premises
- <span style='color:#0fb9b1'>overview:</span>
	- Centrally manages software licenses in AWS/on-premises
	- Provides control and visibility into license usage
	- Supports various licensing models
	- Allows license purchase from different sources
- <span style='color:#8854d0'>pricing:</span>
	- Charged for AWS resources used to run applications
## AWS CloudTrail:
- <span style='color:#eb3b5a'>use case:</span>  
	- Auditing AWS actions and monitoring account activity
- <span style='color:#0fb9b1'>overview:</span> 
	- Logs events across AWS console, CLI, SDKs
	- Provides a history of events and records 90 days of activity in CloudWatch logs
	- Offers CloudTrail Lake for log aggregation, immutable storage, and querying via SDKs and CLI
	- CloudTrail Insights identifies unusual account activity
	- Provides log file integrity validation
- <span style='color:#8854d0'>pricing:</span> 
	- First copy of management events free in each region, additional copies charged
	- Data events recorded and charged only for specified Lambda functions, DynamoDB tables, S3 buckets
	- S3 charges apply once CloudTrail trail is set up; logs delivered to S3 bucket
## AWS CloudWatch  %% fold %% 
- <span style='color:#eb3b5a'>use case:</span>  
	- Monitoring tool for AWS apps
	- Create alarms to watch metrics and take automated actions
- <span style='color:#0fb9b1'>overview:</span> 
	- Displays metrics and provides insights
	- Delivers real-time system events
	- Monitors logs from EC2 instances and CloudTrail
- <span style='color:#8854d0'>pricing:</span> 
	- Charged per metrics, log data, and events
	- Monthly charges for metrics, alarms, log data, and RUM events
## CloudTrail vs CloudWatch  %% fold %% 
- <span style='color:#eb3b5a'>use case:</span>  
	- CloudWatch: application monitoring
	- CloudTrail: logging AWS account activity
- <span style='color:#0fb9b1'>overview:</span> 
	- CloudWatch: monitors AWS resources/apps, tracks metrics, logs, alarms
	- CloudTrail: records API activity, logs requester, services used, actions, parameters, responses
- <span style='color:#8854d0'>pricing:</span> 
	- CloudWatch: default basic monitoring for EC2, EBS, RDS DB instances; detailed monitoring available for extra cost
	- CloudTrail: provides free copy of management event logs per region, charges for data event logs
## AWS Config
- <span style='color:#eb3b5a'>use case:</span> 
	- Assess, audit, and evaluate the configurations of your AWS resources.
- <span style='color:#0fb9b1'>overview:</span> 
	- AWS Config helps with security, governance, compliance auditing, and troubleshooting by tracking resource configurations over time and recording third-party configurations.
	- exports a full resource inventory and provides ready-made rules to check resource setups.
- <span style='color:#8854d0'>pricing:</span> 
	- Charged based on the number of configuration items and AWS Config rules evaluations recorded. Not based on the number of active rules in the account per region. 
	- Charged only once for recording a configuration item and per conformance pack evaluation per region.
## AWS Organizations:
- <span style='color:#eb3b5a'>use case:</span> 
	- Manage and centrally govern AWS resources as businesses grow and scale.
- <span style='color:#0fb9b1'>overview:</span> 
	- Policy-based management for multiple AWS accounts.
	- Create groups of accounts and apply policies.
	- Policy framework for multiple AWS accounts.
	- Consolidated billing for all accounts.
	- High availability with data replication.
- <span style='color:#8854d0'>pricing:</span> 
	- Free service.
## AWS Secrets Manager: 
- <span style='color:#eb3b5a'>use case:</span>  
	- Rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle
- <span style='color:#0fb9b1'>overview:</span> 
	- Easily rotate, manage, and retrieve secrets
	- Encrypts secrets at rest using CMKs
	- Supports rotating credentials for RDS, DocumentDB, and RedShift
- <span style='color:#8854d0'>pricing:</span> 
	- Pay based on number of secrets stored + API calls made/month
## AWS Systems Manager 
- <span style='color:#eb3b5a'>use case:</span>  
	- Centralize operational data from multiple AWS services and automate tasks across your AWS resources.
- <span style='color:#0fb9b1'>overview:</span> 
	- Create logical groups of resources and view their activity, configuration changes, alerts, and software inventory.
	- Collect info on instances and ensure software compliance.
	- Schedule admin tasks across instances.
- <span style='color:#8854d0'>pricing:</span> 
	- Pay for what you use.
	- Charged based on package transfer, API calls, and configuration requests.
## AWS Support Trusted Advisor
- <span style='color:#eb3b5a'>use case:</span>  
	- Identify and resolve common issues in your AWS environment to optimize performance, security, and cost.
- <span style='color:#0fb9b1'>overview:</span> 
	- provides automated checks and recommendations to help you improve your AWS infrastructure. 
	- analyzes your resources and configurations to identify potential issues and offers best practices to optimize performance, security, and cost.
- <span style='color:#8854d0'>pricing:</span> 
	- Available as part of AWS Support plans, with different levels of access and features. Pricing varies based on the support plan chosen.
---
# tags:
- #gpt-summary/aws-ccp/management-monitoring 