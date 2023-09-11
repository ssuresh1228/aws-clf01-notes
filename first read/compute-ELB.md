---
service: ELB - elastic load balancer
service-type: load balancer
---

# Amazon ELB: Elastic Load Balancer
---
- **key insights:**  ^357633
	- automatically distributes incoming app traffic across targets
		- EC2 instances, containers, and IP addresses
	- High Availability
		- achieved by distributing traffic evenly and routing it away from unhealthy targets
--- 
- <mark style="background: #FF000094;">classic load balancer</mark>
	- balances at request/connection level for [[compute-EC2-summary#EC2 overview key points fold|EC2 instances]]
- <mark style="background: #930083;">application load balancer</mark>
	- advanced routing based on content, host, path, etc.
- <mark style="background: #0055FF;">network load balancer</mark>
	- handles traffic with ultra-low latencies at the transport layer
- integrates with [[compute-EC2-autoscaling#Overview fold|AWS autoscaling]] for resource scaling 

- <mark style="background: #6800FFBF;">key features</mark>
	- <mark style="background: #FF5700AB;">security:</mark>
		- security groups in VPC for load balancers
			- internet-facing/internal options
	- <mark style="background: #FF5700AB;">high availability:</mark>
		- distributes traffic across EC2 instances in multiple [[global infrastructure#Availability Zones fold|AZs]] 
		- auto scales, and performs health checks
	- <mark style="background: #FF5700AB;">supports sticky sessions:</mark>
		- mechanism to route requests from the same client to the same target
	- <mark style="background: #FF5700AB;">monitoring/logging:</mark>
		- [[monitoring-cloudwatch|CloudWatch]] reports metrics
		- integrates with [[monitoring-CloudTrail 1|CloudTrail]] for API call tracking
	- <mark style="background: #FF5700AB;">deletion protection:</mark>
		- can enable deletion protection to prevent accidental deletion
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-elastic-load-balancing-elb/)
- [ELB features](https://aws.amazon.com/elasticloadbalancing/features/)
# Tags
- #aws-ccp-exam-notes/services/compute/capacity-management/ELB  
---