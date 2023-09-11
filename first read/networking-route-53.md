---
network: "amazon route 53: highly available and scalable DNS used for domain registration, routing, and health checking"
---
# amazon route 53
---
- **key insights:**  ^82e4b9
	- highly available and scalable DNS (translates website names into IPs)
	- used for domain registration, DNS routing, and health checking
	- routes users to internet apps
--- 
## key features 
- Resolver
- Traffic flow
- Latency based routing
- Geo DNS
- Private DNS for [[networking-vpc#^4ff0f7|amazon VPC]]
- DNS Failover
- Health Checks and Monitoring
- Domain Registration
- [[networking-aws-cloudfront#^00eb30|CloudFront]] and [[storage-s3#^939999|S3]] Zone Apex Support
- [[compute-ELB#^357633|Amazon ELB]] Integration
## authentication/access control 
- [[security-identity-compliance-aws-iam#^ab9f15|Authenticate with IAM]] before allowing any operation on Route 53 resources.
- Each AWS resource is owned by an account, and access is controlled by permissions policies.
- A _permissions policy_ specifies who has access to what.
## pricing 
- Hosted zone charged at creation then monthly 
	- No charge if deleted within 12 hours. Queries still charged. 
- Billion queries/month. 
- No extra cost for Alias queries to certain AWS resources. 
- Traffic flow policy record/month. 
- Domain name pricing varies by TLD (Top Level Domain)
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-route-53/)
# Tags 
- #aws-ccp-exam-notes/services/networking/route53 


	

