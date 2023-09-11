---
gpt-meta: "aws ccp: best practices"
---
# Title
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	-  [[summary-best-practices]]
--- 
- **AWS global infrastructure:**
	- Regions are physical locations for datacenters. 
	- Choose based on user location for less latency. 
	- Multiple regions for disaster recovery. 
	- Each region includes 2+ availability zones (AZs) which are logical zones with highly available datacenters.
- **Edge locations:** 
	- AWS CloudFront sites that cache content copies for faster delivery. 
	- Can perform data processing at edge locations to minimize latency and reduce compute overhead on backend systems.
- **Disaster recovery options:**
	- Backup and Restore for quick restore by storing backup data on S3. 
	- Pilot Light for faster recovery with core system components already running. 
	- Warm Standby for an always-on, scaled down version of the environment in the cloud. 
	- Multi-site for active infrastructure on another site using multiple AZs.
- **Cloud Adoption Framework (CAF):**
	- Function includes identifying and prioritizing transformation opportunities, evaluating and enhancing cloud readiness, and iterating on transformation/migration roadmap. Perspectives include Business, People, Platform, Governance, Security, and Operations.
- **Well-Architected Framework:**
	- Focuses on Operational Excellence, Security, Reliability, Performance Efficiency, and Cost Optimization. Each area has specific principles and best practices to follow.

---
# tags:
- #gpt-meta/aws-ccp/best-practices