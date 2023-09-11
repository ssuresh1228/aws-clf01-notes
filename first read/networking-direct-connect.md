---
network: "AWS direct connect: provides a dedicated network connection from your premises to AWS"
---

# AWS direct connect
---
- **key insights:** 
	- dedicated network connection from your premises to AWS
	- Links network to Direct Connect via Ethernet fiber-optic cable. One end to your router, other to Direct Connect router. 
	- Allows creation of virtual interfaces to AWS services or [[networking-vpc#^4ff0f7|VPC]].
	- 1 Gbps, 10 Gbps, and 100 Gbps connection options
	- Supports hosted connection capacities of 1, 2, 5 and 10 Gbps
	- [[security-identity-compliance-aws-iam#^ab9f15|IAM]] to control access 
---
## use cases 
- transferring large datasets
- developing/using apps with real-time data feeds 
- building hybrid environments to satisfy regulations of private connections 
## monitoring 
- Optional tags for Direct Connect resources to categorize/manage
	- Tag = key + optional user-defined value
- [[monitoring-CloudTrail#^718023|CloudTrail]] captures all API calls for AWS Direct Connect as events.
- Set up [[monitoring-cloudwatch#^7382c4|CloudWatch]] alarms to monitor metrics.
## pricing 
- pay only for network ports used and data transferred over the connection.
- cost is based on port type + usage
- Data transfer out is charged per GB. 
- Data transfer IN is $0.00 per GB in all locations.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-direct-connect/#security)
# Tags
- #aws-ccp-exam-notes/services/networking/direct-connect 


	

