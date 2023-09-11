---
analytics: "amazon athena: interactive query service used to analyze data directly in S3/data sources using SQL"
---

# amazon athena
---
- **key insights:** 
	- serverless interactive query service  
	- analyzes data directly in [[meta-storage#Amazon S3 (Simple Storage Service)|S3]] and other data sources 
	- supports CSV, JSON, ORC, Avro, and Parquet data format 
	- executes queries in parallel 
	- uses S3 as underlying data storage 
	- integrates with [[analytics-amazon-quicksight#^68a572|amazon QuickSight]] and [[analytics-aws-glue#^08891b|AWS glue]]
---
**table of contents:**
- [[#federated queries|federated queries]]
- [[#cost controls|cost controls]]
- [[#security|security]]
- [[#pricing|pricing]]
--- 
## federated queries 
- Query data sources other than S3 using a data connector.
- Data connector implemented in [[meta-compute#AWS Lambda|Lambda]] function using Athena Query Federation SDK.
- Pre-built connectors available for popular data sources like MySQL, PostgreSQL, Oracle, SQL Server, [[database-dynamodb#^fbeb12|DynamoDB]], MSK, [[database-redshift#^fd71f3|RedShift]], OpenSearch, [[monitoring-cloudwatch#^7382c4|CloudWatch]] Logs and Metrics, [[document-db#^431fde|documentDB]] , and Kafka.
- Write custom data connector using Athena Query Federation SDK if data source not supported.
- Customize pre-built connectors for specific use cases.
## cost controls
- Create workgroups to isolate queries and enforce cost controls.
- Two types of cost controls available: per-query limit and per-workgroup limit.
- Per-query limit cancels queries that exceed the specified data scan threshold.
- Per-workgroup limit limits the total data scan for queries within a specific time frame.
- Multiple limits can be established based on hourly or daily data scan totals.
## security
- control access with [[security-identity-compliance-aws-iam#policies|IAM policies]], [[storage-s3#Resource Based Policies fold|S3 policies]], and [[storage-s3#Access Control Lists fold|ACLs]]     
## pricing 
- pay only for data scanned for executed queries 
- not charged for failed queries 
- high cost savings/performance gain by compressing/partitioning/converting data to columnar format 
	- reduces amount of data needed to scan for query execution 
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-athena/)
# Tags
- #aws-ccp-exam-notes/services/analytics/athena 
---


	

