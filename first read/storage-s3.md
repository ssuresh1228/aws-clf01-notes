---
storage: "amazon s3: scalable object storage"
sticker: emoji//1faa3
---
# amazon S3
---
- **key insights:**  ^939999
	- <span style='color:#eb3b5a'>stores data as objects in buckets</span> 
	- <span style='color:#fa8231'>object: file + optional metadata describing the file</span> 
	- <span style='color:#20bf6b'>key: unique identifier for an object in a bucket</span> 
	- <span style='color:#0fb9b1'>virtually unlimited storage capacity </span>
---
**table of contents:**
- [[#buckets|buckets]]
- [[#data consistency model|data consistency model]]
- [[#storage classes|storage classes]]
	- [[#storage classes#Frequently Accessed Objects: %% fold %%|Frequently Accessed Objects: %% fold %%]]
	- [[#storage classes#Infrequently Accessed Objects: %% fold %%|Infrequently Accessed Objects: %% fold %%]]
	- [[#storage classes#S3 Intelligent Tiering: %% fold %%|S3 Intelligent Tiering: %% fold %%]]
	- [[#storage classes#S3 GLACIER: %% fold %%|S3 GLACIER: %% fold %%]]
		- [[#S3 GLACIER: %% fold %%#retrieval options: %% fold %%|retrieval options: %% fold %%]]
		- [[#S3 GLACIER: %% fold %%#storage types: %% fold %%|storage types: %% fold %%]]
			- [[#storage types: %% fold %%#Amazon S3 Glacier Instant Retrieval %% fold %%|Amazon S3 Glacier Instant Retrieval %% fold %%]]
			- [[#storage types: %% fold %%#Amazon S3 Glacier Flexible Retrieval %% fold %%|Amazon S3 Glacier Flexible Retrieval %% fold %%]]
			- [[#storage types: %% fold %%#Amazon S3 Glacier Deep Archive %% fold %%|Amazon S3 Glacier Deep Archive %% fold %%]]
			- [[#storage types: %% fold %%#Amazon S3 on Outposts %% fold %%|Amazon S3 on Outposts %% fold %%]]
- [[#bucket configs|bucket configs]]
- [[#objects  %% fold %%|objects  %% fold %%]]
	- [[#objects  %% fold %%#2 types of metadata|2 types of metadata]]
	- [[#objects  %% fold %%#Tagging|Tagging]]
	- [[#objects  %% fold %%#Object Delete|Object Delete]]
	- [[#objects  %% fold %%#Object Lock|Object Lock]]
	- [[#objects  %% fold %%#Object Ownership|Object Ownership]]
	- [[#objects  %% fold %%#S3 Select|S3 Select]]
- [[#security|security]]
	- [[#security#Resource Based Policies %% fold %%|Resource Based Policies %% fold %%]]
		- [[#Resource Based Policies %% fold %%#Bucket Policies %% fold %%|Bucket Policies %% fold %%]]
		- [[#Resource Based Policies %% fold %%#Access Control Lists %% fold %%|Access Control Lists %% fold %%]]
		- [[#Resource Based Policies %% fold %%#User Policies %% fold %%|User Policies %% fold %%]]
		- [[#Resource Based Policies %% fold %%#backup  %% fold %%|backup  %% fold %%]]
- [[#monitoring|monitoring]]
- [[#pricing|pricing]]
--- 
## buckets 
- Control access to buckets (create, delete, list objects)
- View access logs for buckets and objects
- Choose storage region for buckets
- Bucket name must be unique and DNS-compliant
- Can create up to 100 buckets per AWS account
- Can't change bucket region after creation
- Can host static websites in buckets
- Can't delete buckets with 100,000+ objects or with versioning enabled
## data consistency model 
- Add new objects to storage service, read them anywhere instantly.
- Get up-to-date and correct information about added things.
- Changes or deletions immediately reflected worldwide.
- Always receive up-to-date and correct information when requesting.
- Deleting a bucket may take time for complete removal.
- Enabling versioning on a bucket may take time to work worldwide.
## storage classes  
- Objects in [[storage-s3#Frequently Accessed Objects fold|S3 standard]], [[storage-s3#Infrequently Accessed Objects fold|S3 standard-IA]], and [[storage-s3#S3 GLACIER fold|Glacier]] storage classes are stored across multiple devices in at least three Availability Zones.
### Frequently Accessed Objects: %% fold %% 
- Use <span style='color:#8854d0'>S3 STANDARD</span> for general-purpose storage of data that you access often. ^fcd873
### Infrequently Accessed Objects: %% fold %% 
- Use <span style='color:#eb3b5a'>S3 STANDARD_IA</span> for infrequently accessed, long-term data storage. Data is stored in multiple AZs to make sure it's safe. ^66c16f
- Use <span style='color:#fa8231'>S3 ONEZONE_IA</span> save money,but data is less secure b/c it's not as resilient to the physical loss of an AZ ^c1037e
- These storage classes are good for big files that you want to keep for at least 30 days. 
- If you delete a file before 30 days, you still have to pay for 30 days.
### S3 Intelligent Tiering: %% fold %% 
- For cost-saving when data access patterns change.
- Data is moved between frequent and infrequent tiers based on access frequency.
- If data isn't accessed for 30 days, it goes to infrequent tier. 
	- If accessed again, back to frequent tier.
- Archive tier for data not accessed for 90 days, moves to [[storage-s3#Amazon S3 Glacier Deep Archive fold|deep archive]] after 180 days.
- No extra fees to retrieve data from this class.
### S3 GLACIER: %% fold %% 
- for long-term archiving of data.
- can't directly choose GLACIER as the storage class when storing objects.
- Archived objects can only be accessed through S3 after restoring them.
- Your data is stored in multiple places across at least three Availability Zones for reliability.
- S3 Glacier instant/flexible/deep archive options 
#### retrieval options: %% fold %% 
1. <span style='color:#eb3b5a'>Expedited Retrieva</span>l: Quick access within minutes for urgent data retrieval.   
2. <span style='color:#f7b731'>Standard Retrieval</span>: Access within hours for non-urgent needs.
3. <span style='color:#20bf6b'>Bulk Retrieval</span>: Cost-effective but longer retrieval time, typically 5-12 hours for large amounts of data.
#### storage types: %% fold %% 
##### Amazon S3 Glacier Instant Retrieval %% fold %% 
- Storage class for rarely accessed long-lived data, retrieved in milliseconds.
- Cost-saving compared to [[storage-s3#Infrequently Accessed Objects fold|S3 Standard-IA]] for data accessed quarterly.
- Data is resilient to destruction of one Availability Zone.
##### Amazon S3 Glacier Flexible Retrieval %% fold %% 
- A storage class for storing archive data that is accessed once or twice per year.
- Cost-effective retrieval options, ranging from minutes to hours, with free bulk retrievals.
#####  Amazon S3 Glacier Deep Archive %% fold %% 
- Storage class for rarely accessed data.
- Lowest cost, high durability, and 12-hour restoration.
- Objects stored across three Availability Zones for 99.999999999% durability and 12-hour restoration.
- Bulk retrieval option for petabytes of data within 48 hours.
#####  Amazon S3 on Outposts %% fold %% 
- Amazon S3 on Outposts: S3 APIs for on-premises storage.
- Encrypted data with SSE-C and SSE-S3, stored on Outposts servers.
- Automate data transfer with AWS DataSync.
- Access any object in an Outposts bucket with access points.
- Supports S3 lifecycle rules.
## bucket configs 
- <span style='color:#eb3b5a'>location</span> 
	- Specify the AWS Region for bucket creation.
- <span style='color:#0fb9b1'>policy and ACL</span> (access control list)
	- All your resources are private by default. 
	- Use bucket policy and ACL options for permission management.
- <span style='color:#fa8231'>cors (cross origin resource sharing)</span>
	- configure  bucket to allow cross-origin requests. 
	- defines a way for client web applications that are loaded in one domain to interact with resources in a different domain.
- <span style='color:#f7b731'>website</span>
	- configure  bucket for static website hosting.
- <span style='color:#20bf6b'>logging</span>
	- enables you to track requests for access to your bucket. 
	- Each access log record provides details about a single access request: 
		- requester, bucket name, request time, request action, response status, and error code, if any.
- <span style='color:#0fb9b1'>event notification</span>
	-  enable your bucket to send you notifications of specified bucket events.
- <span style='color:#2d98da'>versioning</span>
	- AWS recommends VERSIONING AS A BEST PRACTICE to recover objects from being deleted or overwritten by mistake.
- <span style='color:#3867d6'>lifecycle</span>
	- define lifecycle rules for objects in your bucket that have a well-defined lifecycle.
- <span style='color:#8854d0'>cross-region replication</span>
	- automatic, asynchronous copying of objects across buckets in different AWS Regions.
- <span style='color:#eb3b5a'>tagging</span>
	- S3 provides the `tagging` subresource to store and manage tags on a bucket. 
	- AWS generates a cost allocation report with usage and costs aggregated by your tags.
- <span style='color:#20bf6b'>transfer acceleration</span> 
	- enables fast, easy, and secure transfers of files over long distances between your client and an S3 bucket.  
	- takes advantage of [[networking-aws-cloudfront#^00eb30|CloudFront]] globally distributed **edge locations**.
## objects  %% fold %% 
- private by default 
- each object has <span style='color:#2d98da'>data</span>, <span style='color:#20bf6b'>key</span>, and <span style='color:#eb3b5a'>metadata</span>
	- <span style='color:#eb3b5a'>metadata</span> cannot be modified after object is uploaded 
### 2 types of metadata 
- <span style='color:#0fb9b1'>system metadata</span>
	- <span style='color:#eb3b5a'>date</span>: 
		- not user modifiable
	- <span style='color:#eb3b5a'>content length</span>: 
		- object size in bytes | not user modifiable
	- <span style='color:#eb3b5a'>last-modified</span>: 
		- not user modifiable
	- <span style='color:#eb3b5a'>content-MD5</span>: 
		- \base64-encoded 128-bit MD5 digest of the object 
		- not user modifiable
	- <span style='color:#eb3b5a'>x-amz-server-side-encryption</span>: 
		- Indicates if server-side encryption is enabled for the object:
		- tells if from [[security-aws-kms#^bed19a|AWS KMS]] (SSE-KMS) or AWS managed encryption (SSE-S3).
		- user modifiable
	- <span style='color:#eb3b5a'>x-amz-version-id</span>
		- object version 
		- version number to objects assigned to objects in bucket
		- not user modifiable
	- <span style='color:#eb3b5a'>x-amz-delete-marker</span>
		- boolean delete marker in a versioning enabled bucket 
		- not user modifiable
	- <span style='color:#eb3b5a'> x-amz-storage-class</span>
		- S3 storage class used 
		- user modifiable
	- <span style='color:#eb3b5a'>x-amz-website-redirect-location</span>
		- redirects requests for an object to another object in the same bucket/URL
		- user modifiable
	- <span style='color:#eb3b5a'>x-amz-server-side-encryption-aws-kms-key-id</span>
		- ID of [[security-aws-kms#^bed19a|KMS]] master encryption key if `x-amz-server-side-encryption` is enabled
		- user modifiable
	- <span style='color:#eb3b5a'>x-amz-server-side-encryption-customer-algorithm</span>
		- Indicates if server-side encryption with customer-provided encryption keys (SSE-C) is enabled.
		-  user modifiable
- <span style='color:#8854d0'>user-defined metadata (key-value pair you provide)</span>

### Tagging
- You can associate up to 10 tags with an object. Tags must have unique keys and can be up to 128 Unicode characters in length for key and 256 Unicode characters in length for values. Key and values are case sensitive.
### Object Delete
- Deleting Objects from a Version-Enabled Bucket
    - Specify a non-versioned delete request with only the object's key.
    - Specify a versioned delete request with both the key and version ID.
- Deleting Objects from an MFA-Enabled Bucket
    - Providing an invalid MFA token results in a failed request.
    - Not providing an MFA token (when not deleting a versioned object) allows the delete to succeed.
### Object Lock
- Object Lock prevents objects from being deleted or overwritten for a fixed time or indefinitely. 
- Options include retention period or legal hold, which locks the object until explicitly removed.  
- only works in versioned buckets and applies to individual object versions.
### Object Ownership
- ACL allows automatic ownership of objects uploaded to your buckets.
### S3 Select
-  pulls out needed data from objects, improving performance and reducing cost. 
-  works on objects in CSV, JSON, Apache Parquet formats, and supports JSON Arrays and BZIP2 compression. 
- [[monitoring-cloudwatch#^7382c4|CloudWatch]] Metrics for S3 Select provide 1-minute interval monitoring to identify and address operational issues.
## security  
- Policies contain the following:
    - **Resources** – buckets and objects
    - **Actions** – set of operations
    - **Effect** – can be either allow or deny. Need to explicitly grant allow to a resource.
    - **Principal** – account, service or user granted access to actions/ resources in the statement.
### Resource Based Policies %% fold %% 
#### Bucket Policies %% fold %% 
- Provides **centralized access control** to buckets and objects based on a variety of conditions, including S3 operations, requesters, resources, and aspects of the request (e.g., IP address).
- Can either **add or deny permissions** across all (or a subset) of objects within a bucket.
- IAM users need additional permissions from root account to perform bucket operations.
- Bucket policies are limited to 20 KB in size.
#### Access Control Lists %% fold %% 
- A list of grants identifying grantee and permission granted.
- ACLs use an S3–specific XML schema.
- You can grant permissions only to other AWS accounts, not to users in your account.
- You cannot grant conditional permissions, nor explicitly deny permissions.
- Object ACLs are limited to 100 granted permissions per ACL.
- The only recommended use case for the bucket ACL is to grant **write** permissions to the **S3 Log Delivery group**.
#### User Policies %% fold %% 
- [[security-identity-compliance-aws-iam#^ab9f15|AWS IAM]] 
	- IAM User Access Keys
	- Temporary Security Credentials
#### backup  %% fold %% 
- can use [[storage-aws-backup#^6d75b2|AWS Backup policies]] to protect your Amazon S3 data.
	- Continuous backups and Periodic backups
	- Automated backup scheduling and retention
	- Restore backups
## monitoring 
- [[monitoring-cloudwatch#^7382c4|CloudWatch]] - 
	-  <span style='color:#eb3b5a'>Daily Storage Metrics for Buckets ‐</span> 
		-  collects and processes storage data from S3 into readable, daily metrics.
	- <span style='color:#0fb9b1'>Request metrics ‐ </span>
		- monitor S3 requests to quickly identify and act on operational issues. 
		- metrics are available at 1 minute intervals after some latency to process.
	- [[monitoring-cloudwatch#alarms|CloudWatch alarms]] – 
		- Monitor a metric over a specified time period and take actions based on its value compared to a threshold over multiple time periods
- [[monitoring-CloudTrail#^718023]|CloudTrail]] log monitoring – 
	- Share log files between accounts 
	- monitor in real time by sending them to CloudWatch Logs, 
	- write log processing applications in Java,  
		- validate file integrity after delivery by CloudTrail.
- max of 1000 metrics config per bucket 
- Supported event activities in S3 are recorded in a [[monitoring-CloudTrail#^718023|CloudTrail]] event with other AWS service events in **Event history**.
## pricing 
- only charged for resources used 
- no charge for creating a bucket: 
	- charged for storing/transferring objects  
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-s3/) 
# Tags
- #aws-ccp-exam-notes/services/storage/s3  
---