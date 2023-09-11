---
container: ECS - elastic container service
---
# AWS ECS: Elastic Container Service
---
- **key insights:**  ^daa71f
	- managed docker container orchestration
	- deploys, manages, and scales containers
	- integrates seamlessly in AWS
	- supports [[compute-EC2-summary|EC2]], [[compute-fargate|Fargate]], and on-premises with *ECS anywhere*
---
**table of contents:**
- [[#key features %% fold %%|key features %% fold %%]]
- [[#development %% fold %%|development %% fold %%]]
	- [[#development %% fold %%#docker support %% fold %%|docker support %% fold %%]]
	- [[#development %% fold %%#windows containers %% fold %%|windows containers %% fold %%]]
	- [[#development %% fold %%#AWS Copilot %% fold %%|AWS Copilot %% fold %%]]
	- [[#development %% fold %%#repository compatibility|repository compatibility]]
- [[#management %% fold %%|management %% fold %%]]
	- [[#management %% fold %%#task definitions  %% fold %%|task definitions  %% fold %%]] ^669548
	- [[#management %% fold %%#programmatic control %% fold %%|programmatic control %% fold %%]]
	- [[#management %% fold %%#container deployments %% fold %%|container deployments %% fold %%]]
	- [[#management %% fold %%#container auto-recovery %% fold %%|container auto-recovery %% fold %%]]
	- [[#management %% fold %%#capacity providers %% fold %%|capacity providers %% fold %%]]
	- [[#management %% fold %%#storage %% fold %%|storage %% fold %%]]
- [[#scheduling/task placement %% fold %%|scheduling/task placement %% fold %%]]
	- [[#scheduling/task placement %% fold %%#scheduling strategies %% fold %%|scheduling strategies %% fold %%]]
	- [[#scheduling/task placement %% fold %%#task scheduling %% fold %%|task scheduling %% fold %%]]
	- [[#scheduling/task placement %% fold %%#service scheduling %% fold %%|service scheduling %% fold %%]]
	- [[#scheduling/task placement %% fold %%#daemon scheduling %% fold %%|daemon scheduling %% fold %%]]
	- [[#scheduling/task placement %% fold %%#task placement %% fold %%|task placement %% fold %%]]
--- 
## key features %% fold %%
- integrated with [[compute-fargate#^c08b80]] 
- supports hybrid deployments with ECS Anywhere and AWS Outposts
- strong security/isolation features
- fully managed with autonomous control plane operation
## development %% fold %%
### docker support %% fold %%
- supports docker
- allows you to easily run/manage containers
### windows containers %% fold %%
- manages windows containers
- provides optimized AMIs for better performance and visibility
### AWS Copilot %% fold %%
- copilot CLI simplifies building, releasing, and operating containerized apps on ECS and Fargate
- offers monitoring, scaling, and automated testing
### repository compatibility
- works with 3rd party docker image repos like dockerhub and  [[compute-ECR|Amazon ECR]] 
## management %% fold %%
### task definitions  %% fold %%
- define tasks in JSON
	- specify containers, docker image, resource requirements, etc.
	- enables version control
### programmatic control %% fold %%
- simple API actions for 
	- cluster management
	- task registration
	- container operations
	- monitoring
- integration with [[monitoring-cloudwatch|AWS CloudWatch]]
### container deployments %% fold %%
- easily update containers to new versions
- ECS scheduler handles container registration/deregistration
### container auto-recovery %% fold %%
- ECS automatically recovers unhealthy containers to maintain desired container count
### capacity providers %% fold %%
- define rules for workload distribution on different compute capacity types
- works with [[compute-EC2-summary|EC2]] and [[compute-fargate|Fargate]] 
### storage %% fold %%
- [[storage-EFS|Amazon EFS]] links seamlessly with ECS and [[compute-fargate|Fargate]] for scalable, managed file storage
- no management required
## scheduling/task placement %% fold %% 
### scheduling strategies %% fold %%
- multiple strategies based on resource needs/availability
	- suitable for [[AWS Batch|batch jobs]], services, and daemons
### task scheduling %% fold %%
- starts tasks automatically from a queue/defined time intervals
	- ideal for [[AWS Batch|batch processing jobs]]
### service scheduling %% fold %%
- runs stateless services
- ensures a set number of tasks are always running
- performs health checks
### daemon scheduling %% fold %%
- automatically run the same task on each selected instance for common management functions
### task placement %% fold %%
- customize task placement based on attributes like [[compute-EC2-summary#instance types fold|instance types]], [[global infrastructure#Availability Zones fold| AZs]], or custom labels


--- 
# Resources
- [AWS ECS features page](https://aws.amazon.com/ecs/features/)
- [cheat sheet](https://tutorialsdojo.com/amazon-elastic-container-service-amazon-ecs/)
# Tags
- #aws-ccp-exam-notes/services/compute/container/ECS  
---