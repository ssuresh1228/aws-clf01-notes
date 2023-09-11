---
service: EKS - elastic kubernetes service
service-type: container
---

# EKS - elastic Kubernetes service

^1743b1

---
- **key points**:  ^19ca59
	- Fully managed service ^e5841c
	- allows you to run kubernetes on AWS without installing, operating, or maintaining your kubernetes control plane/nodes 
	- integrates with 
		- [[compute-ECR#^bef2f7|ECR]] for container images 
		- [[compute-ELB#^357633|elastic load balancing]] for load distribution 
		- [[security-identity-compliance-aws-iam#^ab9f15|IAM]] for authentication 
		- amazon VPC for isolation 
---
## Components %% fold %% 

^498fb4

### EKS control plane %% fold %% 
- runs Kubernetes software
- single tenant, unique, runs on EC2 instances
- distributed across AZs with an <mark style="background: #FF000094;">ELB Network Load balancer</mark>
- <mark style="background: #930083;">encrypted with AWS KMS</mark>
### EKS nodes %% fold %% 
- EC2 instances for running pods
- connect to control plane via API server
	- API endpoint is public by default
- supports Cluster autoscaler and Karpenter
- must be in the same VPC as cluster subnets
#### self managed nodes %% fold %%
- node groups with similar instance config
- 2 AMI update methods: migrate or update
#### managed node groups %% fold %%
- automated provisioning and lifecycle management
- auto-tagged for Kubernetes cluster autoscaler
- supports on-demand and spot instances
- automatic node updates/terminations

### Clusters %% fold %%
- EKS cluster = EKS Control Plane + EKS Nodes
- authentication: IAM/OIDC
- authorization: Kubernetes RBAC


---
## Storage %% fold %% 
- CSI (Container Storage Interface) enables 3rd party storage options
### Amazon EBS CSI Driver %% fold %%
- manages persistent volumes like EBS
- requires IAM permissions
- not for Fargate pods
#### EFS CSI Driver %% fold %%
- manages EFS file systems
- incompatible with Windows containers
- works with Fargate static provisioning
#### FSx CSI drivers %% fold %% 
- manage FSx file systems
- not for Fargate



## Networking
### VPC creation %% fold %%
- private subnets: 
	- cluster endpoint in VPC
	- 3 private subnets distributed across different AZs
- public subnets: 
	- public IP nodes + external endpoint
	- 3 public subnets distributed across different AZs
- public + private subnets: 
	- mixed; supports IPv6
	- each AZ has 1 private and public subnet
- <mark style="background: #0055FF;">cluster security group:</mark>
	- manages control plane communication
### Pod networking %% fold %%
- CNI (Container Network Interface) assigns private IPs to pods
- security groups control inbound/outbound traffic for pods
#### Other networking tools: %% fold %%
##### Load balancer controller %% fold %%
- manages AWS ELBs in Kubernetes cluster
##### CoreDNS %% fold %%
- DNS service for container discovery
- allows containers to discover and connect to other containers in the cluster


## Security %% fold %% 

- <mark style="background: #FF000094;">IAM users/roles need policies to modify EKS resources</mark>
- cluster creator gets automatic RBAC permissions
- service linked role is predefined by EKS for its components; includes permissions required to call other services
- specific IAM roles needed to create an EKS cluster
- <mark style="background: #930083;">use AWS Secrets and Configuration Provider (ASCP) to display secrets from AWS Secrets Manager and parameters from AWS Systems Manager Parameter Store as files in EKS pods</mark> 
## Monitoring %% fold %%
- <mark style="background: #00FF266B;">EKS control plane integrates with CloudWatch logs</mark>, including
	- API server
	- audit
	- authenticator
	- controller manager
	- scheduler logs
- <mark style="background: #930083;">Integrated with CloudTrail</mark>
	- all API calls are recorded as events
	- each event/log entry includes info on who initiated the request:
		- root/IAM user credentials
		- temporary security credentials for role/federated user
		- AWS service
## Pricing %% fold %%
- 

- EKS cluster creation has hourly charge
- EC2 resources in node groups is charged
- AWS Fargate charges for vCPU and memory
- no extra charge for nodes on AWS Outposts EC2
# References
- [cheat sheet](https://tutorialsdojo.com/amazon-elastic-kubernetes-service-eks/)
# Tags
- #aws-ccp-exam-notes/services/compute/container/EKS  
---