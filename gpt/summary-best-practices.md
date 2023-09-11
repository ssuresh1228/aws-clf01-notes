---
gpt-summary: "aws ccp: cloud concepts"
---
# GPT summary: cloud concepts
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	-  [[AWS-overview-best-practices]]
--- 
## global infrastructure 
- <span style='color:#eb3b5a'>Regions</span>:
	- AWS datacenters physical location. 
	- Choose based on user location for less latency. 
	- Multiple regions for disaster recovery. 
	- Host services in 1+ regions to avoid localized disasters. 
	- 1 region includes 2+ availability zones. 
	- Regions isolated, data movement needs configuration.
- <span style='color:#20bf6b'>Availability Zones</span>:
	- Logical zone, 1 or more data centers
	- Each AZ highly available
	- Datacenters in AZ locally separated, close, connected with high speed networking
	- Prevent disasters affecting both, usually less than 100km/60mi apart
- <span style='color:#2d98da'>Edge locations:</span>
	- AWS CloudFront site, caches content copies for faster delivery
	- Edge computing options available
	- Perform data processing at edge locations, minimize latency, reduce compute overhead on backend systems
## disaster recovery
- <span style='color:#eb3b5a'>Backup and Restore</span>: Quick restore, store backup data on S3 
- <span style='color:#fa8231'>Pilot Light</span>: Faster recovery, core system components already running, kept updated 
- <span style='color:#f7b731'>Warm Standby</span>: Always-on, scaled down version of environment in cloud 
- <span style='color:#20bf6b'>Multi-site</span>: Active infrastructure on another site, use multiple AZs
## cloud adoption framework (CAF)
- <span style='color:#eb3b5a'>Function</span>: identify, prioritize transformation opportunities; evaluate, enhance cloud readiness; iterate on transformation/migration roadmap: 
	- <span style='color:#f7b731'>Business</span>: aims for digital transformation, business goals
	- <span style='color:#fa8231'>People</span>: links tech, business for quick cultural growth
	- <span style='color:#20bf6b'>Platform</span>: builds hybrid cloud, modernizes workloads, deploys cloud-native solutions
	- <span style='color:#0fb9b1'>Governance</span>: controls cloud efforts for benefits, risk management
	- <span style='color:#2d98da'>Security</span>: guarantees data, workload security
	- <span style='color:#3867d6'>Operations</span>: matches cloud services to business needs
		- Each perspective: owned/managed by stakeholders in cloud migration
## well architected
- Operational Excellence:
	- Code-based operations
	- Regular, minor, reversible adjustments
	- Regular operation procedure refinement
	- Failure anticipation
	- Learn from operational mishaps

- Security:
	- Identity foundation strength
	- Traceability enabled
	- All-layer security application
	- Data protection in transit/rest
	- Security event preparation
	- Pre-design security practices
	- System security/incident response readiness
	- AWS Shared Responsibility Model

- Reliability:
	- Ensure consistent and correct workload functioning
	- Establish essential foundational requirements
	- Follow specific design patterns
	- Anticipate workload changes
	- Implement workload resiliency
	- Collect comprehensive architecture data
	- Regularly assess choices

- Performance Efficiency:
	- Monitor and detect performance deviations
	- Enhance performance with architecture adjustments
	- Relax consistency requirements for improved performance
	- Implement cloud financial management
	- Adapt a consumption model
	- Measure overall efficiency
	- Stop spending money on undifferentiated heavy lifting
	- Analyze and attribute spending
	- Evaluate trade-offs
	- Optimize workloads for cost savings
	- Understand long-term impact

- Cost Optimization:
	- Establish sustainability goals
	- Maximize utilization
	- Anticipate and adapt new offerings
	- Use managed services
	- Reduce downstream impact
	- Choose AWS regions aligned with goals
	- Analyze user patterns to optimize resource use
	- Implement load balancing patterns
	- Automate development lifecycle and testing

---
# tags:
- #gpt-summary/aws-ccp/cloud-concepts 