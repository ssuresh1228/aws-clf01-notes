
# EC2 overview key points %% fold %% 
---
- Description: summarizing key points of [[compute-EC2]], since it is too technical
---
- instances: server environments ^ac65c9
- Amazon Machine Images (AMIs): instance + OS + additional installations in a reusable template
## nitro system  %% fold %% 
- [[compute-EC2#AWS Nitro System fold|nitro system - detailed]] %% fold %%
- powers next-gen EC2 instances
- offloads hypervisor functions to dedicated hardware, reducing costs
	- nitro hypervisor offers performance like bare metal; outperforms Xen hypervisor
## instance types %% fold %%
- [[compute-EC2#Instance types fold|detailed instance types]]
- **<mark style="background: #FF000094;">general purpose:</mark>**
	- <mark style="background: #FF000094;">balanced CPU, memory, and network resources</mark>
	- suitable for a wide range of apps
		- **hosting a company website with moderate traffic and holds a database**
- <mark style="background: #930083;">compute optimized:</mark>
	- <mark style="background: #930083;">high CPU performance for compute-bound apps</mark>
		- **complex scientific simulations**
- <mark style="background: #0055FF;">memory optimized:</mark>
	- <mark style="background: #0055FF;">high memory-to-CPU ratio</mark>
	- ideal for memory-intensive tasks
		- hosting a large in-memory database
- <mark style="background: #00FF266B;">storage optimized:</mark>
	- <mark style="background: #00FF266B;">high storage capacity and fast disk performance</mark>
	- ideal for data-intensive apps
		- **storing/processing large volumes of data in a data warehousing ap**p
- <mark style="background: #6800FFBF;">accelerated computing:</mark>
	- instances with specialized hardware (GPUs) for ML and graphics processing
		- **training ML models**

---
## EC2 pricing %% fold %%
- **on-demand:** pay by the second with no commitments
- **dedicated host:** pay for dedicated physical hosts ^1fee9e
- **dedicated instances:** pay hourly for single tenant hardware ^f11da0
### On-demand capacity reservations: %% fold %% 
- reserve AZ capacity w/o long term commitment
- monitored with CloudWatch
### Reserved %% fold %%
- one time upfront payment + discounted hourly rate
#### Standard class %% fold %%
- highest discount
- limited modifications
- sellable
#### Convertible class  %% fold %%
- lower discount
- more modifications
- not sellable
### Spot instances %% fold %%

^ff0472

- request unused instances for up to 90% discount
- can be used/stopped/started at will when backed by EBS
#### spot blocks: %% fold %%
- continuous; ideal for finite tasks
#### spot fleet %% fold %%
- spot instance + on-demand instance hybrid
- used for maintaining target capacity
#### spot capacity %% fold %%
- set of unused instances with same configuration
## Additional charges %% fold %%
- data transfer costs from copying AMIs/instances between regions
- EBS pricing is separate from instance pricing
---
# References
- [[compute-EC2]]
# Tags
- aws-ccp-exam-notes//services/compute/EC2  
---