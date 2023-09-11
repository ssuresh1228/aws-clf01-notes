---
relational database: "amazon redshift: cloud data warehousing/analytics"
---

# amazon redshift 
---
- **key insights:**  ^fd71f3
	- fully managed, cloud-based SQL analytics solution
	- securely accesses, combines, and shares data from various sources without moving or copying it.
	- integrates with AWS database, analytics, and machine learning services for real-time analytics, SQL-based machine learning, and Apache Spark analytics.
	- easy and scalable analytics in a zero-administration environment.
	- MPP engine and architecture separate compute and storage for efficient scaling, 
		- with performance innovations like AutoMaterialized Views.
	- Amazon Redshift delivers up to 5x better price performance than other cloud data warehouses.
---
**table of contents:**

--- 
## features 
- fully managed by AWS
	- no need to worry about data warehouse management tasks like hardware provisioning, software patching, setup, configuration, monitoring nodes and drives for recovery, or backups.
	- AWS handles the setup, operation, and scaling of the data warehouse, allowing you to focus on building applications.
- Redshift Serverless automatically adjusts the data warehouse capacity for high performance and you only pay for the resources used.
- Redshift has automatic tuning and provides recommendations through Redshift Advisor for warehouse management.
- Redshift Spectrum manages computing infrastructure, load balancing, planning, scheduling, and query execution on data stored in Amazon S3.
- Redshift enables analytics on all data with integration into database services like [[database-aurora#^a3c101|amazon aurora]] and [[database-RDS#^5a198f|amazon RDS]], as well as [[storage-s3#^939999|amazon S3]] data lake.
- Streamlined data ingestion with automated pipelines for streaming data or Amazon S3 files.
- Integration with AWS Data Exchange allows finding, subscribing to, and querying third-party datasets.
- Native integration with [[analytics-amazon-sagemaker|amazon sagemaker]] for creating, training, and building machine learning models in SQL.
- Redshift Serverless automatically provisions data warehouse capacity and scales underlying resources
## pricing 
### On-demand pricing 
- pay for capacity by the hour 
- use pause and resume feature to suspend billing when the cluster is not in use.
### Reserved Instances 
- significant discounts for steady-state workloads compared to on-demand instances.
### Amazon Redshift Spectrum 
- pricing is based on the number of bytes scanned when running SQL queries directly against data in an Amazon S3 data lake.
### Concurrency Scaling
- provides one hour of free credits per day, ensuring fast performance even with numerous concurrent queries and users. Usage exceeding the free credits is billed at a per-second on-demand rate.
### RMS pricing 
- for RA3 clusters is based on the amount of data stored, independent of the number of compute nodes provisioned.
### Redshift ML 
- allows users to create, train, and deploy machine learning models using SQL. 
- Costs are incurred for model creation and storage after exhausting the free tier for [[analytics-amazon-sagemaker|amazon sagemaker]]
- Redshift ML is also available for use with Amazon Redshift Serverless.

--- 
# Resources
- [FAQs](https://aws.amazon.com/redshift/faqs/?nc=sn&loc=5&dn=4)
# Tags
- #aws-ccp-exam-notes/services/databases/redshift
---


	

