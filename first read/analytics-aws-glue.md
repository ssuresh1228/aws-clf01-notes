---
analytics: "AWS glue: extract/transform/data for analytics"
---

# AWS glue
---
- **key insights:**  ^08891b
	- fully managed service 
	- extract/transform/load (ETL) data for analytics
	- discover/search across different AWS datasets w/o moving your data
	- consists of central metadata repo + ETL engine + flexible scheduler
---
**table of contents:**
- [[#use cases|use cases]]
- [[#monitoring|monitoring]]
- [[#security|security]]
- [[#pricing|pricing]]
--- 
## use cases 
- Use AWS Glue to query Amazon [[storage-s3#^939999|S3]] data without moving it.
- Transform and enrich log data in your data warehouse with ETL scripts.
- Trigger ETL jobs in AWS Glue with new data in S3 using [[compute-lambda#^74b901|Lambda]].
- Find and manage all datasets in one place with AWS Glue Data Catalog 
	- Persistent metadata store.
	- Data used as ETL job sources/targets stored in data catalog.
	- Only one data catalog per region.
	- AWS Glue Data catalog can be used as Hive metastore.
	- Contains database and table resource links.
## monitoring
- auditing with [[monitoring-CloudTrail#^718023|CloudTrail]]
- [[monitoring-cloudwatch#^7382c4|CloudWatch]] events to automate actions when an event matches a rule 
	- CloudWatch Logs: monitor/store/access logs from different sources 
	- real time logs available 
## security 
- Security config: can encrypt data at rest w/ SSE-S3 & SSE-KMS
- S3 encryption mode
- CloudWatch logs encryption mode
- Job bookmark encryption mode
- [[security-aws-kms#^bed19a|AWS KMS]] keys: encrypt job bookmarks & logs
- supports symmetric [[security-aws-kms#CMKs - customer managed keys|CMKs]] 
- AWS provides SSL encryption for data in transit
- Access management:  [[security-identity-compliance-aws-iam#identity-based policies fold|Identity-Based Policies]] and [[security-identity-compliance-aws-iam#resource-based policies fold|Resource-Based Policies]]
- Grant cross-account access in AWS Glue w/ Data Catalog resource policy & IAM role
- Data Catalog Encryption: metadata encryption & encrypt connection passwords
- Create policy for data catalog for fine-grained access control.
## pricing 
- Charged hourly based on DPUs used for crawler. 
- Data Catalog storage: 
	- Charged monthly if >1 million objects stored. 
	- Charged monthly if >1 million requests in a month.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-glue/)
# Tags
- #aws-ccp-exam-notes/services/analytics/glue 


	

