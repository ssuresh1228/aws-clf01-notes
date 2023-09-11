---
service: amazon EBS - elastic block store | S3 | EFS
service-type: storage
---

# S3 vs EBS vs EFS
--- 
## storage type 
- <span style='color:#eb3b5a'>S3</span>: 
	- Object storage - can store virtually any kind of data in any format
- <span style='color:#20bf6b'>EBS</span>: 
	- Persistent block level storage for EC2 instances.
- <span style='color:#8854d0'>EFS</span>: 
	- POSIX-compliant file storage for EC2 instances.
## features
- <span style='color:#eb3b5a'>S3</span>: 
	- Accessible to anyone/service with the right permissions
- <span style='color:#20bf6b'>EBS</span>: 
	- performance for workloads that require the lowest-latency access to data from a single EC2 instance
- <span style='color:#8854d0'>EFS</span>: 
	-  file system interface 
	- file system access semantics (such as strong consistency and file locking)
	- concurrently-accessible storage for multiple EC2 instances
## max storage style 
- <span style='color:#eb3b5a'>S3</span>: Virtually unlimited
- <span style='color:#20bf6b'>EBS</span>: 16 TiB for one volume
- <span style='color:#8854d0'>EFS</span>: Unlimited system size
## max file size 
- <span style='color:#eb3b5a'>S3</span>: S3 objects can range to a max of 5 terabytes.
- <span style='color:#20bf6b'>EBS</span>: maximum size of your volumes
- <span style='color:#8854d0'>EFS</span>: 47.9 TiB for a single file
## latency performance 
- <span style='color:#eb3b5a'>S3</span>: Low, for mixed request types, integration with [[networking-aws-cloudfront#^00eb30|CloudFront]]
- <span style='color:#20bf6b'>EBS</span>: Lowest, consistent; 
	- SSD-backed storages include the highest performance Provisioned OPS SSD and General Purpose SSD that balance price and performance.
- <span style='color:#8854d0'>EFS</span>: Low, consistent; use Max I/O mode for higher performance
## throughput performance 
- <span style='color:#eb3b5a'>S3</span>: Multiple GBs per second; supports multi-part upload
- <span style='color:#20bf6b'>EBS</span>: Up to 2 GB per second. 
	- HDD-backed volumes include throughput intensive workloads and Cold HDD for less frequently accessed data.
- <span style='color:#8854d0'>EFS</span>: 10+ GB per second. 
	- [[storage-efs#^020012|Bursting Throughput]] mode scales with the scales with the size of the file system. 
	- [[storage-efs#^5475a5|Provisioned Throughput]] mode has higher dedicated throughput than bursting 
## durability 
- <span style='color:#eb3b5a'>S3</span>: Stored redundantly across multiple AZs; has 99.999999999% durability
- <span style='color:#20bf6b'>EBS</span>: Stored redundantly in a single AZ
- <span style='color:#8854d0'>EFS</span>: Stored redundantly across multiple AZs
## availability 
- <span style='color:#eb3b5a'>S3</span>: 
	- [[storage-s3#Frequently Accessed Objects fold|S3 Standard]]– 99.99% availability 
	- [[storage-s3#Infrequently Accessed Objects fold|S3 Standard-IA]] – 99.9% availability
	- [[storage-s3#Infrequently Accessed Objects fold|S3 One-Zone-IA]] – 99.5% availability.
	- [[storage-s3#S3 Intelligent Tiering fold|S3 intelligent tiering]] – 99.9%
- <span style='color:#20bf6b'>EBS</span>: 99.999% availability
- <span style='color:#8854d0'>EFS</span>: 99.9% SLA; Runs in multiple AZs
## scalability 
- <span style='color:#eb3b5a'>S3</span>: Highly scalable
- <span style='color:#20bf6b'>EBS</span>: Manually increase/decrease memory size. 
	- Attach/detach additional volumes to/from your EC2 instance to scale.
- <span style='color:#8854d0'>EFS</span>: file systems are elastic 
	- automatically grow and shrink as you add and remove files.
## data accessing 
- <span style='color:#eb3b5a'>S3</span>: One to millions of connections over the web; REST web services interface
- <span style='color:#20bf6b'>EBS</span>: [[storage-ebs#Provisioned IOPS SSD (io1/io2) fold|provisioned IOPS SSDs]] support >= 16 [[compute-EC2#AWS Nitro System fold|EC2 Nitro]] instances in same AZ
- <span style='color:#8854d0'>EFS</span>: One to thousands of EC2 instances or on-premises servers from multiple AZs, regions, VPCs, and accounts concurrently
## access control 
- <span style='color:#eb3b5a'>S3</span>: bucket policies and IAM [[security-identity-compliance-aws-iam#users|user]] [[security-identity-compliance-aws-iam#policies|policies]]
- <span style='color:#20bf6b'>EBS</span>: Policies, [[security-identity-compliance-aws-iam#role fold|roles]], and Security Groups
- <span style='color:#8854d0'>EFS</span>: Only VPC-accessible resources with mount target access can access the file system with POSIX-compliant permissions.
## encryption methods 
- <span style='color:#eb3b5a'>S3</span>: SSL endpoints, Client/Server-Side Encryption
- <span style='color:#20bf6b'>EBS</span>: data-at-rest and data-in-transit through encryption that uses [[security-aws-kms#CMKs - customer managed keys|AWS KMS CMKs]] 
- <span style='color:#8854d0'>EFS</span>:
## backup/restoration 
- <span style='color:#eb3b5a'>S3</span>: versioning or cross-region replication
- <span style='color:#20bf6b'>EBS</span>: durable snapshot capabilities
- <span style='color:#8854d0'>EFS</span>: EFS to EFS replication
## pricing 
- <span style='color:#eb3b5a'>S3</span>: based on the location of your bucket; cheaper as more storage used
- <span style='color:#20bf6b'>EBS</span>: pay Gb/month of provisioned storage/IOPS storage + snapshot data in S3
- <span style='color:#8854d0'>EFS</span>:
## use case 
- <span style='color:#eb3b5a'>S3</span>: 
- Web serving/ content management/media
- backups, big data analytics, data lake
- <span style='color:#20bf6b'>EBS</span>: 
- Boot volumes, transactional/NoSQL databases, data warehousing & ETL
- <span style='color:#8854d0'>EFS</span>:
	- Web serving and content management,
	- enterprise applications, 
	- media and entertainment, 
	- home directories, 
	- database backups,
	- developer tools,
	- container storage,
	- big data analytics
## service endpoint
- <span style='color:#eb3b5a'>S3</span>:
- <span style='color:#20bf6b'>EBS</span>: w/in VPC
- <span style='color:#8854d0'>EFS</span>: w/in VPC
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-s3-vs-ebs-vs-efs/)
# Tags
- #aws-ccp-exam-notes/services/storage/s3-vs-ebs-vs-efs  
---


	

