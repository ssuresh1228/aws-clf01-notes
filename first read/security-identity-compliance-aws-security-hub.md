---
service: security-hub
service-type: support, security
---
# Title
---
- **key insights:**  ^d7ac3d
	- comprehensive view of 
		- your security state in AWS
		- compliance with security industry standards 
			- compliance reports are found in [[security-identity-compliance-aws-artifact#^b5c2c4|AWS artifact]]
---
**table of contents:**
- [[#features|features]]
- [[#pricing|pricing]]
--- 
## features 
- aggregates and prioritizes security alerts from 
	- [[security-identity-compliance-amazon-guard-duty#^04cebc|GuardDuty]]
	- [[security-identity-compliance-amazon-inspector#^72ad21|inspector]]
	- [[security-identity-compliance-amazon-macie#^c13eab|macie]]
- works with AWS Organizations for simplified security management.
- automated compliance checks are based on industry standards.
- compliance checks use [[monitoring-config#^64534d|AWS config]] configuration items.
- Integrated dashboards show security and compliance status.
- Security findings can be sent to various systems via [[monitoring-cloudwatch#^7382c4|CloudWatch]] Events.
- Findings are stored for a minimum of 90 days in AWS Security Hub
## pricing 
- based on number of recorded configuration items, [[monitoring-config#^64534d|AWS Config]] rules/evals recorded 
- charged once for recording the config item 
- charged per conformance pack per [[AWS-Regions-and-Availability-Zones.jpg|region]]
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-security-hub/)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/security-hub  
---