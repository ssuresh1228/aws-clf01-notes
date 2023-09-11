---
gpt-summary: "aws ccp: compute services"
---
- [[#EC2  %% fold %%|EC2  %% fold %%]]
- [[#EC2 autoscaling  %% fold %%|EC2 autoscaling  %% fold %%]]
- [[#AWS Batch %% fold %%|AWS Batch %% fold %%]]
- [[#AWS Lightsail %% fold %%|AWS Lightsail %% fold %%]]
- [[#Amazon WorkSpaces: %% fold %%|Amazon WorkSpaces: %% fold %%]]
- [[#EKS - Elastic Kubernetes Service: %% fold %%|EKS - Elastic Kubernetes Service: %% fold %%]]
- [[#AWS ECS: Elastic Container Service %% fold %%|AWS ECS: Elastic Container Service %% fold %%]]
- [[#Amazon ECR: Elastic Container Registry %% fold %%|Amazon ECR: Elastic Container Registry %% fold %%]]
- [[#Amazon Fargate: %% fold %%|Amazon Fargate: %% fold %%]]
- [[#AWS Lambda: %% fold %%|AWS Lambda: %% fold %%]]
- [[#Amazon ELB: Elastic Load Balancer %% fold %%|Amazon ELB: Elastic Load Balancer %% fold %%]]
- [[#AWS Savings Plan: %% fold %%|AWS Savings Plan: %% fold %%]]
- [[#AWS Elastic Beanstalk: %% fold %%|AWS Elastic Beanstalk: %% fold %%]]]]
# summary: AWS compute services
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	- [[compute-overview]]
--- 
# Compute services:
## EC2  %% fold %% 
### use case: %% fold %% 
- Provision Linux/Mac/Windows VMs on-demand
### overview:  %% fold %% 
- EC2 is a scalable cloud service for on-demand VM provisioning.
- Offers optimized instance types for different use cases.
- Features include secure login, storage volumes, elastic IP addresses, tags, and VPCs.
- Supports hibernation, hardware modification, and volume attachment.
- Start, stop, hibernate instances, replace root volumes.
- AMIs used as instance templates.
- Pricing options: on-demand, reserved, spot instances.
### pricing: %% fold %% 
- On-demand: Pay by the second, no commitments.
- Reserved: Upfront payment, discounted hourly rate.
- Spot: Request unused instances, up to 90% discount.
## EC2 autoscaling  %% fold %% 
### use case:  %% fold %% 
- automatically scale a collection of EC2 instances based on demand metrics
### overview:  %% fold %% 
- logical collection of EC2 instances for automatic scaling
- maintains desired instance count via health checks
- scaling policies adjust instance count based on conditions
- supports on-demand and spot instances
- replaces terminated Spot instances
- desired capacity can be distributed across AZs
### pricing:  %% fold %% 
- pricing varies based on the type of EC2 instances used
## AWS Batch %% fold %% 
### use case: %% fold %% 
- Streamlining batch computing tasks for developers, scientists, and engineers.
### overview: %% fold %% 
- Fully managed service that automates infrastructure management for efficient resource allocation.
- Allows running containerized applications as jobs on AWS Fargate or EC2.
- Job definitions specify CPU, IAM roles, etc., and can be overridden when submitting individual jobs.
- Job queues are used for scheduling and prioritizing jobs.
- Compute environments specify compute type, instance type, vCPU limits, pricing preferences, etc.
- AWS Batch handles launching, managing, and terminating compute resources as required.
### pricing: %% fold %% 
- No additional charge for AWS Batch.
- Pay for the resources created to store and run the applications.
## AWS Lightsail %% fold %% 
### use case:  %% fold %% 
- Easy to use cloud resources for instances, containers, databases, storage, etc.
- Many preconfigured app blueprints for use.
### overview:  %% fold %% 
- Easy setup of instances backed by AWS.
- Simplified container management with infra handled by Lightsail.
### pricing:  %% fold %% 
- Instances billed when running/stopped.
- Cost based on virtual server/instance package.
- Additional charges for outbound data past package cap.
## Amazon WorkSpaces: %% fold %% 
### use case: 
- Fully managed, secure cloud desktop service
### overview: 
- Fully managed, secure cloud desktop service
- Provides persistent desktops with variable storage
- Supports different bundles based on user needs
- Provides user customization and admin control
- Offers regular backups to S3
- Supports Amazon WorkDocs Drive
- Allows image sharing across AWS accounts
- Requires users to exist in a directory for provisioning
- Volume sizes cannot be increased after launch
### pricing: 
- Based on bundle type and number of WorkSpaces launched
- Offers monthly or hourly billing options
- Monthly billing: fixed fee for unlimited usage
- Hourly billing: small fixed monthly fee + hourly usage rate
## EKS - Elastic Kubernetes Service: %% fold %% 
### use case:  %% fold %% 
- Fully managed Kubernetes service for container orchestration.
### overview:  %% fold %% 
- EKS control plane runs Kubernetes software on EC2 instances.
- EKS nodes are EC2 instances for running pods.
### pricing:  %% fold %% 
- Hourly charge for EKS cluster creation.
- EC2 resources in node groups are charged.
- AWS Fargate charges for vCPU and memory.
## AWS ECS: Elastic Container Service %% fold %% 
### use case:  %% fold %% 
- Managed docker container orchestration
- Deploying, managing, and scaling containers
### overview: %% fold %% 
- Managed service for deploying, managing, and scaling containers
- Seamlessly integrates with AWS services
- Supports EC2, Fargate, and on-premises with ECS anywhere
- Provides strong security and isolation features
- Fully managed with autonomous control plane operation
### pricing: %% fold %% 
- Pay for the resources (EC2 instances or Fargate tasks) used to run containers
- Additional charges for data transfer and other AWS resources used in conjunction with ECS
## Amazon ECR: Elastic Container Registry %% fold %% 
### use case:  %% fold %% 
- Store and manage Docker/OCI container images securely
### overview:  %% fold %% 
- AWS managed container image registry
- Scalable, reliable, and secure
- Supports private repositories with IAM permissions
- Push, pull, and manage Docker/OCI images using CLI
### pricing:  %% fold %% 
- Pay only for the amount of data stored in repositories and transferred data to the internet
## Amazon Fargate: %% fold %% 
### use case: %% fold %%
- Launch containers without managing EC2 instances
### overview: %% fold %%
- Managed service for container cluster management
- Serverless compute engine for containers
### pricing: %% fold %%
- Pay for the amount of vCPU/memory resources used by containerized apps
## AWS Lambda: %% fold %% 
### use case:  %% fold %% 
- Serverless compute service for executing code on demand and scaling automatically.
### overview:  %% fold %% 
- Serverless compute service that executes code only when needed and scales automatically.
- Pay-as-you-go pricing model, where you only pay for code execution time.
### pricing:  %% fold %% 
- Pay-as-you-go pricing based on code execution time.
## Amazon ELB: Elastic Load Balancer %% fold %% 
### use case:  %% fold %% 
- automatically distributes incoming app traffic across targets (EC2 instances, containers, and IP addresses)
- achieves high availability by distributing traffic evenly and routing it away from unhealthy targets
### overview:  %% fold %% 
- classic load balancer balances at request/connection level for EC2 instances
- application load balancer provides advanced routing based on content, host, path, etc.
- network load balancer handles traffic with ultra-low latencies at the transport layer
- integrates with AWS autoscaling for resource scaling
### pricing:  %% fold %% 
- pricing varies based on the type of load balancer and the amount of data processed
## AWS Savings Plan: %% fold %% 
### use case:  %% fold %% 
- Cost-saving model for EC2, Fargate, and Lambda instances
### overview:  %% fold %% 
- Offers up to 66% savings on EC2, Fargate, and Lambda instances
- Automatically applies to EC2 instances regardless of instance type
- Allows flexibility to move workloads between different instance families, regions, or migrate to ECS using Fargate while maintaining the discount
### pricing:  %% fold %% 
- All Upfront: Pay the entire savings plan amount upfront get max discount.
- Partial Upfront: Pay a portion of the savings plan amount upfront get a lower discount 
- No Upfront: Pay nothing upfront but commit to a specific usage amount
- Savings plan rates vary based on the term length (1 or 3 years) and the payment option chosen.
## AWS Elastic Beanstalk: %% fold %% 
### use case:  %% fold %% 
- Easily deploy and manage AWS applications.
### overview:  %% fold %% 
- Automated management of capacity, load balancing, scaling, and health monitoring.
- Platform as a Service (PaaS) for app development without infrastructure concerns.
### pricing:  %% fold %% 
- No cost for Elastic Beanstalk itself, only pay for underlying infrastructure use.

---
# tags:
- #gpt-summary/aws-ccp/compute