---
gpt-summary: "aws ccp: networking"
gpt-3.5:
---
# GPT summary: networking 
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	-  [[networking-overview]]
- 
--- 
## Amazon API Gateway %% fold %% 
### use case: %% fold %% 
- Create, manage, and secure APIs
### overview: %% fold %% 
- Exposes backend services through RESTful API
- Part of AWS serverless infrastructure
### pricing: %% fold %% 
- Pay for API calls and data transfer
## AWS CloudFront %% fold %% 
### use case: %% fold %% 
- Distributing content globally for optimal performance
### overview: %% fold %% 
- Content is distributed via a global network of data centers called edge locations
- Users are directed to the fastest edge location for optimal performance
- Content is delivered instantly if it's already in the edge location, otherwise it's fetched from the specified origin
### pricing: %% fold %% 
- Costs for 
	- storing data in S3 bucket, 
	- data transfer to/from users and origin
	- making HTTP/HTTPS requests, 
	- invalidating old data, and 
	- using special security certificates
- Additional charges for secure requests and requests with special encryption
## Amazon VPC:  %% fold %% 
### use case:  %% fold %% 
- Create a virtual network in the cloud for launching AWS resources.
### overview:  %% fold %% 
- Virtual network in the cloud for your AWS account.
- Networking layer for EC2 instances.
### pricing:  %% fold %% 
- Billed for VPN and NAT Gateway hours.
- Fees for NAT Gateway data processing.
- Standard AWS data transfer charges apply.

## Amazon Route 53 %% fold %% 
### use case: %% fold %% 
- Highly available and scalable DNS for domain registration, routing, and health checking.
### overview: %% fold %% 
- Highly available and scalable DNS service.
- Translates website names into IPs.
- Routes users to internet applications.
### pricing: %% fold %% 
- Hosted zone charged at creation then monthly - No charge if deleted within 12 hours.
- Billion queries/month.
- No extra cost for Alias queries to certain AWS resources.
- Traffic flow policy record/month.
- Domain name pricing varies.
## AWS Direct Connect:  %% fold %% 
### use case:  %% fold %% 
- Transferring large datasets
- Developing/using apps with real-time data feeds
### overview:  %% fold %% 
- Dedicated network connection from your premises to AWS
- Links network to Direct Connect via Ethernet fiber-optic cable
- Allows creation of virtual interfaces to AWS services or VPC
- Supports hosted connection capacities of 1, 2, 5, and 10 Gbps
- IAM to control access
### pricing:  %% fold %% 
- Pay only for network ports used and data transferred over the connection
- Cost is based on port type + usage
- Data transfer out is charged per GB
- Data transfer IN is free in all locations.
# tags:
- #gpt-summary/