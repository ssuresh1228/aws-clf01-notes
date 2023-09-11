---
service: ECR - elastic container registry
service-type: container
---

---
Table of Contents:

---
# Amazon ECR: Elastic Container Registey
---
- **key insights:**  ^bef2f7
	- AWS managed container image registry (like github)
	- scalable, reliable, secure
	- supports private repositories with IAM permissions
	- push, pull, and manage Docker/OCI images using CLI
---
**table of contents:**
- [[#Features %% fold %%|Features %% fold %%]]
	- [[#Features %% fold %%#lifecycle policies %% fold %%|lifecycle policies %% fold %%]]
	- [[#Features %% fold %%#image scanning  %% fold %%|image scanning  %% fold %%]]
	- [[#Features %% fold %%#cross-region/account replication %% fold %%|cross-region/account replication %% fold %%]]
	- [[#Features %% fold %%#pull through cache rules %% fold %%|pull through cache rules %% fold %%]]
- [[#Pricing %% fold %%|Pricing %% fold %%]]
--- 
## Features %% fold %%
### lifecycle policies %% fold %% 
- manage image lifecycle
- clean up rules and test before applying
### image scanning  %% fold %%
- find software vulnerabilities
- scan on push
- retrieve scan results
### cross-region/account replication %% fold %%
- easily replicate images
### pull through cache rules %% fold %%
- cache remote public registry images in ECR, ensure updates
## Pricing %% fold %%
- pay only for amount of data stored in repos and transferred data to internet
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-elastic-container-registry-amazon-ecr/)
- [ECR user guide](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html)
# Tags
- #aws-ccp-exam-notes/services/compute/container/ECR  
---