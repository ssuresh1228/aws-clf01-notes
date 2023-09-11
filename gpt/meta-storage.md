---
gpt-meta: "aws ccp: storage services"
---
# meta: AWS Storage services
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	-  [[summary-storage]]
--- 
## AWS Backup: 
- Centralizes and automates data protection for AWS services and hybrid workloads.
- supports multiple backup plans 
- charged based on backup storage used, data transferred between AWS regions, and data restored.
## Amazon EBS (Elastic Block Store): 
- block-level storage volumes for EC2 instances
- suitable for file systems, databases, and apps needing precise updates
- billed based on provisioned storage amount in GB per month
## Amazon EFS (Elastic File System): 
- scalable, serverless file storage for various AWS compute services. 
- file system access to EC2, ECS, EKS, Fargate, and Lambda through a file system interface.
- Pricing is based on storage used and provisioned throughput values.
## Amazon S3 (Simple Storage Service): 
- Scalable object storage. Stores data as objects in buckets  
- different storage classes for different access patterns.
- S3 glacier used for long term archival
	- <span style='color:#eb3b5a'>S3 standard: frequent access; general use</span>
	- <span style='color:#fa8231'>S3 standard_IA: infrequent access/long term. data stored in multiple AZs</span>
	- <span style='color:#20bf6b'>S3 onezone_IA: same as standard_IA but stores data in 1 AZ for cheaper price</span>
	- <span style='color:#0fb9b1'>S3 glacier instant retrieval: access archived data instantly</span>
	- <span style='color:#3867d6'>S3 glacier flexible retrieval: for archived data accessed once/twice per year</span> 
	- <span style='color:#8854d0'>S3 glacier deep archive: for rarely accessed data (cheapest)</span>
- Pricing is based on storage type and data amount stored/transferred.
## AWS Snowball: 
- Large data transfer, local to AWS Cloud. Storage, compute capabilities included. Local processing, edge computing options. Price: Snowball Edge machine type, term of use.
## AWS Storage Gateway: 
- Hybrid storage, on-premises and cloud. 
- Integrates on-premises apps/workflows, block/object storage in cloud. 
- Pricing: storage type/amount, requests, data transferred out of AWS.
## AWS Snowmobile: 
- Exabyte-scale data transfer service for moving extremely large amounts of data to AWS Cloud 
- can transfer up to 100PB per Snowmobile 
- pricing based on the amount of data stored on Snowmobile per month 
---
# tags:
- #gpt-meta/aws-ccp/storage 