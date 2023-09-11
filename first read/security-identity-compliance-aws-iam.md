---
security: IAM  - identity and access management
sticker: emoji//1f92c
---

# AWS IAM - identity and access management
---
- **key insights:**  ^ab9f15
	- web service for secure AWS resource access control
	- manages permissions for AWS resource access centrally
	- controls authentication and authorization for resource use
	- root user credentials should not be used for daily tasks
---
**table of contents:**
- [[#features|features]]
	- [[#features#granular permissions %% fold %%|granular permissions %% fold %%]]
	- [[#features#resource specific permissions %% fold %%|resource specific permissions %% fold %%]]
	- [[#features#2 factor authentication %% fold %%|2 factor authentication %% fold %%]]
	- [[#features#identity federation %% fold %%|identity federation %% fold %%]]
	- [[#features#CloudTrail logging %% fold %%|CloudTrail logging %% fold %%]]
	- [[#features#access keys  %% fold %%|access keys  %% fold %%]]
	- [[#features#PCI DSS compliant|PCI DSS compliant]]
	- [[#features#eventual consistency  %% fold %%|eventual consistency  %% fold %%]]
	- [[#features#IAM tags %% fold %%|IAM tags %% fold %%]]
	- [[#features#credential report %% fold %%|credential report %% fold %%]]
- [[#users|users]]
	- [[#users#iam users %% fold %%|iam users %% fold %%]]
	- [[#users#federated users %% fold %%|federated users %% fold %%]]
	- [[#users#groups %% fold %%|groups %% fold %%]]
	- [[#users#iam role %% fold %%|iam role %% fold %%]]
		- [[#iam role %% fold %%#AWS service role %% fold %%|AWS service role %% fold %%]]
			- [[#AWS service role %% fold %%#EC2 instance role %% fold %%|EC2 instance role %% fold %%]]
			- [[#AWS service role %% fold %%#service-linked role  %% fold %%|service-linked role  %% fold %%]]
		- [[#iam role %% fold %%#instance profile %% fold %%|instance profile %% fold %%]]
- [[#when to create a user vs role|when to create a user vs role]]
	- [[#when to create a user vs role#user %% fold %%|user %% fold %%]]
	- [[#when to create a user vs role#role %% fold %%|role %% fold %%]]
- [[#policies|policies]]
	- [[#policies#identity-based policies %% fold %%|identity-based policies %% fold %%]]
	- [[#policies#resource-based policies %% fold %%|resource-based policies %% fold %%]]
		- [[#resource-based policies %% fold %%#trust policies %% fold %%|trust policies %% fold %%]]
- [[#tasks requiring root user|tasks requiring root user]]
- [[#best practices|best practices]]

--- 
## features
### granular permissions %% fold %%
- grant permissions to use resources w/out sharing credentials
### resource specific permissions %% fold %%
- different permissions for different users/resources 
### 2 factor authentication %% fold %%
- more security with 2FA
### identity federation %% fold %%
- users can temporarily access AWS via identity federation
### CloudTrail logging %% fold %%
- integrates with [[monitoring-CloudTrail#^718023|CloudTrail]] 
- records IAM identity's resource requests
### access keys  %% fold %% 
- used for programmatic AWS requests
- unique and regenerable
### PCI DSS compliant 
### eventual consistency  %% fold %% 
- high availability by replicating data across multiple data centers in the world 
### IAM tags %% fold %%
- attach custom attributes to users/roles with key-value pairs 
### credential report %% fold %%
- generate and download
- has all users with status of password, access key. and MFA device
## users
### iam users %% fold %%
- individual users in your AWS account
- correspond to organization members 
- have passwords for console access 
- optional access keys for programmatic requests 
- global entities in your account
### federated users %% fold %%
- federate user identities, providing access if already authenticated
### groups %% fold %%
- collection of users 
- allows policy attachment; all users in the group have this permission 
- users can be in multiple groups 
- cannot be nested with other groups 
- do not have credentials/direct web service access
### iam role %% fold %%
- no credentials
- used for temporary permissions 
#### AWS service role %% fold %%
- used by services for actions in your account 
##### EC2 instance role %% fold %%
- used by services to launch [[compute-EC2#^e5d497|EC2]] instances 
##### service-linked role  %% fold %%
- predefined; links directly to AWS services 
#### instance profile %% fold %%
- container for IAM role 
- provides role info to EC2 instances during startup
## when to create a user vs role 
### user %% fold %%
- single user AWS account 
- distinct access credentials are needed
- typically for real users
### role %% fold %%
- used for temporary permissions 
- for apps, services, or entities assuming roles 
- for federated access w/out reauthentication
## policies 
- most are JSON format
- IAM console displays policy summaries 
- allows assigning of permissions to federated users through roles
### identity-based policies %% fold %%
- attached to a principal (identity)
- managed policies are standalone; can be attached to multiple entities 
- inline policies are created and managed directly within a single entity 
### resource-based policies %% fold %%
- attached to resources like [[storage-s3#^939999|S3 buckets]]
#### trust policies %% fold %%
- resource based policies for roles 
- specifies trusted principals 
## tasks requiring root user 
- modify account settings
	- email, password, name, access keys, etc.
- restore IAM user permissions
- activate IAM access to Billing and Cost Management
- view certain tax invoices
- close AWS account
- register as a seller in [[reserved-instance-discount#^7433b9|reserved instance]] marketplace 
- configure MFA for [[storage-s3#^939999|S3]] bucket 
- sign up for AWS GovCloud (US) + request its root user access keys 
- recover unmanageable [[security-aws-kms#^bed19a|KMS]] keys though AWS Support
## best practices 
- lock root user access keys 
- create individual IAM Users 
- use groups to assign permissions to IAM users 
- prefer AWS defined policies when possible 
- use access levels to review permissions 
- enforce strong password policies 
- enable MFA for privileged users 
- use roles for EC2 apps and delegation
- don't share access keys 
- rotate credentials regularly 
- remove unnecessary credentials 
- use policy conditions for more security
- monitor AWS account activity
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-identity-and-access-management-iam/)
- [tasks requiring root user](https://docs.aws.amazon.com/accounts/latest/reference/root-user-tasks.html) 
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/iam  
---
