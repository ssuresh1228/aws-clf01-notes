---
app integration: "amazon SNS: web service that makes it easy to set up, operate, and send notifications from the cloud"
---

# Amazon SNS - simple notification service
---
- **key insights:**  ^a311ff
	- web service that makes it easy to set up, operate, and send notifications from the cloud
	- delivers push notifications to clients 
	- **event-driven** computing hub  
	- native integration with many AWS event sources (includes [[compute-EC2#^e5d497|EC2]], [[storage-s3#^939999|S3]], [[database-RDS#^5a198f|RDS]]) and event destinations ([[management-monitoring-amazon-sqs#^687987|SQS]], [[compute-lambda#^74b901|Lambda]])
--- 
## user notifications 
- Push notifications can be sent straight to mobile apps, appearing as message alerts, badge updates, or sound alerts. 
- Direct addressing allows targeted delivery to single endpoints instead of all topic subscribers. 
- SNS can send text or SMS messages to SMS-enabled devices, either directly to a number or multiple numbers subscribed to a topic.
- Use **Delivery Status** for SMS disposition. 
- Mark high priority SMS as _Transactional_ for reliable delivery of crucial messages like one-time passwords. 
- Mark marketing SMS as _Promotional_. 
- Amazon SNS sends these over cheaper, reasonably reliable routes.
## monitoring 
- Monitoring SNS topics using [[monitoring-cloudwatch#^7382c4|CloudWatch]]
- Logging SNS API calls using [[monitoring-CloudTrail#^718023|CloudTrail]] 
## security 
- Encrypts topics to safeguard messages from unapproved access with server-side encryption.
- Allows private message publishing to SNS topics from a [[networking-vpc#^4ff0f7|VPC]] via VPC Endpoints through AWS PrivateLink, avoiding the public internet.
- Offers detailed control over topic endpoints, publishing permissions, and conditions via access control policies.
- AWS X-Ray can be enabled.
## limits 
- default: 10 million subscriptions/topic +  100,000 topics/account.
- 1 SMS message can be max 140 bytes
- SNS messages can contain up to 256 KB of text data except in SMS 
## pricing 
- charged based on the number of notifications you publish/deliver + API calls for managing topics/subscriptions
- Delivery pricing varies by endpoint type.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-sns/)
# Tags
- #aws-ccp-exam-notes/services/management-monitoring/sns 
---


	

