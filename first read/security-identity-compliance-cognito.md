
---
Table of Contents:

---
# Amazon Cognito
---
- **key insights:** 
	- simplifies user sign-up and authentication for mobile and web apps
	- supports external identity providers: SAML, OpenID connect, and social media providers
	- syncs data across a user's devices; stores data locally enabling offline use, then auto-syncs when back online
	- pricing based on monthly active users (MAUs)
---
**table of contents:**
- [[#user pools|user pools]]
- [[#Identity pools|Identity pools]]
- [[#role-based access control|role-based access control]]
- [[#regional availability|regional availability]]
- [[#pricing|pricing]]
--- 
## user pools
- user pools are user directories
- users sign in via cognito or 3rd party identity providers (IdPs)
- local users are managed in AWS tools
- cognito handles tokens from IdPs, converting them into JWTs for your app
## Identity pools
- assigns unique IDs to users with AWS credentials
- authentication is based on trusted claims from identity providers
- tokens are generated by the identity pool for AWS access
- supports auth/un-auth access, including custom authentication
- integrates with [[security-identity-compliance-aws-iam#^ab9f15|IAM]] policies in 2 ways:
	- used together or separately
## role-based access control
- role selection based on user claims
- customize tole permissions with IAM policies
- roles can be default, rule-based, or group-based
- role trust policy ensures IAM trusts identity pool for sessions 
## regional availability
- available in multiple [[AWS-Regions-and-Availability-Zones.jpg|regions]]
- ensures high availability and low latency for cognito services
## pricing
- based on monthly active users
- free tier has 50k MAUs for direct sign-ins or social identity providers
	- 50 MAUs for SAML2.0 federated users
- extra fees apply for advanced security features
- SMS costs for MFA (phone number verification) through [[app-integration-sns#^6f6ad4|Amazon SNS]]
--- 
# Resources
- [cognito FAQs](https://aws.amazon.com/cognito/faqs/)
- [cognito docs](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html)
- [cheat sheet](https://tutorialsdojo.com/amazon-cognito/)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/cognito   
---