---
service: AWS Elastic Beanstalk
service-type: compute
---

# AWS Elastic Beanstalk
---
- **key insights:**  ^2dd932
	- easily deploy/manage AWS apps
	- <mark style="background: #FF000094;">automated management</mark>: handles capacity, load balancing, scaling, and health monitoring
	- <mark style="background: #930083;">PaaS</mark>: provides a platform for app development without infrastructure concerns
---
**table of contents:**
- [[#supported application platforms|supported application platforms]]
- [[#multiple deployment options:|multiple deployment options:]]
- [[#updates and management|updates and management]]
- [[#scaling/availability|scaling/availability]]
- [[#customization|customization]]
- [[#monitoring, logging, and alerts|monitoring, logging, and alerts]]
- [[#compliance|compliance]]
- [[#pricing|pricing]]
--- 
## supported application platforms 
- supports various languages/frameworks for web apps
- easy deployment from development to cloud with minimal code changes
- supported options:
	- java
	- .NET
	- node.js
	- PHP
	- ruby
	- python 
	- go
	- docker
## multiple deployment options:
- AWS management console
- CLI
- visual studio
- eclipse
- various deployment policies:
	- rolling deployment
	- immutable deployment
	- blue/green deployment
## updates and management
- automatically get platform/patch updates
- implement updates safely with immutable deployment 
- customize app properties, create alarms, and email notifications
## scaling/availability
- scale automatically with [[compute-EC2-autoscaling|autoscaling]] and [[compute-ELB#^357633|elastic load balancing]]
- enhance availability with multiple [[global infrastructure#Availability Zones fold|AZs]]
## customization
- select optimal resources, including [[compute-EC2-summary#instance types fold|EC2 instance types]] 
- keep control of AWS resources via elastic beanstalk's management capabilities if needed
## monitoring, logging, and alerts
- integrates with [[monitoring-cloudwatch|CloudWatch]] and [[monitoring-aws-xray|AWS X-Ray]] for monitoring/tracing
- set up CloudWatch alarms for threshold based notifications
- monitor app through a unified UI
- collect 40+ metrics/attributes to assess app health
- use [Elastic Beanstalk Health Dashboard](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced.html) for visualization/customization
## compliance
- complies with ISO, PCI, SOC 1, SOC 2, SOC 3, and HIPAA for regulated data processing.
## pricing
- no cost associated with elastic beanstalk itself
- only pay for underlying infrastructure use
	- EC2 instances to run app
	- [[storage-s3|S3 buckets]] to store data
	- database pricing:
		- [[database-RDS|RDS]]
		- [[database-dynamodb|dynamoDB]]
		- [[database-simpledb|simpleDB]]
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-elastic-beanstalk/)
- [elastic beanstalk details - AWS](https://aws.amazon.com/elasticbeanstalk/details/)
# Tags
- #aws-ccp-exam-notes/services/compute/elastic-beanstalk  
---