# AWS Lightsail
---
- **key insights:**
	- easy to use cloud resources
		- instances, containers, databases, storage, etc.
	- many preconfigured app blueprints for use
	- guided configuration in Lightsail console
---
## Lightsail %% fold %%
- easy to set up instances backed by AWS
- simple OS, app, or stack selection
- custom alarms for anomaly detection
## Containers %% fold %%
- easily run docker containers
- simplified container management
- infra handled by Lightsail
## Simplified load balancers %% fold %%
- routes web traffic for scalability/resilience
- integrated certification management for SSL/TLS
- easy certificate provisioning/renewal
## Managed databases %% fold %%
- fully configured MySQL/Postgres plans
- independent scaling from virtual servers/instances
- support for multi-tiered apps
## Block/object storage %% fold %%
- quick/scalable SSD storage
- static content hosting available
- CDN (cloud delivery network) distributions for global content delivery
## Upgrade to EC2 %% fold %%
- seamless migration to EC2 as your needs grow
- snapshot your lightsail instance and export to EC2
- use the *Upgrade to EC2* wizard
## AWS service access %% fold %%
- lightsail integrates with 90+ AWS services via Amazon VPC peering
- manage AWS services in AWS management console
- day-to-day management in lightsail console
## Pricing %% fold %% 
- no charge for attached static IP
- <mark style="background: #FF000094;">instances</mark> billed when running/stopped
- **cost based on virtual server/instance package**
	- windows costs more
- additional charges for outbound data past package cap
- highly available managed <mark style="background: #930083;">databases</mark> cost double package price
- <mark style="background: #0055FF;">load balancers</mark> have fixed monthly fee
	- doesn't consume data transfer allowance
- extra <mark style="background: #00FF266B;">EBS SSD storage</mark> available for $0.10/GB/month
- point in time <mark style="background: #6800FFBF;">snapshots</mark> cost $0.05/GB/month
### included in all plans: %% fold %%
- static IP
- management console
- DNS management
- SSH access 
- RDP access (windows)
- API
- SSD storage
- server monitoring
## Limits per account %% fold %% 
- 20 instances
- 5 static IPs
- 3 DNS zones
- 20TB block storage
- 5 load balancers
- 20 certificates/year
---
# References
- [Lightsail Features](https://aws.amazon.com/lightsail/features/)
# Tags
- #aws-ccp-exam-notes/services/compute/lightsail   
---