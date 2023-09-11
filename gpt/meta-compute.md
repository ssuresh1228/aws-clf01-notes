---
gpt-meta: "aws ccp: compute services"
---
# meta summary: AWS compute
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	- [[summary-compute]]
---
## EC2: 
- Scalable cloud service for on-demand VM provisioning. 
- Offers optimized instance types, secure login, storage volumes
- pricing based on instance type.
## EC2 autoscaling: 
- Automatically scales EC2 instances based on demand metrics. 
- Supports on-demand and spot instances.
- pricing varies based on instance type used
## AWS Batch: 
- Fully managed service for batch (extremely high) computing tasks. 
- Automates infrastructure management and supports containerized applications.
- Pay for the resources created to store and run the applications.
## AWS Lightsail: 
- Easy-to-use cloud resources for instances, containers, databases, storage, etc. Offers preconfigured app blueprints.
- Running/stopped instances are billed based on the virtual server package
- extra charges for outbound data exceeding the package limit.
## Amazon WorkSpaces: 
- Fully managed, secure cloud desktop service. 
- Provides persistent desktops, user customization, and admin control.
- Bundle type, WorkSpaces number affect cost, monthly/hourly billing, 
- monthly fixed fee for unlimited usage, hourly rate with small monthly fee for hourly billing.
## EKS - Elastic Kubernetes Service: 
- Fully managed Kubernetes service for container orchestration. 
- Runs on EC2 instances.
## AWS ECS: 
- Managed docker container orchestration. 
- Seamlessly integrates with AWS services and provides strong security features.
## Amazon ECR: 
- Store and manage Docker/OCI container images securely. Supports private repositories.
## Amazon Fargate: 
- Managed service for container cluster management. Launch containers without managing EC2 instances.
## AWS Lambda:
- Serverless compute service for executing code on demand. 
- Pay-as-you-go pricing based on code execution time.
## Amazon ELB:
- Automatically distributes incoming app traffic across targets.
- Supports classic, application, and network load balancers.
## AWS Savings Plan: 
- Cost-saving model for EC2, Fargate, and Lambda instances. 
- Offers up to 66% savings and flexibility in workload migration.
## AWS Elastic Beanstalk: 
- Easily deploy and manage AWS applications. 
- Automated management of capacity, load balancing, and scaling.
# tags:
- #gpt-meta/aws-ccp/compute