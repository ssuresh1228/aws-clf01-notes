
---
Table of Contents:

---
# AWS Artifact
---
- **key insights:**  ^b5c2c4
	- central repository for AWS security and compliance reports/agreements
	- audit artifact: evidence of adherence to documented processes and compliance requirements
---
**table of contents:**
- [[#overview|overview]]
- [[#access to AWS artifact|access to AWS artifact]]
- [[#types of artifact agreements|types of artifact agreements]]
- [[#termination/removal|termination/removal]]
--- 
## overview
- offers on demand access to security/compliance docs
	- ISO certs, PCI (payment card industry) reports, and SOC (service organization control) reports
	- docs are used for audits, regulatory compliance, and assessing internal protocols
- provides docs from ISVs (independent software vendors) on AWS marketplace
- users are responsible for their company's security/compliance
	- [[shared-responsibility-model|shared responsibility model]]
- allows reviewing/accepting <mark style="background: #FF000094;">AWS Artifact Agreements</mark> like
	- BAA - business associate addendum for HIPPA compliance
- users can accept agreements for multiple accounts through AWS Organizations
## access to AWS artifact
- all AWS accounts with Artifact [[security-identity-compliance-aws-iam#^ab9f15|IAM]] permissions have access
- root/IAM users with admin permissions can download all audit artifacts by agreeing to terms
- IAM users without admin permissions cannot access AWS artifact
## types of artifact agreements
- <mark style="background: #930083;">account agreements</mark>:
	- apply to individual AWS accounts
- <mark style="background: #0055FF;">organization agreements</mark>:
	- apply to all accounts in an AWS organization
	- only management account in the organization can accept this
- management and member accounts can have both agreements at once
- for accounts in separate AWS organizations:
	- each org's management account must accept relevant agreements though <mark style="background: #00FF266B;">AWS Artifact Organization Agreements</mark>
## termination/removal
- terminating an organizational agreement doesn't terminate the account agreement
- when a member account is removed from an organization:
	- organization agreements no longer apply to that account
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-artifact/)
- [AWS Artifact overview - AWS](https://docs.aws.amazon.com/artifact/latest/ug/what-is-aws-artifact.html)
- [FAQ](https://aws.amazon.com/artifact/faq/)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/artifact  
---