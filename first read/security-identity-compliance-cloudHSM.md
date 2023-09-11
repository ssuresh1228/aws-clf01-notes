
---
Table of Contents:

---
# AWS CloudHSM
---
- **key insights:**  ^282620
	- provides secure, flexible management of cryptographic keys and operations while offering control and compatibility for various applications, simplifying migration for users of PKCS #11, JCE, CNG, or KSP.
	- merges cloud advantages with hardware security modules (HSMs)
	- HSMs process crypto operations and securely store keys
	- cloudHSM offers control, high availability, low latency access, and automated HSM management
	- charged per hour per HSM launched
---
**table of contents:**
- [[#overview|overview]]
- [[#use cases|use cases]]
- [[#pricing|pricing]]
--- 
## overview
- cloudHSM uses FIPS 140-2 level 3 validated HSMs
- offers more flexibility compared to managed AWS services like [[security-identity-compliance-aws-iam#^ab9f15|IAM]]
- end to end encryption ensures data privacy and control over user management, though with more responsiblity
	- AWS is no longer responsible for user management, you are
- provides control over cryptographic keys, algorithms, and app development
	- includes session, token, symmetric, and asymmetric keys
- simplifies migration of cryptographic workloads
	- infra using the following requires fewer changes for cloud migration: 
		- Public Key Cryptography Standards #11 (PKCS #11) 
		- Java Cryptographic Extension (JCE)
		- Cryptography API: Next Generation (CNG)
		- key storage provider (KSP) 
## use cases
- AWS CloudHSM ensures compliance with robust security standards, including FIPS 140-2 level 3, PCI DSS, and more.
- manages encryption keys, offering secure data encryption and decryption along with support for digital signatures.
- AWS CloudHSM empowers users to handle symmetric keys for message authentication.
- Combining AWS CloudHSM with AWS KMS delivers certified key storage and cloud integration.
- Offloading SSL/TLS processing for web servers reduces computation while enhancing security.
- Transparent Data Encryption (TDE) is supported for safeguarding database files.
- AWS CloudHSM securely stores private keys for certificate authorities.
- It provides a secure environment for generating essential random numbers.
## pricing
- charged per hour per HSM launched
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-cloudhsm/)
- [AWS user guide](https://docs.aws.amazon.com/cloudhsm/latest/userguide/use-cases.html)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/cloudHSM   
---