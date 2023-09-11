---
aws-cost: billing services overview
---
## overview
- **Cost Explorer** for AWS usage tracking, analysis; free for all accounts.
- Manage budgets with [[billing-aws-budgets|AWS Budgets]].
- See current charges details using **Bills**.
- **Payment History** shows past transactions.
- Billing period ends at midnight last day each month; AWS Billing and Cost Management calculates bill.
- Charges to credit card on file at end of billing cycle or for one-time fee; invoice issued as downloadable PDF.
- Set billing alerts with [[monitoring-cloudwatch#^7382c4|CloudWatch]] for usage exceeding defined thresholds.
- Track detailed AWS costs using **cost allocation tags** (AWS generated tags, user-defined tags).
## AWS Cost anomaly detection 
- AWS Cost Management feature; uses machine learning for anomalous spend pattern detection, alerts in AWS workloads.
- Alerts received individually or in aggregated reports via email; 
	- [[app-integration-sns#^6f6ad4|Amazon SNS]] for Slack notifications.
- Team evaluates spend patterns using machine learning, reducing false positives; weekly, monthly, custom timeframe cost data evaluation.
- **Billing group**: set of accounts in pro forma billing domain sharing common end customer; end customer maintains "Primary Account", sees accrued cost, usage across group.
## AWS Billing conductor 
- Feature simplifies AWS account billing, reporting; customizable pricing, cost visibility.
- Assign accounts to specific billing group for aggregated monthly cost, usage data view across AWS workloads, accounts.
- Uses Billing Groups; set of accounts in consolidated billing family sharing common end customer.
- Set up account for end customer maintaining "Primary Account"; view all costs, usage across business group.
## AWS Free Tier
- AWS account creation auto-signs up for free tier for **12 months**.
- Several AWS services usable for free within allocated usage limit.
- Track free tier usage, set **billing alarm with AWS Budgets** for charge notification.
## AWS Cost and usage reports 
- Provides AWS resource usage info, estimated costs.
- AWS Cost and Usage report: .csv file(s) stored in [[storage-s3#^939999|S3 bucket]]; accessible to those with permission.
- Useful for tracking Reserved Instance Utilization, charges, allocations.
- Time granularity options: **Hourly**, **Daily**, **Monthly** for item aggregation.
- Report can auto-upload into [[database-redshift#^fd71f3|RedShift]], [[analytics-amazon-quicksight#^68a572|Quicksight]] for analysis.
## AWS Cost explorer
- Default report visualizes costs/usage for TOP FIVE cost-accruing AWS services; detailed service breakdown in table view.
- Data viewable up to last 12 months; forecast next three months spend; Reserved Instances purchase recommendations.
- Cost Explorer requires enablement by AWS account owner with **root credentials.**
- Management account owner enabling Cost Explorer applies to all organization accounts; no individual access grant or denial.
- Create forecasts predicting AWS usage, define forecast time range.
- Other default reports: 
	- **EC2 Monthly Cost and Usage report** (past two months, current month-to-date costs), 
	- **Monthly Costs by Linked Account report** (cost distribution across organization), 
	- **Monthly Running Costs report** (past three months running costs, coming month forecast with confidence interval).
## AWS Budgets 
- Set custom budgets for cost, usage alerts when exceeding or forecasted to exceed budget.
- Budgets allow view of plan proximity to budget/free tier limits, usage to date (including Reserved Instances, Savings Plans), current AWS estimated charges, predicted end-month charges, used budget percentage.
- Budget info updated thrice daily.
- Budget types: **Cost budgets** (service spend planning), **Usage budgets** (service usage planning), **RI utilization budgets** (set, alert on RI usage below threshold), **RI coverage budgets** (set, alert on instance hours covered by RIs below threshold).
- Budgets tracked daily, monthly, quarterly, yearly; customizable start, end dates.
- Budget alerts via email, Amazon SNS topic.
- First two budgets free of charge.

# Resources 
- [AWS budgets](https://aws.amazon.com/aws-cost-management/aws-budgets/)  
- [AWS cost explorer ](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)  
- [aws cost and usage reporting/](https://aws.amazon.com/aws-cost-management/aws-cost-and-usage-reporting/)  
- [aws cost management faqs](https://aws.amazon.com/aws-cost-management/faqs/)
- [aws account billing](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2)
# tags 
- #aws-ccp-exam-notes/services/billing/aws-budgets   
- #aws-ccp-exam-notes/services/billing/cost-anomaly-detection
- #aws-ccp-exam-notes/services/billing/billing-conductor
- #aws-ccp-exam-notes/services/billing/free-tier 
- #aws-ccp-exam-notes/services/billing/aws-cost-and-usage-reports
- #aws-ccp-exam-notes/services/billing/aws-cost-explorer 