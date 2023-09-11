---
app integration: "amazon SQS: allows independent systems or components to communicate with each other by sending and receiving messages while maintaining loose coupling."
---

# amazon SQS
---
- **key insights:**  ^687987
	- hosted queue (standard/FIFO)
	- allows independent systems or components to communicate with by sending/receiving messages while maintaining loose coupling.
	- uses [[security-aws-kms#^bed19a|KMS]] for server-side encryption
	- can be accessed via [[networking-vpc#^4ff0f7|VPC]] without using public IP/internet
---  
## features
- You manage messaging permissions for an SQS queue and its server-side encryption. It 
- ensures durability through multi-server message storage and high availability via redundant infrastructure
- scales to handle load spikes, processing requests independently
- allows concurrent messaging by locking messages during processing.
## monitoring and security
- monitor SQS queues with [[monitoring-cloudwatch#^7382c4|CloudWatch]]
- log SQS API calls with [[monitoring-CloudTrail#^718023|CloudTrail]]
- uses [[security-identity-compliance-aws-iam#^ab9f15|IAM]] for authorization 
- uses [[security-aws-kms#^bed19a|KMS]] for server-side encryption
	- messages are encrypted as soon as SQS receives them 
	- stored in encrypted format
	- decrypted only when sent to authorized consumer 
## pricing 
- pay per 1 million SQS requests; depends on queue type used
	- requests: 
		- API actions, FIFO requests, [[storage-s3#^939999|S3]]/[[security-aws-kms#^bed19a|KMS]] interaction, 
		- single request of 1-10 messages w/ max payload of 256 kb
			- each 64kb chunk is 1 request 
- 1 GB free data transfer/month, then pay in TB/month 

--- 
# Resources
- [cheat sheet]()  
# Tags
- #aws-ccp-exam-notes/services/management-monitoring/sqs 
---


	

