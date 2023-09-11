
---
Table of Contents:

---
# Amazon Detective
---
- **key insights:** 
	- collects log data from AWS resources
	- uses ML, stats, and graph theory for security investigations
	- builds a unified, interactive view for identifying security concerns
	- can integrate with
		- [[security-identity-compliance-amazon-guard-duty#^04cebc|Amazon GuardDuty]]
		- [[security-identity-compliance-amazon-macie#^c13eab|Amazon Macie]]
		- [[security-identity-compliance-aws-security-hub#^d7ac3d|AWS security hub]]
	- has prebuilt data aggregations, summaries, and context for analysis
	- enabled on a per-[[AWS-Regions-and-Availability-Zones.jpg|region]] basis
---
**table of contents:**
- [[#key benefits|key benefits]]
- [[#Detective vs GuardDuty and Security Hub|Detective vs GuardDuty and Security Hub]]
- [[#guidance provided|guidance provided]]
- [[#detective and security hub|detective and security hub]]
- [[#Detective and EKS|Detective and EKS]]
- [[#pricing|pricing]]
--- 
## key benefits
- simplifies security investigations
- maintains up to a year of aggregated data
- visualizations of activity changes linked to findings
- no upfront costs
	- pay only for analyzed events
	- no additional software/log feeds needed
## Detective vs GuardDuty and Security Hub
- [[security-identity-compliance-amazon-guard-duty#^04cebc|GuardDuty]] monitors for threats
- [[security-identity-compliance-aws-security-hub#^d7ac3d|Security Hub]] aggregates alerts from multiple AWS services
- detective simplifies process of investigating security findings and identifying the root cause
	- analyzes trillions of events from various sources and creates an interactive graph model of your resources, users, and interactions b/w them over time
## guidance provided
- creates visualizations to answer questions related to findings/activity
- textual guidance explains how to interpret and use info
## detective and security hub
- detective continuously analyzes + correlates activity
	- works with services integrated with [[security-identity-compliance-aws-security-hub#^d7ac3d|security hub]] 
	- ingests security findings through AWS security findings ^3c6a7e
		- don't need to configure AWS Security Findings; just enable [[security-identity-compliance-aws-security-hub#^d7ac3d|security hub]] and data source in Amazon Detective
		- cost won't increase for [[security-identity-compliance-aws-security-hub#^d7ac3d|security hub]] and integrated security services due to Detective's usage
## Detective and EKS
- detective automatically analyzes user, network, and config activity across [[compute-EKS#^e5841c|EKS]] workloads
- ingests EKS audit logs and correlates user activities with [[monitoring-CloudTrail#^718023|CloudTrail]] and network activity with [[security-identity-compliance-amazon-guard-duty#^04cebc|Amazon VPC Flow logs]] 
- stores security data in graph db for 1 year
- provides data analysis/visualization for investigating malicious behavior in [[compute-EKS#^e5841c|EKS]] workloads
## pricing
- depends on volume of processed findings
- free 30 day trial for customers enabling [[security-identity-compliance-amazon-detective#^3c6a7e|AWS security findings]]
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-detective/)
- [detective FAQs](https://aws.amazon.com/detective/faqs/)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/detective   
---