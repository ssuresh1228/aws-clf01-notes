---
gpt-summary: "aws ccp: storage"
---
# summary: AWS storage services 
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	-  [[storage-overview]]
--- 
## AWS backup  %% fold %% 
### use case: %% fold %% 
- Centralizes and automates data protection across AWS services and hybrid workloads.
### overview: %% fold %% 
- Centralizes and automates data protection for AWS services and hybrid workloads.
- Supports multiple backup plans for different backup requirements.
### pricing: %% fold %% 
- Charged based on backup storage used, data transferred between AWS regions, and data restored
## amazon EBS - elastic block store  %% fold %% 
### use case: %% fold %% 
- Storage for EC2 instances
### overview: %% fold %% 
- Block level storage volumes for EC2 instances
- Good for file systems, databases, and apps needing precise updates/raw block level storage
### pricing: %% fold %% 
- Billed based on provisioned storage amount in GB per month
## Amazon EFS: Elastic File Service: %% fold %% 
### use case:  %% fold %% 
- Scalable, serverless file storage for various AWS compute services
### overview:  %% fold %% 
- Fully managed file storage service that scales automatically from gigabytes to petabytes
- Provides file system access to EC2, ECS, EKS, Fargate, and Lambda through a file system interface
- Supports Network File System version 4 protocol and offers strong data consistency and file locking
### pricing:  %% fold %% 
- Pay only for storage used by your file system(s)
- Provisioned throughput costs are determined by your specified throughput values
## Amazon S3:  %% fold %% 
### use case:  %% fold %% 
- Scalable object storage for storing and retrieving data
### overview:  %% fold %% 
- Stores data as objects in buckets
- Objects consist of files and optional metadata
- Uses unique keys to identify objects
- Virtually unlimited storage capacity
- Offers different storage classes for different access patterns:
	- S3 Standard for frequently accessed data
	- S3 Standard-IA for infrequently accessed data
	- S3 One Zone-IA for cost-saving but less secure storage
	- S3 Intelligent Tiering for automatic data movement between frequent and infrequent tiers
- S3 Glacier for long-term archiving
- S3 Glacier has different storage types:
	- Glacier Instant Retrieval for quick access
	- Glacier Flexible Retrieval for archive data accessed once or twice per year
	- Glacier Deep Archive for rarely accessed data with the lowest cost
- S3 on Outposts for on-premises storage
### pricing:  %% fold %% 
- Pay for storage and data transfer
- No charge for creating buckets
- Different pricing tiers for different storage classes and retrieval options

## S3 vs EBS vs EFS %% fold %% 
### use case:  %% fold %% 
- S3: Web serving, backups, big data analytics
- EBS: Boot volumes, databases, data warehousing
- EFS: Web serving, enterprise applications, media and entertainment
### overview:  %% fold %% 
- S3: Object storage for any kind of data, accessible to anyone with permissions
- EBS: Persistent block storage for EC2 instances, low-latency access
- EFS: POSIX-compliant file storage for EC2 instances, concurrent access
### pricing:  %% fold %% 
- S3: Based on storage used, cheaper with more storage
- EBS: Pay per GB/month of provisioned storage, plus snapshot data
- EFS: Pay only for storage used by your file system(s) + throughput values

## AWS Snowball:  %% fold %% 
### use case:  %% fold %% 
- Transfer large amounts of data between local environment and AWS Cloud
- Perform local processing and edge computing tasks
### overview:  %% fold %% 
- Snowball device with storage and compute capabilities for AWS
- Designed for scenarios requiring local processing, edge computing, and data transfer between local environment and AWS Cloud
- On-board S3-compatible storage and compute for Lambda functions and EC2 instances
- Storage optimized and compute optimized options available
- Compute optimized option includes GPU for accelerated computing
### pricing:  %% fold %% 
- Charges depend on the chosen Snowball Edge machine type
- Charges are based on the selected term of use: On demand, 1-year commitment, or 3-year commitment
- Service fee is charged per data transfer job, including 10 days of on-site Snowball Edge device usage
- Additional fees are incurred for each day beyond 10 days
- One-time setup fee is applied per job ordered through the console

## AWS storage gateway  %% fold %% 
### use case:  %% fold %% 
- Hybrid storage between on-premises and cloud
- Integrates on-premises apps/workflows with block and object storage
### overview:  %% fold %% 
- Hybrid storage solution for integrating on-premises applications and workflows with block and object storage in the cloud
- Supports file gateway, volume gateway, and tape gateway
- File gateway provides a file interface for S3 and allows direct access to S3 data from any AWS Cloud application or service
- Volume gateway provides cloud-backed volumes that can be mounted as iSCI devices on on-premises app servers
- Cached volumes store frequently accessed data subsets locally and retain the rest in S3
- Stored volumes provide low-latency access to the entire dataset and asynchronously back up snapshots to S3
- Tape gateway archives backup data in S3 Glacier and provides a virtual tape library interface
- Supports AWS KMS for data encryption and IAM for authentication/access control
### pricing:  %% fold %% 
- Charged based on the type and amount of storage used, requests made, and data transferred out of AWS
- Tape Gateway is charged based on the amount of data written to the tape, not tape capacity
## Service Name: AWS Snowmobile %% fold %% 
### Use Case: %% fold %% 
- Exabyte-scale data transfer service to move extremely large amounts of data to AWS cloud.
### Overview: %% fold %% 
- Exabyte-scale data transfer service used to move extremely large amounts of data to AWS.
- Can transfer up to 100PB per Snowmobile.
- Snowmobile returns to your designated AWS region where your data will be uploaded into your selected AWS storage services, such as S3 or Glacier.
### Pricing: %% fold %% 
- Pricing is based on the amount of data stored on Snowmobile per month.
# tags:
- #gpt-summary/aws-ccp/storage 