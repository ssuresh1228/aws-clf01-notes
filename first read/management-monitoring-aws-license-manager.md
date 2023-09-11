---
management: "aws license manager: centrally manages software licenses in AWS/on-premises"
---
# aws license manager
---
- **key insights:** 
	- centrally manages software licenses in AWS/on-premises
	- gives control/visibility into license usage, allowing you to limit licensing overages and reduce risk of noncompliance/misreporting
	- supported licensing models:
		- **Perpetual** – lifetime license with no expiration date.
		- **Floating** – shareable licenses.
		- **Subscription** – license with expiration date.
		- **Usage-based** – license with specific terms based on usage.
	- can buy licenses on AWS marketplace/data exchange/direct from seller
--- 
## concepts 
### License Configurations:
- Contains rules based on enterprise agreements.
- Has parameters and rules that change based on parameter values. 
- Defines how AWS handles commands using licenses.
- Allows modifications to license numbers and usage limits.
- Shareable using AWS RAM.
- Deactivation doesn't affect existing resources but stops license tracking.
### License Reports: 
- Track license usage history with periodic snapshots.
- Usage reports go to an [[storage-s3#^939999|S3 bucket]].
- Includes license consumption details and resource tracking.
### License Type Conversion:
- Convert license types without redeployment.
- Options: AWS provided licensing or BYOL.
- Change tenancy using AWS CLI: Shared, Dedicated Instance, Dedicated Host, Host Resource Groups.
### [[management-monitoring-aws-systems-manager#^a0aa4b|Systems Manager]] Inventory:
- Discovers on-premises apps and attaches licensing rules.
### License Purchase:
- Buy licenses from AWS Marketplace, AWS Data Exchange, or sellers with managed entitlements.
### License Capabilities:
- Captured as entitlements.
### Cross-Region Replication:
- For granted and seller-issued licenses.
- Automatically replicates license info to other regions.
### User-Based Subscriptions:
- Purchase Amazon provided licenses for Microsoft Visual Studio with a per-user subscription fee.
### Organization Delegation:
- One member account per organization can be an administrator.
### Dashboard:
- Displays license consumption and alert results for license rule violations.
## monitoring 
- track licenses for [[compute-EC2|EC2]]:
	- [[compute-EC2-summary#^1fee9e|dedicated hosts]]
	- [[compute-EC2-summary#^f11da0|dedicated instances]]
	- [[compute-EC2-summary#Spot instances fold|spot instances]]
	- [[compute-EC2-summary#spot fleet fold|spot fleet]]
- use [[monitoring-CloudTrail#^718023|CloudTrail]] to log calls from license manager console/API
## security 
- **Create and Distribute Licenses**:
    - Create licenses in AWS License Manager.
    - Distribute through [[security-identity-compliance-aws-iam#identity-based policies fold|IAM identities]] or digitally signed tokens.
- **License Signing**:
    - Sign and verify licenses using AWS KMS Sign and Verify API operations.
- **Private Connection**:
    - Establish a private connection between [[networking-vpc#^4ff0f7|VPC]] and AWS License Manager using an interface VPC endpoint.
## pricing 
- charged for AWS resources that you create to run your application
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-license-manager/)
# Tags
- #aws-ccp-exam-notes/services/management-monitoring/license-manager