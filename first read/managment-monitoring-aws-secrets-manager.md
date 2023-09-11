---
management: "aws secrets manager: rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle"
---
# AWS secrets manager 
---
- easily rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle
- encrypts secrets at rest using your [[security-aws-kms#CMKs - customer managed keys|CMKs]] 
	- Secrets Manager decrypts the secret and transmits it securely over TLS to your local environment when retrieved 
- rotate secrets on a schedule or on demand via Secrets Manager console, AWS SDK, or AWS CLI
- natively supports rotating credentials for databases on [[database-RDS#^5a198f|RDS]],  [[databases-documentdb#^3d4b73|DocumentDB]] and clusters hosted on [[database-redshift#^fd71f3|RedShift]]
- pay based on number of secrets stored + API calls made/month  
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-secrets-manager/) 
# Tags
- #aws-ccp-exam-notes/services/management-monitoring/secrets-manager 

	

