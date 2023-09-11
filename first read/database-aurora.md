---
relational database: "amazon aurora: fully managed relational db engine for mySQL and postgres"
---

# amazon aurora
---
- **key insights:**  ^a3c101
	- modern relational database service
	- Performance and high availability at scale
	- Open-source MySQL- and PostgreSQL-compatible editions
	- Developer tools for serverless and ML-driven apps
	- Distributed, fault-tolerant, self-healing storage system
	- Auto-scales up to 128 TiB per database instance (10 GB increments)
	- Up to 15 low-latency read replicas
	- Point-in-time recovery, continuous backup to Amazon S3
	- Replication across three Availability Zones
	- Fully managed service, automates administration tasks
	- Security, availability, reliability at one-tenth of the cost
--- 
## hardware/scaling 
- 10 GB min storage 
- based on your database usage, aurora storage will automatically grow up to 128 TiB in 10 GB increments with no impact to database performance
- both scaling options below will have an availability impact for a few minutes as scaling operation is performed.
### aurora serverless (autoscaling)
- on-demand, autoscaling config for Amazon Aurora. 
- Scales DB compute resources based on app demand. 
- Run DB in cloud w/o capacity worries. 
- Specify desired capacity range, DB scales as needed.
### manual scaling
- AWS Management Console allows manual scaling of compute resources for databases.
- Scaling can be done by selecting the desired DB instance type.
- Changes can be applied during the specified maintenance window or using the "Apply Immediately" flag.
## pricing 
- Aurora Serverless: capacity adjusts automatically and you only pay for what you use
- Provisioned On-Demand Instances charge per DB instance-hour with no commitments or upfront features
	- can also choose Provisioned Reserved Instances for extra savings.
- Charges vary based on cluster configuration (Aurora Standard or Aurora I/O-Optimized).
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-aurora/)
- [notes](https://github.com/kananinirav/AWS-Certified-Cloud-Practitioner-Notes/blob/master/sections/databases.md#amazon-aurora) 
- [FAQs](https://aws.amazon.com/rds/aurora/faqs/)
# Tags
- #aws-ccp-exam-notes/services/databases/aurora  
---


	

