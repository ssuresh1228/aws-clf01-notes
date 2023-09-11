---
service: amazon EBS - elastic block store
service-type: storage
service-description: block level storage volumes for EC2 instances
---

# Amazon EBS - elastic block store
---
- **key insights:**  ^5c188d
	- used for [[compute-EC2#^e5d497|EC2 instances]] for storage
	- work well for file systems, databases, and apps needing precise updates/raw block level storage
	- good for random/continuous data access 
	- new EBS volumes immediately offer max performance 
	- termination protection is off by default; enable to keep data once instance stops 
	- >=5000 EBS volumes and >=10,000 snapshots by default
---
**table of contents:**
- [[#features|features]]
- [[#EBS volume types|EBS volume types]]
	- [[#EBS volume types#General Purpose SSD (gp3): %% fold %%|General Purpose SSD (gp3): %% fold %%]]
	- [[#EBS volume types#General Purpose SSD (gp2):  %% fold %%|General Purpose SSD (gp2):  %% fold %%]]
	- [[#EBS volume types#Provisioned IOPS SSD (io1/io2):  %% fold %%|Provisioned IOPS SSD (io1/io2):  %% fold %%]]
	- [[#EBS volume types#Throughput Optimized HDD (st1):  %% fold %%|Throughput Optimized HDD (st1):  %% fold %%]]
	- [[#EBS volume types#Cold HDD (sc1):  %% fold %%|Cold HDD (sc1):  %% fold %%]]
- [[#encryption|encryption]]
- [[#monitoring|monitoring]]
- [[#snapshots|snapshots]]
- [[#optimized instances|optimized instances]]
- [[#pricing|pricing]]
--- 
## features
- General purpose SSD, provisioned IOPS SSD, throughput optimized HDD, and cold HDD are the storage types available in Amazon EBS.
- Multiple volumes can be used by one instance
- provisioned IOPS can be shared by multiple instances.
- Enabling multi-attach allows shared volumes to be used on multiple [[compute-EC2#AWS Nitro System fold|nitro-based EC2 instances]] in the same availability zone.
- Encrypted EBS volumes meet data-at-rest encryption requirements.
- Snapshots can be created and copied across regions, allowing for expansion, migration, and disaster recovery.
- Volumes are specific to availability zones but can be moved between regions using [[storage-ebs#snapshots|snapshots]].
- Volume performance can be monitored using [[monitoring-cloudwatch#^7382c4|CloudWatch]].
- Volumes can be detached explicitly or during instance termination
- root device of an instance must be stopped before detaching the volume.
- [[storage-aws-backup#^87e6b4|AWS backup]] can be used to configure, schedule, retain, and monitor backups.
- EBS fast snapshot restore eliminates latency for accessing volumes from initialized snapshots. 
## EBS volume types
### General Purpose SSD (gp3): %% fold %% 
- 3,000 IOPS, 125 MiB/s baseline, 
- expandable to 16,000 IOPS and 1,000 MiB/s, with specific IOPS and throughput limits.
### General Purpose SSD (gp2):  %% fold %% 
- Base 3 IOPS/GiB, 
- bursts to 3,000 IOPS, 
- supports up to 16,000 IOPS and 250 MB/s throughput, 
- burst duration based on volume size and credit balance.
### Provisioned IOPS SSD (io1/io2):  %% fold %% 
- For I/O-intensive workloads, 
- io2 offers higher durability, 
- supports 500 IOPS per provisioned GB.
### Throughput Optimized HDD (st1):  %% fold %% 
- Low-cost, high throughput storage with up to 500 MiB/s.
### Cold HDD (sc1):  %% fold %% 
- Low-cost, moderate throughput storage with up to 250 MiB/s.
## encryption 
- Encrypted EBS covers data at rest, disk I/O, and snapshots.
- Encryption occurs on EC2 instance host servers.
- Encrypts data in transit between volume and instance.
- Utilizes [[security-aws-kms#^bed19a|AWS KMS (key management system)]] master keys.
- Encrypted snapshots result in encrypted volumes.
- Not available on all instance types.
- No direct way to encrypt existing unencrypted volumes.
- Can enable EBS Encryption by Default for new volumes.
## monitoring
- [[monitoring-cloudwatch#^7382c4|CloudWatch]] offers basic and detailed monitoring
- volume status checks:
	- OK - normal
	- warning - degraded
	- impaired -  stalled 
	- insufficient database
- volume event have start, duration, and end times 
- volume event types:
	- awaiting action: enable action
	- IO enabled 
	- IO auto-enabled 
	- normal 
	- degraded 
	- severely degraded 
	- stalled 
## snapshots
- EBS data can be backed up to [[storage-s3#^939999|S3]] through snapshots 
- snapshots are incremental; only save changed blocks 
- deleting a snapshot removes its unique data 
- can be shared across accounts by modifying access permissions 
- can make copies of snapshots 
- constrained to region of creation
	- to share with another region, share a copy
- root device snapshots in use by an [[compute-EC2#EC2 AMIs fold|AMI]] cannot be deleted w/o AMI deregistration
- up to 5 concurrent snapshot copy requests per account per destination region 
- user-defined tags are not copied from source to new snapshot copy 
- must be encrypted with a custom [[security-aws-kms#CMKs - customer managed keys|CMK]] for sharing 
## optimized instances 
- EBS-Optimized Instances minimize contention b/w I/O and instance traffic for performance.
- offer dedicated bandwidth from 500 Mbps to 60,000 Mbps.
- some instance types are EBS-optimized by default; no need to enable/disable it.
## pricing 
- Billed based on provisioned storage amount in GB per month
- Certain volumes billed in per-second increments with a 60-second minimum
- io1 volumes charged based on provisioned storage and IOPS
- Storage charges continue after detaching a volume if it exceeds Free Tier limit
- Snapshot storage cost depends on data consumption in Amazon S3
- Copying snapshots to new regions incurs additional storage costs
- EBS optimization on non-default instances has an extra hourly fee
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-ebs/#types-of-ebs-volumes)
# Tags
- #aws-ccp-exam-notes/services/storage/ebs  
---


	

