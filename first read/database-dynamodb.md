---
non-relational database: "amazon DynamoDB: NoSQL database service that provides fast and predictable performance with seamless scalability"
---

# DynamoDB
---
- **key insights:**  ^fbeb12
	- NoSQL database service that provides fast and predictable performance with seamless scalability
	- It allows customers to offload the administrative tasks of managing and scaling distributed databases.
	- Customers don't need to worry about hardware provisioning, setup, configuration, capacity planning, replication, patching, or scaling.
---
**table of contents:**
- [[#features|features]]
- [[#dynamoDB accelerator - DAX|dynamoDB accelerator - DAX]]
	- [[#dynamoDB accelerator - DAX#use cases:|use cases:]]
- [[#global tables|global tables]]
- [[#pricing|pricing]]
	- [[#pricing#on-demand capacity mode|on-demand capacity mode]]
	- [[#pricing#provisioned capacity mode|provisioned capacity mode]]
--- 
## features 
- NoSQL db service w/ fast, predictable performance & seamless scalability.
- Offers encryption at rest.
- Tables store/retrieve any data amount & serve any request traffic level.
- Scale tables' throughput capacity w/o downtime or performance degradation.
- Use AWS Management Console/[[monitoring-cloudwatch#^7382c4|CloudWatch]] to monitor resource utilization & performance metrics.
- [[monitoring-CloudTrail#^718023|CloudTrail]] for monitoring logs
- On-demand backup & point-in-time recovery for DynamoDB tables (last 35 days).
- Data stored in partitions w/ SSDs & replicated across multiple AZs for high availability & durability.
- Create tables replicated across 2+ AWS Regions w/ multi-master writes support.
## dynamoDB accelerator - DAX
- fully managed in-memory cache DB for dynamoDB
- improvement: single digit millisecond to microsecond latency
- secure, scalable, highly available 
- only used with dynamoDB; [[database-elasticache#^1ed1be|elasticache]] can be used with other DBs
### use cases:
- apps that need fastest response time reads/frequent reads of limited-time items.
- Cost-sensitive read-intensive apps can offload read activity to DAX cluster and reduce read capacity units needed for DynamoDB tables.
- Repeated reads against large data set to avoid resource consumption for other apps.
## global tables 
- No need to build or maintain custom replication solution.
- Specify AWS regions for table availability.
- DynamoDB handles creation of identical tables in specified regions and propagates data changes.
- Replica Table (Replica) is a part of a global table.
- Each replica stores same data items.
- Only one replica table per region in a global table.
- Add or delete replicas from global tables.
- active-active replication: read/write to any region 
## pricing 
### on-demand capacity mode
- charges for reads/writes
- don't need to specify capacity - dynamoDB adjusts to workload
- best for:
	- creating new tables w/unknown workloads 
	- have unpredicable app traffic 
	- prefer paying by resource usage 
### provisioned capacity mode 
- specify reads/writes per sec app you expect your app to require
- autoscaling adjusts capacity based on this metric for performance/cost reduction
- best for:
	- apps with predictable traffic 
	- running apps w/ traffic that is consistent/ramps up gradually  

--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-dynamodb/)
- [notes](https://github.com/kananinirav/AWS-Certified-Cloud-Practitioner-Notes/blob/master/sections/databases.md)
- [FAQs](https://aws.amazon.com/dynamodb/faqs/)
# Tags
- #aws-ccp-exam-notes/services/databases/dynamodb  
---


	

