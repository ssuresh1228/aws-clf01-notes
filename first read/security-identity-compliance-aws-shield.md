---
service: Shield
service-type: security
---

# AWS Shield 
---
- **key insights:**  ^4cbf08
	- managed DDoS protection service that safeguards apps running on AWS
---
**table of contents:**
- [[#tiers and features|tiers and features]]
	- [[#tiers and features#standard  %% fold %%|standard  %% fold %%]]
	- [[#tiers and features#advanced %% fold %%|advanced %% fold %%]]
- [[#pricing|pricing]]
--- 
## tiers and features 
### standard  %% fold %%
- available for all customers for automatic protection 
- monitors incoming traffic
	- detects and mitigates malicious traffic 
- uses methods like packet filtering and traffic shaping 
- provides availability protection with [[networking-aws-cloudfront#^00eb30|CloudFront]] and [[networking-route-53#^82e4b9|Route 53]] 
- allows viewing of detected and mitigated threats in your account 
### advanced %% fold %% 
- enhances detection
	- monitors network traffic and app layer traffic 
- handles DDoS protection for layer 3, 4, and 7 attacks
- 24x7 access to AWS DDoS Response Team, requires [[business-enterprise-support-plan|business]] or [[enterprise-support-plan|enterprise]] support plans.
- Provides automatic and manual mitigation for DDoS attacks
- Offers real-time notifications and diagnostics via CloudWatch and Management Console
- Includes "DDoS cost protection" to prevent scaling charges during attacks
- Available globally on CloudFront and Route 53 edge locations
- Provides incident history for the past 13 months
## pricing
- shield standard: free 
- shield advanced: 
	- 1 year subscription commitment + monthly fee
	- more fees from [[networking-aws-cloudfront#^00eb30|CloudFront]], [[compute-ELB#^357633|ELB]], [[compute-EC2#^e5d497|EC2]] use 
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-shield/)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/shield  
---


	

