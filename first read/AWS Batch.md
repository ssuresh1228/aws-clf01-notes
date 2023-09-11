---
service: AWS Batch
service-type: compute
---

# AWS Batch
---
- key insights: 
	- fully managed
	- streamlines batch computing, offering devs, scientists, and engineers access to extensive computing resources.
	- automates infra management for efficient resource allocation
	- reduces costs and delivers rapid results for large-scale computing tasks
---
## Components %% fold %%
### Jobs %% fold %%
- units of work
- run as containerized apps on [[compute-fargate|AWS Fargate]] or [[compute-EC2|EC2]]
- jobs can reference/depend on other jobs by name/ID
### job definitions %% fold %%
- blueprints for job resources
- specify CPU, IAM roles, etc.
- specifications in a job definition can be overridden when individual jobs are submitted  
### job queues %% fold %%
- used for job scheduling
- jobs wait in queues until scheduled to a compute environment
- queues can have priority values
	- jobs can be assigned to different queues based on importance/resource needs
### compute environments %% fold %%
- resource set for running the jobs 
- managed environments allow to specify:
	- compute type
	- instance type
	- vCPU limits
	- pricing preferences
	- etc.
- AWS Batch efficiently handles launching/managing/terminating compute resources as required
- users can manage their own compute environments too:
	- set up
	- specify scaling
## Pricing %% fold %%
- no additional charge
- pay for resources you create to store/run your app
---
# References
- [cheat sheet](https://tutorialsdojo.com/aws-batch/)
- [AWS Batch user guide](https://docs.aws.amazon.com/batch/latest/userguide/what-is-batch.html)
# Tags 
- #aws-ccp-exam-notes/services/compute/batch 
---