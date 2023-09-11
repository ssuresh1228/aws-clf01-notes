---
service: amazon EFS - elastic file system
service-type: storage, serverless
service-description: file storage
---

# Amazon EFS: Elastic File Service
---
- **key insights:**  ^233be8
	- fully managed file storage service 
	- scalable, serverless file storage 
	- accessible to [[compute-EC2#^e5d497|EC2]], [[compute-ECS#^daa71f|ECS]], [[compute-EKS#^19ca59|EKS]], [[compute-fargate#^c08b80|fargate]], and [[compute-lambda#^74b901|lambda]] through file system interface 
	- scales from gigabytes to petabytes automatically 
	- highly durable and available 
---
**table of contents:**
- [[#features|features]]
	- [[#features#performance modes:  %% fold %%|performance modes:  %% fold %%]]
	- [[#features#throughput modes:  %% fold %%|throughput modes:  %% fold %%]]
- [[#mount targets (accessing EFS file system in VPC)|mount targets (accessing EFS file system in VPC)]]
- [[#EFS access points|EFS access points]]
- [[#components|components]]
- [[#data consistency|data consistency]]
- [[#managing file systems|managing file systems]]
- [[#mounting file systems|mounting file systems]]
- [[#lifecycle management|lifecycle management]]
- [[#monitoring file systems|monitoring file systems]]
- [[#security|security]]
- [[#pricing|pricing]]
--- 
## features 
- Fully managed file storage service
- Scalable, serverless file storage
- Scales automatically from gigabytes to petabytes
- Highly durable and available
- Supports Network File System version 4 protocol
- Can be mounted on EC2 instances, [[compute-ECS#task definitions fold|ECS tasks]], [[compute-EKS#Pod networking fold|EKS pods]], and [[compute-lambda#functionality and integration fold|lambda]] functions
- Multiple EC2 instances can access an EFS file system simultaneously
- Data and metadata are stored across multiple [[AWS-Regions-and-Availability-Zones.jpg|AZs]]
- Provides file system access semantics, strong data consistency, and file locking
- Allows control of access through POSIX permissions
- Simplified data transfer with AWS DataSync
- Automatic incremental backups with EFS-to-EFS Backup solution
- Cost-optimized storage class for files accessed less frequently (EFS IA)
- EFS IA-One Zone storage class for lower costs and durability
### performance modes:  %% fold %% 
- <span style='color:#eb3b5a'>general purpose:</span> default, ideal for latency sensitive tasks
- <span style='color:#8854d0'>max I/O mode:</span> scales to high throughput/ operations per sec at tradeoff of higher latency
### throughput modes:  %% fold %% 
- <span style='color:#eb3b5a'>bursting throughput mode (default)</span>: throughput scales as file system grows  ^020012
- <span style='color:#8854d0'>provisioned throughput mode</span>: specify throughput of your file system independent of amount of data stored 
## mount targets (accessing EFS file system in VPC)
- Mount targets are used to access EFS file system in VPC
- Create one mount target in each AZ in a [[AWS-Regions-and-Availability-Zones.jpg|region]]
- Provide IP address for NFSv4 endpoint
- Access file system using DNS name of EFS mount target
- DNS format: `File-system-id.efs.aws-region.amazonaws.com`
- Linux-based OS required for on-premises servers
## EFS access points 
- simplify how apps are provided access to shared data sets in an EFS file system. 
- works with [[security-identity-compliance-aws-iam#^ab9f15|IAM]] to enforce: 
	- operating system user and group
	- directory for every file system request made through the access point
## components
- ID
- creation token
- creation time
- file system size in bytes
- number of mount targets created for the file system
- file system state
- mount targets
## data consistency 
- EFS provides open-after-close consistency semantics.
- Write operations are durably stored across Availability Zones.
- Synchronous data access and non-appending writes have read-after-write consistency.
## managing file systems 
- Encrypted file systems supported (in transit and at rest)
- Managing network accessibility (create/delete mount targets, update its configuration)
- Create/update/delete tags associated with file system
- Metered data size for different file system objects:
	- <span style='color:#8854d0'>Regular files:</span> logical size rounded to next 4-KiB increment (less for sparse files)
	- <span style='color:#eb3b5a'>Directories:</span> actual storage used for entries and data structure, rounded to next 4 KiB increment
	- <span style='color:#3867d6'>Symbolic links and special files</span>: always 4 KiB
- File system deletion is irreversible, unmount before deleting
- Use AWS DataSync for: 
	- efficient/secure file copying between EFS resources
	- one-time migrations 
	- periodic ingest for distributed workloads 
	- automate replication for data protection/recovery 
- Automatic daily backups with [[storage-aws-backup#^87e6b4|AWS Backup]] (35-day retention)
- Monitor storage usage with [[monitoring-cloudwatch#^7382c4|CloudWatch]] Metrics
## mounting file systems
- Mount on EC2 instance using mount helper in `amazon-efs-utils package`
- Mount on on-premises servers in [Amazon VPC](https://tutorialsdojo.com/amazon-vpc/) with [AWS Direct Connect](https://tutorialsdojo.com/aws-direct-connect/) or VPN
- Use fstab to automatically mount file system on EC2 instance on reboots
## lifecycle management 
- Choose from 5 EFS Lifecycle Management policies (7, 14, 30, 60, or 90 days)
- Automatically move files to EFS IA storage class
- Save up to 85% in cost
## monitoring file systems
- [[monitoring-cloudwatch#alarms|CloudWatch alarms]]
- [[monitoring-cloudwatch#logs|CloudWatch logs]]
- [[monitoring-cloudwatch#events|CloudWatch events]]
- [[monitoring-CloudTrail#^718023|CloudTrail logs]]
- log files on your file system 
## security 
- Valid credentials required for EFS API requests
- Permissions needed to create/access resources
- when file system is created, there's only 1 root directory at `/` 
	- Only root user has default permissions (read/write/execute) initially
- Specify EC2 security groups for instances and EFS mount targets
- Use [[security-identity-compliance-aws-iam#iam role fold|IAM roles]] for NFS (network file system) access and [[security-identity-compliance-aws-iam#policies|policies]] client-specific permissions
## pricing 
- pay only for storage used by your file system(s)
- [[storage-efs#throughput modes fold|provisioned throughput]] costs are determined by your specified throughput values ^5475a5
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-efs/)
# Tags
- #aws-ccp-exam-notes/services/storage/efs  
---


	

