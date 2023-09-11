---
service: AWS savings plan
service-type: compute, cost savings
---

# AWS Savings plan
---
- **key insights:** 
	- cost-saving model for [[compute-EC2-summary|EC2]], [[compute-fargate|fargate]], and [[compute-lambda|lambda]] 
	- can be bought from any account, payer, or linked account
	- applies across AWS organization by default
		- can restrict to purchasing account
	- payment is all upfront, partial upfront, or no upfront
		- like [[compute-EC2#reserved fold|reserved instances]]
---
**table of contents:**
- [[#plan types %% fold %%|plan types %% fold %%]]
	- [[#plan types %% fold %%#compute savings plan %% fold %%|compute savings plan %% fold %%]]
	- [[#plan types %% fold %%#EC2 instance savings plan %% fold %%|EC2 instance savings plan %% fold %%]]
- [[#monitoring %% fold %%|monitoring %% fold %%]]
--- 
## plan types 
### compute savings plan %% fold %% 
- max flexibility with up to 66% savings on EC2, Fargate, and Lambda
- automatically applies to your EC2 instances regardless of its [[compute-EC2-summary#instance types fold|instance type]]
- can freely move workloads b/w different instance families, regions, or even migrate to [[compute-ECS|ECS]] using fargate while maintaining the discount
### EC2 instance savings plan %% fold %% 
- up to 72% discount off [[compute-EC2#^59341b|on-demand instances]]
- require a commitment to a specific instance family in a chosen [[AWS-Regions-and-Availability-Zones.jpg|region]]
- can switch instance sizes, OS, or adjust tenancy while maintaining discount
## monitoring 
- <mark style="background: #FF000094;">savings plan inventory</mark>: provides a detailed overview of your savings plans
- <mark style="background: #930083;">linked account</mark>: users in linked AWS accounts can see their specific savings plans
- can use [[monitoring-aws-budgets|AWS budgets]] to set savings plan utilization, coverage, and cost
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-savings-plan/)
# Tags
- #aws-ccp-exam-notes/services/cost/aws-savings-plan
- #aws-ccp-exam-notes/services/compute/aws-savings-plan
---