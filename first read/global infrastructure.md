
# global infrastructure
---
**Table of Contents**
- [[#Regions, availability zones, and edge locations %% fold %%|Regions, availability zones, and edge locations %% fold %%]]
	- [[#Regions, availability zones, and edge locations %% fold %%#Regions %% fold %%|Regions %% fold %%]]
	- [[#Regions, availability zones, and edge locations %% fold %%#Availability Zones %% fold %%|Availability Zones %% fold %%]]
	- [[#Regions, availability zones, and edge locations %% fold %%#Edge locations %% fold %%|Edge locations %% fold %%]]
- [[#Relations between regions, AZs, and edge locations %% fold %%|Relations between regions, AZs, and edge locations %% fold %%]]
	- [[#Relations between regions, AZs, and edge locations %% fold %%#Regions %% fold %%|Regions %% fold %%]]
	- [[#Relations between regions, AZs, and edge locations %% fold %%#Availability Zones %% fold %%|Availability Zones %% fold %%]]
	- [[#Relations between regions, AZs, and edge locations %% fold %%#Edge Locations %% fold %%|Edge Locations %% fold %%]]
		- [[#Edge Locations %% fold %%#Content caching %% fold %%|Content caching %% fold %%]]
		- [[#Edge Locations %% fold %%#Amazon CloudFront %% fold %%|Amazon CloudFront %% fold %%]]
		- [[#Edge Locations %% fold %%#Optimized Delivery %% fold %%|Optimized Delivery %% fold %%]]
		- [[#Edge Locations %% fold %%#Route 53 and DNS %% fold %%|Route 53 and DNS %% fold %%]]
		- [[#Edge Locations %% fold %%#End user advantage %% fold %%|End user advantage %% fold %%]]
		- [[#Edge Locations %% fold %%#AWS Global Accelerator %% fold %%|AWS Global Accelerator %% fold %%]]
		- [[#Edge Locations %% fold %%#CloudFront vs Global Accelerator %% fold %%|CloudFront vs Global Accelerator %% fold %%]]
			- [[#CloudFront vs Global Accelerator %% fold %%#IP addresses %% fold %%|IP addresses %% fold %%]]
			- [[#CloudFront vs Global Accelerator %% fold %%#Pricing %% fold %%|Pricing %% fold %%]]
			- [[#CloudFront vs Global Accelerator %% fold %%#Caching/Routing %% fold %%|Caching/Routing %% fold %%]]
			- [[#CloudFront vs Global Accelerator %% fold %%#Protocols %% fold %%|Protocols %% fold %%]]
- [[#When to consider using multiple regions %% fold %%|When to consider using multiple regions %% fold %%]]
---
## Regions, availability zones, and edge locations %% fold %% 
### Regions %% fold %%
- physical location where AWS has datacenters available to operate your workloads on
- can pick a global location to host your services based on where your users are located to minimize latency
- many regions allows for flexible disaster recovery options
	- can host your services on more than 1 region to avoid localized disasters at 1 data center
- **1 region contains at least 2 availability zones**
- regions are isolated containers
	- by default, your data is isolated in a region; doesn't move across regions unless you specifically configure it to do so
### Availability Zones %% fold %%
- logical zone **made up of 1 or more data centers**
	- this design makes each AZ highly available
	- datacenters making up an AZ are locally separated but still relatively close to each other
		- connected with high speed networking to minimize latency b/w them
		- far enough apart to prevent disasters from affecting both
		- usually less than 100km/60mi apart
### Edge locations %% fold %%
- a site that [[networking-aws-cloudfront#^00eb30|AWS Cloudfront]] uses to cache copies of your content for faster delivery to users at any location
- edge computing options are also available
	- can perform data processing at these edge locations (closer to end users) to minimize latency and offload compute functions to reduce compute overhead on backend systems
## Relations between regions, AZs, and edge locations %% fold %% 
### Regions %% fold %% 
- a region has at least 2 AZs
	- all regions are connected via high speed networks
	- regions are isolated from each other:
		- no data can go in/out of a region unless configured to do so
### Availability Zones %% fold %% 
- an AZ has 1 or more datacenter
	- datacenters are separated but still relatively close
	- separated in case of disasters
	- AZs *never* share a single point of failure
- having multiple AZs in a region ensures higher availability, fault tolerance, and scalability compared to a single datacenter
### Edge Locations %% fold %%
- separate from AWS regions
- crucial role in speeding up data access
#### Content caching %% fold %%
- if clients in Mumbai need data from Tokyo region, instead of making them wait for data to travel from Tokyo to Mumbai, just create local copies of the data in Mumbai
- achieved through CDNs (Content Delivery Networks)
#### Amazon CloudFront %% fold %%
- delivers various types of content to customers worldwide
- designed to offer quick access to customers worldwide
- uses Edge Locations for faster data access and delivery
#### Optimized Delivery %% fold %%
- send data from AWS regions to edge locations for faster content delivery
#### Route 53 and DNS %% fold %% 
- edge locations run route 53 to run domain names for seamless and fast customer redirection 
#### End user advantage %% fold %% 
- edge locations are primarily used by end-users, people who actually use your services
- taking advantage of AWS distributed infrastructure makes your services faster and improves access for users worldwide
#### AWS Global Accelerator %% fold %% 
- enhances app performance for local/global users via accelerators
- standard accelerator:
	- improves availability for global users by directing traffic over AWS global network to nearest region endpoints
- custom routing accelerator:
	- maps users to specific destinations among multiple choices
- standard accelerator routing:
	- uses AWS global network to route traffic optimally based on health, location, and configured policies
#### CloudFront vs Global Accelerator %% fold %% 
##### IP addresses %% fold %% 
- CloudFront uses multiple dynamic IP addresses
- Global Accelerator gives you a fixed set of IP addresses
##### Pricing %% fold %%
- CloudFront charges based on how much data you send/requests made
- Global Accelerator charges a fixed hourly rate + extra based on data transfer
##### Caching/Routing %% fold %%
- CloudFront uses Edge Locations to cache content
- Global Accelerator uses Edge Locations to find the best way to reach nearby servers
##### Protocols %% fold %% 
- CloudFront: HTTP
- Global Accelerator: HTTP, TCP, UDP
## When to consider using multiple regions %% fold %% 
- expanding an app to multiple regions increases cost b/c of region isolation 
	- isolation maintains region autonomy
- AWS regions have strong isolation but need special care to prevent correlated failures across them

![[AWS-Regions-and-Availability-Zones.jpg]]

---
# References
- [AWS CloudFront Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)
- [Multi-Region Scenarios - Well Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/multi-region-scenarios.html)
- [5 reasons to build multi-region app architecture](https://www.cockroachlabs.com/blog/5-reasons-to-build-multi-region-application-architecture/)
- [AWS Global Accelerator docs](https://docs.aws.amazon.com/global-accelerator/latest/dg/what-is-global-accelerator.html)
- [CloudFront vs Global Accelerator](https://tutorialsdojo.com/aws-global-accelerator-vs-amazon-cloudfront/)
# Tags
- #aws-ccp-exam-notes/overview/global-infra  
- ---