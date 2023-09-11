
---
Table of Contents:

---
# AWS ACM - AWS Certificate Manager
---
- **key insights:** 
	- manages SSL/TLS certificates, simplifying creation, storage, and renewal
	- supports public/private certificates
	- integrated with:
		- [[compute-ELB#^357633|Elastic Load Balancer (ELB)]]
		- [[networking-aws-cloudfront#^00eb30|CloudFront]] (must request/import certificate in US East (N.Virginia) [[AWS-Regions-and-Availability-Zones.jpg|region]])
		- [[compute-elastic-beanstalk#^2dd932|Elastic Beanstalk]]
		- [[networking-api-gateway#^bfe094|API gateway]]
		- [[monitoring-cloudformation|CloudFormation]]
	- pay per active ACM private CA monthly; rate lowers with more certs
---
**table of contents:**
- [[#concepts|concepts]]
- [[#public certificates|public certificates]]
- [[#private certificates|private certificates]]
- [[#imported certificates|imported certificates]]
- [[#CA certificates|CA certificates]]
- [[#ACM private certificate authority|ACM private certificate authority]]
- [[#pricing|pricing]]
--- 
## concepts
- issued by ACM or 3rd party certificates
	- secures various domains and wildcards
		- wildcards cover unlimited subdomains
- ACM certs are valid for 13 months
- ownership validation required for requested domains
- private key for ACM Cert cannot be downloaded
- delete only when not in use
- public certs trusted by default
	- private certs require explicit config
- [[security-aws-kms#^bed19a|AWS KMS]] creates a unique CMK for each cert in each [[AWS-Regions-and-Availability-Zones.jpg|region]]
- domain names can't be added/removed from existing certificates
	- must request new ones
## public certificates
- managed by ACM for renewal/deployment with integrated services
- can't be installed directly on websites/apps
## private certificates
- managed in 3 ways:
	- delegated to ACM for auto-renewal/deployment with integrated services
	- exported for use with various resources and auto-renewed by ACM private CA (certificate authority)
		- <mark style="background: #FF000094;">ACM private CA (certificate authority)</mark>: AWS service for secure internal certificate management, creating a secure CA hierarchy.
	- self management: create private keys, generate CSR, and issue certs from ACM private CA - manual renewal + deployment
## imported certificates
- 3rd party certificates can be imported into ACM
- ACM doesn't manage their renewal; must be done manually by the user
## CA certificates
- ACM Private CA enables creating a hierarchy of private certificate authorities (CAs) with varying levels of control for secure resource access.
## ACM private certificate authority
- secure private certificate issuance
- hierarchies for various security levels
- handles certificate creation, validation, and revocation
- benefits:
	- Create certificates with any subject name you want.
	- Create certificates with any expiration date you want.
	- Use any supported private key algorithm and key length.
	- Use any supported signing algorithm.
	- Configure certificates in bulk using templates.
- no auto-renewal
- no easy copying from region to [[AWS-Regions-and-Availability-Zones.jpg|region]]; must create separately
## pricing
- no extra cost for SSL/TLS certs with ACM-integrated services
- pay per active ACM private CA monthly
	- cost is lowered with more certs
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-certificate-manager/)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/acm  
- #aws-service
- #aws-security
---