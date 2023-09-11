---
gpt-summary: "aws ccp: cloud concepts"
---
# Overview
--- 
- note(s) summarized: 
	- [[cloud-computing-concepts]]  
	- [[cloud-adoption-framework]]  
	- [[aws-well-architected-pillars]] 
	- [[disaster-recovery]] 
	- [[global infrastructure]]
	- [[reserved-instance-discount]] 
---
- **table of contents:**
	- [[#Cloud Computing Concepts|Cloud Computing Concepts]]
	- [[#Cloud Adoption Framework|Cloud Adoption Framework]]
	- [[#AWS Well-Architected|AWS Well-Architected]]
	- [[#Disaster Recovery|Disaster Recovery]]
	- [[#Global Infrastructure|Global Infrastructure]]
	- [[#Reserved Instances/Discount|Reserved Instances/Discount]]
--- 
## Cloud Computing Concepts
- IaaS: basic building blocks for cloud IT
- PaaS: removes need for managing underlying infrastructure
- SaaS: provides a completed product that is run and managed by service provider

## Cloud Adoption Framework
- Framework provided by AWS to aid enterprise cloud adoption
- Different perspectives: 
	- <mark style="background: #FF000094;">business</mark>: drives cloud investments for transformation
	- <mark style="background: #930083;">people</mark>: focus on culture, leadership, and workforce
	- <mark style="background: #0055FF;">governance</mark>: manages benefits and risk control
	- <mark style="background: #00FF266B;">platform</mark>: builds hybrid cloud/deploys solutions
	- <mark style="background: #6800FFBF;">security</mark>: ensures data/workload security
	- <mark style="background: #FF5700AB;">operations</mark>: align cloud services with business needs 

## AWS Well-Architected
- <mark style="background: #FF000094;">Operational Excellence:</mark> 
	- Efficiently run and monitor systems, continuously improve processes.
- <mark style="background: #930083;">Security: </mark>
	- Protect information, systems, and assets, ensure data confidentiality, integrity, and availability.
- <mark style="background: #0055FF;">Reliability: </mark>
	- Recover from disruptions, dynamically scale resources, mitigate failures.
- <mark style="background: #00FF266B;">Performance Efficiency: </mark>
	- Optimize resource usage, meet system requirements efficiently.
- <mark style="background: #6800FFBF;">Cost Optimization: </mark>
	- Avoid unnecessary costs, optimize spending, maximize IT investment value.
- <mark style="background: #FF5700AB;">Sustainability: </mark>
	- Minimize environmental impact, maximize efficiency, reduce waste.

## Disaster Recovery
- Backup and restore: 
	- store backup data on S3 for quick restoration
- Pilot light: 
	- core pieces of the system are already running and kept up to date
- Warm standby solution: 
	- scaled down version of fully functional environment is always running
- Multi-site solution: 
	- run infrastructure on another site in an active configuration

## Global Infrastructure
- Regions: physical location where AWS has datacenters
- Availability Zones: logical zones made up of one or more data centers
- Edge locations: sites used by AWS CloudFront to cache content for faster delivery

## Reserved Instances/Discount
- Reserved instances offered with up to 75% discount
- Larger upfront payment = greater discount
--- 
# tags
- #gpt-summary/aws-ccp/cloud-concepts 

