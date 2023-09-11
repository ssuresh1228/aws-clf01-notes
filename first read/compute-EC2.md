---
service: EC2
service-type: compute
---

# EC2: Elastic Cloud Compute
---
- Description:  ^e5d497
	- linux/mac/windows based VM you can provision
	- can use on-demand instances up to a limit based on number of virtual CPUs (vCPUs) allowed
	- can buy and use up to 20 reserved instances
	- can request and use spot instances up to a limit defined by your dynamic spot limit in each region
---
- **Instances: server environments** ^92978b
- **Amazon Machine Images (AMIs): packaged OS and additional installations in a reusable template**
## AWS Nitro System %% fold %%
- powers next-gen EC2 instances
- hypervisors protect hardware and virtualize CPU, storage, networking while providing management capabilities
	- Nitro System shifts these functions to dedicated hardware/software, cutting instance costs
## Instance types %% fold %%
- **general use:**
	- t-type
	- m-type
- **compute optimized:**
	- c-type
- **memory optimized:**
	- r-type
	- x-type
	- z-type
- **storage optimized:**
	- d-type
	- h-type
	- i-type
- **accelerated computing:**
	- f-type
	- g-type
	- p-type
## EC2 Features %% fold %% 
- secure login info for instances using key-pairs
- instance storage volumes hold temporary data
	- deleted on instance STOP/DELETE
	- persistent storage using <mark style="background: #FF000094;">EBS (elastic block store)</mark> volumes
- <mark style="background: #FF000094;">EBS-backed instances can be stopped</mark> 
	- instance storage-backed can only start or terminate
- regions/AZs offer diverse deployment for instances and EBS volumes
-  firewall for specifying protocols, ports, and IP ranges in security groups
- elastic IP addresses for static IPv4 in dynamic cloud computing
- tags for metadata assignment to EC2 resources
- <mark style="background: #0055FF;">Virtual Private Clouds (VPCs)</mark> can be used for isolated virtual networks
- host recovery restarts instances after hardware failure
- <mark style="background: #FF000094;">EC2 hibernation (on certain instance types) preserves instance state + memory onto EBS</mark>
	- useful for quick resumption without reinitialization
	- <mark style="background: #FF000094;">requires encrypted EBS-backed instances</mark> 
## EC2 States %% fold %% 
- **Start**
	- run instance and incur continuous billing
- **Stop**
	- normal shutdown, restart anytime
	- EBS volumes stay, instance store data deleted
	- no charges while stopped
	- <mark style="background: #6800FFBF;">can attach/detach EBS volumes, create an AMI from this instance, and change instance hardware</mark>
- **Hibernate:**
	- <mark style="background: #FF000094;">in-memory state saved to encrypted EBS</mark>
	- instance shuts down
	- pay for EBS and IPs; no hourly charges
- enable termination protection and stop prevention to prevent accidental termination/stop
---
## Root device volumes %% fold %%
- root device volume stores instance boot image
- <mark style="background: #930083;">replace root volume of running EC2 with initial state, snapshot, or AMI</mark>
- **instance-storage (temporary storage) backed instances:**
	- data deleted on termination/failure
	- regularly back up data
- **<mark style="background: #FF000094;">Amazon EBS-backed instances:</mark>**
	- stop/restart without data loss
	- modify hardware, attach volume to another instance
	- <mark style="background: #FF5700AB;">default: root device volume for an AMI backed by EBS is deleted when instance terminates</mark>
	- encrypted EBS-backed instances from unencrypted AMIs required an encrypted AMI copy
		- now can launch encrypted instances directly from unencrypted AMIs
## EC2 AMIs  %% fold %% 
- <mark style="background: #0055FF;">AMI: template for instance root volume, launch permissions, and block device mapping</mark>
- when backed by [[storage-ebs#^5c188d|EBS]]: root device is EBS volume; can use [[storage-ebs#encryption|EBS encryption]]
- when backed by instance storage (temporary): root device is an instance store volume from [[storage-s3#^939999|S3]] template
- AMIs can be copied to/from different regions
- recycle bin can restore deleted AMIs and set locks to protect against mods/deletion
- have timestamps to check last launched instance
- public AMIs deprecate in 2 years by default
## EC2 image builder %% fold %%
- **automates AMI creation, management, and deployment**
- can use management console, CLI, or API to create custom images
- you own customized images
- can configure pipelines for updates and patching
- command exists to create and AMI with defined config resources
## EC2 Pricing %% fold %%
### Pricing options: %% fold %%
- **on-demand:** pay by the second with no commitments ^59341b
- **dedicated hosts:** pay for a dedicated physical host
- **dedicated instances:** pay hourly for single-tenant hardware
#### on-demand capacity reservations: %% fold %% 
- reserve capacity in specific AZ without long term commitment
- applied with Savings Plans and Reserved Instances for discounts
- <mark style="background: #00FF266B;">Monitored with CloudWatch</mark>
#### reserved:  %% fold %% 
- one-time upfront payment for instance, discounted hourly rate
- **standard class:** highest discount, limited attribute modification, sellable
- **convertible class:** lower discount, high attribute modification, *not* sellable
#### spot: %% fold %%
- request unused instances for up to 90% discount
- can be started/stopped at will when backed by EBS
- **spot blocks:** continuous, ideal for finite tasks
- **spot fleet:** spot + on-demand hybrid; used to maintain target capacity
- **spot capacity:** set of unused instances with same attributes
#### additional charges:  %% fold %%
- data transfer from 
	- copying AMIs between regions
	- instances between regions
- EBS pricing is independent of instance pricing
## Security: %% fold %%
- <mark style="background: #0055FF;">use IAM for access control: policies and roles</mark>
- restrict access to trusted hosts/networks on instance ports
- security groups act as firewalls; control traffic for instances
	- different security groups for different needs
	- rules are stateful and permissive
	- default: allows all inbound/outbound traffic
- avoid password-based login for AMI launched instances
- create key-pairs with specified key formats (.pem or .ppk)
# References
- [cheat sheet](https://tutorialsdojo.com/amazon-elastic-compute-cloud-amazon-ec2/)
- [[compute-overview]]
- 
# Tags
- #aws-ccp-exam-notes/services/compute/EC2  
---