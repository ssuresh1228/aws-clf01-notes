---
service: amazon fargate
service-type: serverless container cluster management
---
# Amazon Fargate
---
- **key insights:**  ^c08b80
	- managed service for container cluster management
	- serverless compute engine for containers
	- works with [[compute-ECS|ECS]] and [[compute-EKS|EKS]] 
	- no manual provisioning, patching, cluster capacity management, or infrastructure management needed
---
**table of contents:**
- [[#key features %% fold %%|key features %% fold %%]]
- [[#use cases %% fold %%|use cases %% fold %%]]
- [[#Pricing %% fold %%|Pricing %% fold %%]]
--- 
## key features %% fold %%
- serverless container compute engine
- works with ECS and EKS
- eliminates server management
- enhances security through isolation
## use cases %% fold %%
- launch containers without provisioning/managing [[compute-EC2#Instance types fold|EC2 instances]]
- wide range of applications
	- web apps, APIs, microservices
	- data processing
	- AI/ML apps
	- cloud-native/migration tasks
## Pricing %% fold %% 
- pay for amount of vCPU/memory resources used by containerized apps
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-fargate/)
- [fargate FAQs](https://aws.amazon.com/fargate/faqs/)
- [ECS on fargate - developer guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html)
# Tags
- #aws-ccp-exam-notes/services/compute/container/fargate  
---