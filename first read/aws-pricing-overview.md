---
aws-cost: billing services overview
---

- **3 fundamental drivers of cost**:
	- [[meta-compute|compute]]
	- [[meta-storage|storage]]
	- outbound data transfer 
- AWS has pay-as-you-go pricing 
- **reserved capacity**
	- can buy reserved instances in [[compute-EC2#reserved fold|EC2]], [[database-RDS#^5a198f|RDS]], and [Amazon EMR](https://tutorialsdojo.com/amazon-emr/) 
	- can save up to 75% over equivalent on-demand capacity
		- **all upfront**
			- pay for the entire Reserved Instance term with one upfront payment
			- largest discount compared to On-Demand instance pricing 
		- **partial upfront**
			- low upfront payment + discounted hourly rate for the instance of reserved term 
		- **no upfront** 
			- discounted hourly rate for term duration 
- **volume based discounts for services like** [[monitoring-management-aws-orgs#^61928c|EC2 and S3]] 
- **estimate monthly bill with** [[aws-pricing-calculator#^b6d47e|AWS Price Calculator]] 
	- estimate cost of cloud migration 
	- generate lowest cost estimate for your workload 
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-pricing/) 
# Tags
- #aws-ccp-exam-notes/overview/pricing
- #aws-ccp-exam-notes/services/cost/overview 

	

