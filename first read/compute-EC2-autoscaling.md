---
service: EC2 Autoscaling
service-type: compute
---

# EC2 autoscaling
---
## Overview %% fold %% 
- logical collection of EC2 instances for automatic scaling based on demand metrics
- maintains desired instance count via health checks
	- if an instance is unhealthy, it is replaced
- scaling policies adjust instance count based on conditions
- can use on-demand, spot instances, and both
	- spot instances are cheaper but have variable prices
- Autoscaling tries to replace terminated Spot instances
- Desired capacity can be distributed across AZs
## Simple Scaling  %% fold %%
- relies on CloudWatch alarms and thresholds for scaling
	- "set a CPU utilization threshold of 80%" (and scale when hitting this)
- adds/removes instances based on defined thresholds
- limited fine-grained control
## Target Tracking Policy %% fold %%
- specifies a metric and target value for the autoscaling group
	- "maintain average CPU utilization at 80%"
- scale up when metric is above the target value
- scale down more gradually to avoid sudden capacity drops/maintain stability


---
# References
- [scaling policies](https://tutorialsdojo.com/step-scaling-vs-simple-scaling-policies-in-amazon-ec2/)
# Tags
- #aws-ccp-exam-notes/services/compute/capacity-management/EC2-autoscaling   
---