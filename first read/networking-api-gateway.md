---
network: "amazon API Gateway: allows developers to create, manage, and secure APIs"
---

# API gateway
---
- **key insights:**  ^bfe094
	- Allows developers to create, manage, and secure APIs.
	- HIPAA eligible service that exposes backend services through RESTful API, forming part of AWS serverless infrastructure. 
## features 
- API Gateway runs [[compute-lambda#^74b901|Lambda]] code, initiates Step Functions, calls to [[compute-elastic-beanstalk#^2dd932|elastic beanstalk]], [[compute-EC2#^e5d497|EC2]], or web services with public HTTP endpoints. 
- manages API usage plans, traffic, and documentation. 
- allows selling APIs as SaaS products on AWS Marketplace. 
- directs HTTP API requests to private ELBs and AWS services, supports data mapping, and uses custom domain names for diverse URLs and API versioning.
- Only exposes HTTPS endpoints, not HTTP.
## monitoring 
- API Gateway console, integrated with CloudWatch, provides backend metrics like API calls, latency, and error rates. 
- You can establish custom alarms on APIs and log execution errors to [[monitoring-cloudwatch#^7382c4|CloudWatch]] Logs.
## security 
- aids in authorizing API requests to AWS services using signature version 4 authentication, enabling [[security-identity-compliance-aws-iam#^ab9f15|IAM and access policies]] for resource access. 
- [[security-identity-compliance-aws-waf|AWS WAF]] can be activated in API Gateway to safeguard your APIs against common web threats like SQL injection and XSS. 
- Besides OIDC/OAuth2, API Gateway HTTP APIs can be secured with [[compute-lambda#^a7928c|Lambda]] and IAM authorizers.
## pricing 
- pay only for the API calls you receive + amount of data transferred out.
- optional, hourly-charged data caching, with rates varying by cache size.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-api-gateway/)
# Tags
- #aws-ccp-exam-notes/services/networking/api-gateway 
---