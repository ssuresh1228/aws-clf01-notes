---
network: "amazon VPC: virtual network in the cloud dedicated to your AWS account where you can launch AWS resources"
---

# amazon VPC
---
- **key insights:**  ^4ff0f7
	- virtual network in the cloud dedicated to your AWS account where you can launch  resources
	- networking layer of [[compute-EC2#^e5d497|EC2]] 
	- spans all AZs in a region 
	- after VPC creation, 1/more subnets can be added in each AZ
---  
## key concepts 
- A **virtual private cloud** (VPC) lets you set an IP range, add subnets, link security groups, and adjust route tables. 
- A **subnet** is an IP range in your VPC where you can deploy AWS resources. 
- Use a **public subnet** for internet-connected resources and a **private subnet** for those not connected. 
- Use **security groups** and **network ACLs** for resource protection. 
- Broaden VPC with secondary IP ranges.
## use case scenarios 
### VPC with a Single Public Subnet %% fold %% 
- simplest use case where all your instances are placed in a single public subnet. All resources in this subnet can directly access the internet.
### VPC with Public + Private Subnets (NAT) %% fold %% 
- Public subnet instances can directly access the internet
- private subnet use a NAT Gateway for indirect, secure internet access.
### VPC with Public + Private Subnets + AWS Managed VPN Access %% fold %% 
- Public subnet instances access the internet directly.
- Private ones use a NAT Gateway for indirect, secure internet access.
- Securely connect your home network or office to your AWS VPC via AWS's VPN service.
### VPC with a Private Subnet Only and AWS Managed VPN Access %% fold %% 
- typically used for running private applications or for enhanced security.
- no access from the private subnet, but through AWS Managed VPN instead
	- secure connection between your existing network and your VPC.
## pricing 
- Billed for VPN and NAT Gateway hours.
- Fees apply per Gigabyte processed via NAT, regardless of traffic source/destination.
- Standard AWS data transfer charges apply.
- Costs for unused Elastic IPs.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-vpc/)
# Tags
- #aws-ccp-exam-notes/services/networking/vpc 
---


	

