---
template: ""
---

# shared responsibility model
---
- Description: ^23c6a1
---
## AWS responsibility: Security *of* the cloud  %% fold %% 
- global infrastructure:
	- hardware, software, networking, datacenters, etc. that run AWS services
## Customer's Responsibility: Security *in* the cloud %% fold %% 
- depends on the service in use
- Customer always has some responsibility
- more config needed for IaaS (infra as a service)
- For EC2 (IaaS), the customer:
	- manages guest OS and security patches
	- installs/configures software
	- configures security groups
	- **customer focuses more on security config**
- Abstracted services (S3, DynamoDB):
	- AWS manages infra, OS, and platforms
	- Customer is responsible for data, encryption, and permissions
	- **Customer focuses more on data and access**

## Inherited Controls %% fold %% 
- Controls which a customer fully inherits from AWS
- Physical/environmental controls

## Shared Controls %% fold %% 
- Apply to both AWS and customer
	- Patch Management: AWS patches infra, but customers patch the guest OS and its apps
	- Config Management: AWS configures infra, but customers must configure their guest OS and its apps
- AWS trains its employees, but you have to train yours

## Customer specific %% fold %% 
- solely customer's responsibility
	- routing data within required security zones
	- depends on application

![[Shared_Responsibility_Model_V2.59d1eccec334b366627e9295b304202faf7b899b.jpg]]

---
# References
- [shared responsibility model](https://aws.amazon.com/compliance/shared-responsibility-model/)
- [cheat sheet](https://tutorialsdojo.com/aws-shared-responsibility-model/)
# Tags
- aws-ccp-exam-notes//shared-responsibility-model 