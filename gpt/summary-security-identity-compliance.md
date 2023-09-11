---
gpt-summary: security, identity, compliance
---
# Summary: security, identity, compliance
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	- [[security-identity-compliance-overview]]
- <mark style="background: #FF000094;">meta</mark>: 
	- [[meta-security-identity-compliance]]
---
**<span style='color:#20bf6b'>table of contents:</span>**
- [[#AWS artifact|AWS artifact]]
	- [[#AWS artifact#use case: %% fold %%|use case: %% fold %%]]
	- [[#AWS artifact#overview: %% fold %%|overview: %% fold %%]]
- [[#AWS certificate manager (ACM)|AWS certificate manager (ACM)]]
	- [[#AWS certificate manager (ACM)#use case:%% fold %%|use case:%% fold %%]]
	- [[#AWS certificate manager (ACM)#overview:%% fold %%|overview:%% fold %%]]
	- [[#AWS certificate manager (ACM)#pricing:%% fold %%|pricing:%% fold %%]]
- [[#AWS cloudHSM|AWS cloudHSM]]
	- [[#AWS cloudHSM#use case:  %% fold %%|use case:  %% fold %%]]
	- [[#AWS cloudHSM#overview: %% fold %%|overview: %% fold %%]]
	- [[#AWS cloudHSM#pricing: %% fold %%|pricing: %% fold %%]]
- [[#AWS cognito|AWS cognito]]
	- [[#AWS cognito#use case:%% fold %%|use case:%% fold %%]]
	- [[#AWS cognito#overview:%% fold %%|overview:%% fold %%]]
	- [[#AWS cognito#pricing:%% fold %%|pricing:%% fold %%]]
- [[#AWS key management system (KMS)|AWS key management system (KMS)]]
	- [[#AWS key management system (KMS)#use case:  %% fold %%|use case:  %% fold %%]]
	- [[#AWS key management system (KMS)#overview:  %% fold %%|overview:  %% fold %%]]
	- [[#AWS key management system (KMS)#pricing:  %% fold %%|pricing:  %% fold %%]]
- [[#amazon detective|amazon detective]]
	- [[#amazon detective#use case:%% fold %%|use case:%% fold %%]]
	- [[#amazon detective#overview:%% fold %%|overview:%% fold %%]]
	- [[#amazon detective#pricing:%% fold %%|pricing:%% fold %%]]
- [[#amazon guard duty|amazon guard duty]]
	- [[#amazon guard duty#use case:%% fold %%|use case:%% fold %%]]
	- [[#amazon guard duty#overview:%% fold %%|overview:%% fold %%]]
	- [[#amazon guard duty#pricing:%% fold %%|pricing:%% fold %%]]
- [[#AWS IAM|AWS IAM]]
	- [[#AWS IAM#use case:%% fold %%|use case:%% fold %%]]
	- [[#AWS IAM#overview:%% fold %%|overview:%% fold %%]]
	- [[#AWS IAM#pricing:%% fold %%|pricing:%% fold %%]]
- [[#amazon inspector|amazon inspector]]
	- [[#amazon inspector#use case:%% fold %%|use case:%% fold %%]]
	- [[#amazon inspector#overview:%% fold %%|overview:%% fold %%]]
	- [[#amazon inspector#pricing:%% fold %%|pricing:%% fold %%]]
- [[#amazon macie|amazon macie]]
	- [[#amazon macie#use case:|use case:]]
	- [[#amazon macie#overview:|overview:]]
	- [[#amazon macie#pricing:|pricing:]]
- [[#AWS shield|AWS shield]]
	- [[#AWS shield#use case:%% fold %%|use case:%% fold %%]]
	- [[#AWS shield#overview:%% fold %%|overview:%% fold %%]]
	- [[#AWS shield#pricing:%% fold %%|pricing:%% fold %%]]
- [[#AWS security hub|AWS security hub]]
	- [[#AWS security hub#use case:%% fold %%|use case:%% fold %%]]
	- [[#AWS security hub#overview:%% fold %%|overview:%% fold %%]]
	- [[#AWS security hub#pricing: %% fold %%|pricing: %% fold %%]]
--- 
## AWS artifact
### use case: %% fold %% 
- Central repository for AWS security and compliance reports/agreements
- Evidence of adherence to documented processes and compliance requirements
### overview: %% fold %% 
- On-demand access to security/compliance documents
- Provides ISO certs, PCI reports, and SOC reports
- Used for audits, regulatory compliance, and assessing internal protocols
- Offers docs from ISVs on AWS marketplace
- Users responsible for their company's security/compliance
- Allows reviewing/accepting AWS Artifact Agreements
- Users can accept agreements for multiple accounts through AWS Organizations
## AWS certificate manager (ACM)
### use case:%% fold %%
- Simplify the management of SSL/TLS certificates for secure communication.
### overview:%% fold %%
- manages SSL/TLS certificates for easy creation, storage, and renewal.
- supports both public and private certificates.
- Integrated with various AWS services like Elastic Load Balancer, CloudFront, Elastic Beanstalk, API Gateway, and CloudFormation.
- Pay per active ACM private CA monthly, with lower rates for more certificates.
### pricing:%% fold %%
- No extra cost for SSL/TLS certificates with ACM-integrated services.
- Pay per active ACM private CA monthly, with lower rates for more certificates.
## AWS cloudHSM
### use case:  %% fold %% 
- ensures compliance with security standards like FIPS 140-2 level 3 and PCI DSS.
- It manages encryption keys, supports digital signatures, and handles symmetric keys for message authentication.
### overview: %% fold %% 
- merges cloud advantages with hardware security modules (HSMs).
- It provides secure key management and cryptographic operations.
- Users have control over keys, algorithms, and app development.
- Simplifies migration of cryptographic workloads.
### pricing: %% fold %% 
- charged per hour per HSM launched.
## AWS cognito 
### use case:%% fold %%
- Simplifies user sign-up and authentication for mobile and web apps
- Supports external identity providers like SAML, OpenID connect, and social media providers
### overview:%% fold %%
- User pools are user directories for managing local users
- Cognito handles tokens from identity providers and converts them into JWTs for the app
- Identity pools assign unique IDs to users with AWS credentials
- Supports authentication based on trusted claims from identity providers
- Role-based access control allows customization of role permissions with IAM policies
- Regional availability ensures high availability and low latency for Cognito services
### pricing:%% fold %%
- Pricing is based on monthly active users (MAUs)
- Free tier includes 50k MAUs for direct sign-ins or social identity providers
- Extra fees apply for advanced security features
- SMS costs for MFA (phone number verification) through Amazon SNS
## AWS key management system (KMS)
### use case:  %% fold %% 
- Securely manage and encrypt data in AWS services and applications
### overview:  %% fold %% 
- KMS is a managed service for data encryption
- Provides key storage, management, and auditing
- Encrypts data in apps and across AWS services
- Offers fine-grained security controls and extreme data/key availability
- Supports customer managed keys and AWS managed keys
- Provides features like automatic key rotation and encryption context
### pricing:  %% fold %% 
- Costs incurred for every created CMK until deletion
- CMKs with automatic annual rotation increase monthly costs per rotation
## amazon detective 
### use case:%% fold %% 
- Simplifies security investigations
- Provides visualizations of activity changes linked to findings
### overview:%% fold %% 
- Collects log data from AWS resources
- Uses ML, stats, and graph theory for security investigations
- Builds a unified, interactive view for identifying security concerns
- Can integrate with Amazon GuardDuty, Amazon Macie, and AWS Security Hub
- Has prebuilt data aggregations, summaries, and context for analysis
- Enabled on a per-region basis
### pricing:%% fold %% 
- Depends on the volume of processed findings
- Free 30-day trial for customers enabling AWS security findings
## amazon guard duty 
### use case:%% fold %%
- Intelligent threat detection service
- Analyzes events across AWS accounts for threat detection
### overview:%% fold %%
- Uses AWS CloudTrail, VPC Flow Logs, and DNS logs for analysis
- Provides 3 severity levels (low, med, high) for prioritizing response
- Detects reconnaissance, instance compromise, and account compromise threats
- Generates findings with detailed information on threats
- Supports trusted IPs for secure communication
- Supports threat lists for detecting known malicious IPs
- Differentiates from Macie, which focuses on data classification and protection in S3
### pricing:%% fold %%
- Based on CloudTrail events per 1,000,000 events
- Based on VPC Flow Logs and DNS log data per GB
## AWS IAM 
### use case:%% fold %%
- Securely manage access to AWS resources
### overview:%% fold %%
- IAM is a web service that provides secure access control for AWS resources
- It centrally manages permissions for resource access and controls authentication and authorization
### pricing:%% fold %%
- IAM is offered at no additional cost, users only pay for the AWS resources they access
## amazon inspector
### use case:%% fold %% 
- Assessing the security configuration and behavior of AWS cloud resources.
### overview:%% fold %% 
- Analyzes system/resource configuration and monitors activity.
- Provides insight into assessment targets.
- Uses an API and optional agent for easy deployment/automation.
- Single-step deployment across all accounts.
- Automated discovery and real-time vulnerability findings.
- Central management with delegated admin account.
- Contextual risk scores for accurate response prioritization.
- Integration with Security Hub and EventBridge for workflow automation.
### pricing:%% fold %% 
- Based on the number of EC2 instances in each assessment and the type(s) of rule packages.
## amazon macie 
### use case:
- Automatically find and protect sensitive data in AWS
### overview:
- Uses machine learning to identify and prioritize sensitive data like personally identifiable information and intellectual property
- Provides data type identification, compliance verification, policy change detection, data egress alerts, and document sharing detection
### pricing:
- Based on content classified and CloudTrail events assessed
- Free storage of classified S3 object metadata for 30 days, with optional extended data retention for a monthly fee
## AWS shield 
### use case:%% fold %%
- Protecting applications running on AWS from DDoS attacks
### overview:%% fold %%
- AWS Shield is a managed DDoS protection service for AWS applications
- Monitors incoming traffic and detects/mitigates malicious traffic
- Uses packet filtering and traffic shaping methods
- Provides availability protection with CloudFront and Route 53
- Advanced tier includes enhanced detection, 24x7 access to DDoS Response Team, automatic/manual mitigation, real-time notifications, and incident history
- Standard tier is available for all customers for automatic protection
- Advanced tier requires business or enterprise support plans
- Provides DDoS cost protection to prevent scaling charges during attacks
### pricing:%% fold %%
- Shield Standard: Free
- Shield Advanced: 1 year subscription commitment + monthly fee, additional fees for CloudFront, ELB, and EC2 use
## AWS security hub
### use case:%% fold %%
- Comprehensive view of security state in AWS
- Compliance with security industry standards
### overview:%% fold %%
- Aggregates and prioritizes security alerts from GuardDuty, Inspector, and Macie
- Works with AWS Organizations for simplified security management
- Automated compliance checks based on industry standards
- Integrated dashboards show security and compliance status
- Security findings can be sent to various systems via CloudWatch Events
- Findings are stored for a minimum of 90 days in AWS Security Hub
### pricing: %% fold %% 
- Based on the number of recorded configuration items and AWS Config rules/evals recorded
- Charged once for recording the config item
- Charged per conformance pack per region


# tags:
- #gpt-summary/aws-ccp/security-identity-compliance 