---
service: KMS - key management system
service-type: security
---

# AWS KMS: Key Management System

^6fbc74

---
- **key insights:**  ^bed19a
	- managed service for data encryption
	- provides key storage, management, and auditing
	- encrypt data in your apps and across AWS services
---
**table of contents:**
- [[#features|features]]
- [[#concepts|concepts]]
	- [[#concepts#CMKs - customer managed keys|CMKs - customer managed keys]]
		- [[#CMKs - customer managed keys#customer managed CMKs %% fold %%|customer managed CMKs %% fold %%]]
		- [[#CMKs - customer managed keys#AWS managed CMKs %% fold %%|AWS managed CMKs %% fold %%]]
		- [[#CMKs - customer managed keys#AWS owned CMKs: %% fold %%|AWS owned CMKs: %% fold %%]]
		- [[#CMKs - customer managed keys#data keys: %% fold %%|data keys: %% fold %%]]
		- [[#CMKs - customer managed keys#envelope encryption: %% fold %%|envelope encryption: %% fold %%]]
		- [[#CMKs - customer managed keys#encryption context: %% fold %%|encryption context: %% fold %%]]
		- [[#CMKs - customer managed keys#key policies: %% fold %%|key policies: %% fold %%]]
		- [[#CMKs - customer managed keys#grants: %% fold %%|grants: %% fold %%]]
		- [[#CMKs - customer managed keys#grant tokens:  %% fold %%|grant tokens:  %% fold %%]]
		- [[#CMKs - customer managed keys#automatic key rotation: %% fold %%|automatic key rotation: %% fold %%]]
		- [[#CMKs - customer managed keys#aliases: %% fold %%|aliases: %% fold %%]]
- [[#importing keys:|importing keys:]]
- [[#deleting keys:|deleting keys:]]
- [[#Pricing:|Pricing:]]
--- 
## features
- integrated with [[monitoring-CloudTrail#^718023|CloudTrail]] for auditing
	- tracks key usage, resources, and when it was used
- uses <span style='color:#fa8231'>Customer Master Keys (CMKs)</span> for data encryption/decryption ^d80ca6
- offers automatic annual master key rotation w/o needing to re-encrypt existing data
- ensures extreme data/key availability with multiple copies of your keys stored for 99.999999999% durability
- connects directly to a VPC private endpoint in your VPC, eliminating need for public internet access
- fine-grained security controls via customizable VPC endpoint policies:
	- which principals can access your VPC endpoint
	- which API calls can be made
	- which resources can be accessed 
## concepts
### CMKs - customer managed keys 
- handle encryption/decryption of data
- used for data key generation and external data encryption
- 256 bits in length
#### customer managed CMKs %% fold %%
- created, owned, managed by customer 
- full controls over
	- key policies 
	- [[security-identity-compliance-aws-iam#^ab9f15|IAM]] policies 
	- creating grants + enabling/disabling them
#### AWS managed CMKs %% fold %% 
- created, managed, and owned by AWS 
- viewable in key policies and audit trails in [[monitoring-cloudwatch#^7382c4|CloudWatch]]
- indirect cryptographic use:
	- AWS services create them and use them on your behalf
#### AWS owned CMKs: %% fold %%
- not in your AWS account; managed by AWS for multi-account use 
- used by AWS services to protect your data 
- cannot view, manage, use, or audit AWS owned CMKs 
#### data keys: %% fold %%
- used for encrypting data 
	- generated, encrypted, and decrypted with CMKs
	- not stored, managed, or tracked by KMS
#### envelope encryption: %% fold %%
- encrypt data with a data key 
	- encrypt data key with a master key  ^78297a
#### encryption context: %% fold %%
- optional key-value pairs 
- provide contextual info about the data for cryptographic ops
#### key policies: %% fold %%
- doc defining permissions for CMK use/management
#### grants: %% fold %%
- alternative to key policy for long term access to customer managed CMKs
#### grant tokens:  %% fold %%
- used to mitigate potential delays in granting permissions
#### automatic key rotation: %% fold %%
- CMK cryptographic material regenerated annually
#### aliases: %% fold %%
- "usernames" for CMKs 
- unique in account and [[AWS-Regions-and-Availability-Zones.jpg|region]]

## importing keys:
- CMKs store *key material* for encryption/decryption by default
- CMKs can be created without key material and have external material imported
- imported key material can have an expiration date, leading to an unusable CMK on expiry
- key material can be manually deleted
## deleting keys:
- deleting CMK erases key material and associated metadata, making data unrecoverable
- [[monitoring-cloudwatch#^7382c4|CloudWatch alarms]] can notify on CMK use during pending deletion 
- temporary key disabling is available
- KMS offers custom key stores using [[security-identity-compliance-cloudHSM#^282620|CloudHSM]]
- private VPC endpoints enable secure comms with KMS in AWS network
## Pricing:
- every CMK created (KMS generated/imported key material) incurs cost until deletion
- CMKs with KMS generated key material with automatic annual rotation increase monthly costs per rotation
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-key-management-service-aws-kms/)
- [developer guide](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/kms  
---