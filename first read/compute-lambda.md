---
service: AWS lambda
service-type: serverless compute
---

---
Table of Contents:

---
# AWS Lambda

^a7928c

---
- **key insights:**  ^74b901
	- serverless compute service; executes code only when needed and scales automatically
	- pay as you go pricing: pay only for code execution time
---
**table of contents:**
- [[#overview %% fold %%|overview %% fold %%]]
- [[#key features  %% fold %%|key features  %% fold %%]]
	- [[#key features  %% fold %%#resource management %% fold %%|resource management %% fold %%]]
	- [[#key features  %% fold %%#functionality and integration %% fold %%|functionality and integration %% fold %%]]
	- [[#key features  %% fold %%#Security %% fold %%|Security %% fold %%]]
	- [[#key features  %% fold %%#Admin/maintenance %% fold %%|Admin/maintenance %% fold %%]]
	- [[#key features  %% fold %%#operational tool integration %% fold %%|operational tool integration %% fold %%]]
--- 
## overview %% fold %%
- stateless:
	- each lambda function execution is independent
	- no data/state from previous executions are remembered
- native support for:
	- node.js
	- java
	- C#
	- go
	- python
	- ruby
	- powershell
- custom runtimes are possible
- executes code in response to events:
	- state changes, user actions, etc.
- extends other AWS services or create custom backend services
- handles multiple event types:
	- HTTP requests
	- S3 object changes
	- DynamoDB updates
	- Step functions
- high availability infrastructure
- administers compute resources entirely
- includes maintenance, scaling, security, patching, monitoring, and logging
- user supplies code
## key features  %% fold %%
### resource management %% fold %%
- choose amount of memory for functions
- automatic allocation of CPU power, network bandwidth, and I/O
- support for packaging/deploying functions as container images
### functionality and integration %% fold %%
- custom logic for AWS resources
- easy setup/trigger config
- supports many programming languages
- relational DB connection support
- shared file system access
- CloudFront request handling
- step function orchestration
### Security %% fold %%
- integrated IAM model
- code signing for integrity
- multiple compliance certifications
### Admin/maintenance %% fold %%
- automated administration
- fault tolerance across zones
- granular billing
- flexible resource allocation
### operational tool integration %% fold %%
- extensions for tool integration
- diagnostic data capture
- minimal operational impact
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-lambda/)
# Tags
- #aws-ccp-exam-notes/services/compute/lambda
---