---
service: AWS snowball
service-type: storage
---

# AWS snowball
---
- **key insights:** 
	- <span style='color:#eb3b5a'>Snowball device w/ storage & compute for AWS capabilities</span>
	- <span style='color:#fa8231'>designed for scenarios requiring local processing, edge computing, and data transfer between the local environment and AWS Cloud</span> 
		- used for scenarios where large amounts of data need to be transferred
	- <span style='color:#f7b731'>On-board</span> [[storage-s3#^939999|S3]]-<span style='color:#f7b731'>compatible storage & compute for</span> [[compute-lambda#^74b901|Lambda]] <span style='color:#f7b731'>functions & EC2 instances</span>.
		- allows flexibility and reduces reliance on AWS Cloud; can be advantageous in low-latency processing or limited network connection situations.
	- <span style='color:#20bf6b'>Storage optimized</span>: 
		- <span style='color:#20bf6b'>most storage capacity (up to 80 TB), 24 vCPUs, 32 GiB memory, transfer up to 100 TB with one device</span>.
	- <span style='color:#0fb9b1'>Compute optimized</span>: 
		- <span style='color:#0fb9b1'>most compute functionality (52 vCPUs, 208 GiB memory), 7.68 TB NVMe SSD storage, 42 TB additional storage.</span>
	- <span style='color:#8854d0'>Compute Optimized with GPU</span>: 
		- <span style='color:#8854d0'>same as compute optimized, but with installed GPU eg: </span> [[compute-EC2#Instance types fold|P3 EC2 instance]]
---
**table of contents:**
- [[#features|features]]
- [[#snowball types|snowball types]]
	- [[#snowball types#Snowball Edge Compute Optimized:  %% fold %%|Snowball Edge Compute Optimized:  %% fold %%]]
	- [[#snowball types#Snowball Edge Storage Optimized:  %% fold %%|Snowball Edge Storage Optimized:  %% fold %%]]
- [[#job types|job types]]
	- [[#job types#Import To S3  %% fold %%|Import To S3  %% fold %%]]
	- [[#job types#Export From S3 –  %% fold %%|Export From S3 –  %% fold %%]]
	- [[#job types#Local Compute and Storage Only %% fold %%|Local Compute and Storage Only %% fold %%]]
- [[#recommendations|recommendations]]
- [[#security|security]]
- [[#pricing|pricing]]
- [[#limits|limits]]
--- 
## features 
- Network adapters w/ speeds up to 100 GB/sec.
- Encryption enforced, protects data at rest & in transit.
- Import/export data between local env & S3.
- LCD display for network management & service status.
- Cluster devices for 99.999% data durability across 5-10 devices & adjust storage.
- Use file interface to read/write data via file share or NFS mount point.
- Write Python Lambda functions for S3 bucket actions on device.
- S3 & EC2 compatible endpoints for programmatic use.
- Attach multiple block storage volumes to EC2 instances.
- Deploy SSD or HDD volumes for different app needs.
- Create [[compute-EKS#^19ca59|EKS]] Anywhere cluster w/ Snowball devices for Kubernetes deployments. 
	- In Console, choose device number for cluster and include Amazon EKS Anywhere. 
## snowball types 
### Snowball Edge Compute Optimized:  %% fold %% 
- powerful computing for ML, video analysis, analytics, local computing. 
- 104 vCPUs, 416 GiB memory, optional NVIDIA Tesla V100 GPU. 
- 28 TB usable NVMe SSD storage for [[storage-s3#^939999|S3]] or [[storage-ebs#^5c188d|EBS]]. 
- Runs EC2 sbe-c and sbe-g instances (C5, M5a, G3, P3).
	- compute optimized, general use (high tier), accelerated computing [[compute-EC2#Instance types fold|EC2 instance types]]
### Snowball Edge Storage Optimized:  %% fold %% 
good for big data transfers and local computing w/ high capacity. 
80TB or 210TB NVMe for block & S3-compatible [[s3-vs-ebs-vs-efs#storage type|storage]]. 
40 vCPUs, 80 GiB or 104vCPU & 416GB RAM for EC2 dual instances [[compute-EC2#Instance types fold|(like C5).]]
## job types 
### Import To S3  %% fold %% 
- Transfer up to 80 TB of local data onto one device, then move it into S3.
- Each Snowball Edge device is associated with one job. If you need to import more data, create new jobs or clone existing ones.
### Export From S3 –  %% fold %% 
- Transfer any amount of data from S3 onto multiple Snowball Edge devices, and then move one device at a time to your on-premises destination.
- Each export job is split into parts, with each part no larger than 100 TB and associated with one Snowball Edge device.
### Local Compute and Storage Only %% fold %% 
- These jobs involve one or multiple Snowball Edge devices used in a cluster.
	- A **cluster job** is for workloads needing increased durability and storage capacity. Clusters have 5 to 10 nodes (devices).
	- A cluster provides greater durability and storage compared to a standalone Snowball Edge for local storage and compute.
## recommendations
- Files must be static when writing to the device.
- Only the `Job created` status allows for job cancellation. 
	- Once a job transitions to a different status, cancellation is not possible.
- All files transferred to a Snowball must be at least 1 MB in size.
- To perform multiple write operations simultaneously, 
	- run each command from multiple terminal windows on a computer connected to a single Snowball Edge device.
- Transfer small files in batches.
## security 
- Data transferred to a device is protected by SSL encryption.
- uses server side-encryption to protect data at rest.
- Access to Snowball Edge requires AWS credentials with appropriate permissions to access resources like an Amazon S3 bucket or an AWS Lambda function.
## pricing 
- Charges depend on the chosen Snowball Edge machine type (storage or compute optimized).
- Charges are based on the selected term of use: 
	- On demand, 1-year commitment, or 3-year commitment.
- on-demand use 
	- service fee is charged per data transfer job, including 10 days of on-site Snowball Edge device usage. 
	- Shipping days are not included in the 10-day count. Additional fees are incurred for each day beyond 10 days.
- A one-time setup fee is applied per job ordered through the console.
## limits 
- Each data transferred must have a maximum size of 5 terabytes.
- Jobs must be completed within 120 days of the Snowball Edge device being prepared.
- The default service limit for the number of AWS Snowball Edge devices you can have at one time is 1.
- If you allocate the minimum recommendation of 128 MB of memory for each of your functions, you can have up to seven Lambda functions in a single job. (Limited because of physical limits)
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-snowball-edge/)
# Tags
- #aws-ccp-exam-notes/services/storage/snowball-edge  
---


	

