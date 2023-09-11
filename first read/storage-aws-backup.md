---
service: AWS backup
service-type: storage
service-description: centralizes and automates data protection across AWS services/hybrid workloads
---

# AWS backup
---
- **key insights:**  ^87e6b4
	- centralizes and automates data protection across AWS services/hybrid workloads
---
**table of contents:**
- [[#concepts|concepts]]
	- [[#concepts#backup plan %% fold %%|backup plan %% fold %%]]
		- [[#backup plan %% fold %%#can be assigned as 2 types: %% fold %%|can be assigned as 2 types: %% fold %%]]
			- [[#can be assigned as 2 types: %% fold %%#resource type:|resource type:]]
			- [[#can be assigned as 2 types: %% fold %%#resource:|resource:]]
	- [[#concepts#backup vault %% fold %%|backup vault %% fold %%]]
	- [[#concepts#backup %% fold %%|backup %% fold %%]]
	- [[#concepts#audit manager %% fold %%|audit manager %% fold %%]]
		- [[#audit manager %% fold %%#audit frameworks %% fold %%|audit frameworks %% fold %%]]
		- [[#audit manager %% fold %%#audit reports  %% fold %%|audit reports  %% fold %%]]
- [[#monitoring|monitoring]]
- [[#pricing|pricing]]
--- 
## concepts
### backup plan %% fold %% 
- policy expression; determines when/how you want your AWS resources backed up ^6d75b2
- stores new backups periodically
- can be created with API, CLI, SDK, or CloudFormation template
- supports multiple backup plans for workloads with different backup requirements
- deleting a backup plan requires deletion of all resources associated with it
#### can be assigned as 2 types: %% fold %% 
##### resource type: 
- every instance/resource
##### resource:
- single instance of a resource type 
### backup vault %% fold %% 
- container; stores/organizes your backups
- can create multiple backup vaults if you need different encryption keys/access policies for different backup groups
- encrypting backups in a vault needs a [[security-aws-kms#^bed19a|AWS KMS (key management system)]] encryption key 
- <mark style="background: #0055FF;">AWS backup vault lock</mark> allows you to force retention periods/early deletions
- cannot delete AWS backup default vault and [[storage-efs#^233be8|AWS EFS]] automatic backup vault
### backup %% fold %% 
- recovery points store resource content at specific times in backup vaults
- restore backups with <mark style="background: #6800FFBF;">AWS Backup Console</mark> or on demand manually
- can create backups across [[AWS-Regions-and-Availability-Zones.jpg|regions]] and AWS accounts
- lifecycle policies can be configured to add tags to backups
### audit manager %% fold %% 
#### audit frameworks %% fold %%
- set of controls for assessing backup practices
- finds non-compliant backup activity and resources
- 1 framework per account; max of 10 per [[AWS-Regions-and-Availability-Zones.jpg|region]]
- <mark style="background: #6800FFBF;">2 framework types: AWS backup framework and custom framework</mark>
#### audit reports  %% fold %%
- auto-generate daily and on-demand reports 
	- must create a report plan from a report template to create reports 
	- templates include backup and compliance 
- reports must be in the same region and account as the [[storage-s3#^939999|S3 bucket]]
- max of 20 report plans per account
## monitoring  
- AWS Organizations oversees backup, restore, and copy jobs across multiple AWS accounts
- amazon EventBridge gives visibility into AWS backup events 
- [[monitoring-cloudwatch#^7382c4|CloudWatch]] tracks metrics, sets alarms, and has dashboards for monitoring
- [[monitoring-CloudTrail#^718023|CloudTrail]] monitors AWS backup API calls
- Amazon SNS to subscibe to/notify of AWS backup events 
## pricing
- charged for 
	- backup storage used 
	- amount of backup data transferred between AWS regions 
	- amount of backup data restored 
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-backup/)
- [[storage-overview|storage overview]]
# Tags
- #aws-ccp-exam-notes/services/storage/backup 
---


	

