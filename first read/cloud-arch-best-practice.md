
# Cloud Architecture Best Practices
---

---
## Design for failure %% fold %% 
- avoid single points of failure
- assume everything fails, and design backwards
- **Goal:**
	- Apps should continue to work even if underlying physical hardware is removed/replaced 
### Tools  %% fold %%
- use fault-tolerant services in your app
- use EBS (Elastic Block Store) snapshots
- Autoscaling for autorecovery
- on-demand app provisioning in a different AZ (Availability Zone)
- **multi-AZ app deployment and data replication**
## Loose Coupling  %% fold %%
- build components with minimal dependencies on each other
- if one component fails, the rest should still work
	- reduces inter-component reliance
- Service Oriented Architecture (SOA) supports this approach:
	- the more loosely coupled components are, the better and more stably it scales
## Implement Elasticity %% fold %%
- implemented by automating deployment and optimizing config and build process of architecture
- ensures system can scale in/out to meet demand without manual intervention
## Build Security in every Layer %% fold %%
- AWS can monitor config changes to your IT resources
- since AWS assets are programmable, your security policy can be formalized and embedded with your infra's design
## Think parallel %% fold %%
- implement parallelization
## Use different storage options  %% fold %% 
- S3: large static objects
- CloudFront: content distribution
- SimpleDB: simple data indexing/querying
- EC2 local disc drive: transient data
- EBS: persistent storage for any RDBMS + Snapshots on S3
- RDS: RDBMS service: automated and managed MySQL



---
# References
- [Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/?wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc&wa-guidance-whitepapers.sort-by=item.additionalFields.sortDate&wa-guidance-whitepapers.sort-order=desc)
# Tags
- aws-ccp-exam-notes//cloud-arch-best-practices 
---