
---
Table of Contents:

---
# Amazon inspector
---
- **key insights:**  ^72ad21
	- assesses the security configuration and behavior of your AWS cloud resources  
	- provides predefined rules and packages for security/networking assessments on 
		- [[compute-EC2#^e5d497|EC2 instances]]
		- container images in [[compute-ECR#^bef2f7|ECR]]
		- [[compute-lambda#^74b901|Lambda]] functions  
	- uses [[security-identity-compliance-aws-iam#^ab9f15|IAM]] *service-linked* roles
	- creates a *finding* when a vulnerability is discovered and describes it:
		- affected resource, vulnerability severity, remediation guidance
	- "unit testing" cloud infrastructure
---
- [[#features|features]]
- [[#key benefits|key benefits]]
- [[#concepts|concepts]]
- [[#rules and rule packages|rules and rule packages]]
- [[#assessment reports|assessment reports]]
- [[#pricing|pricing]]
- [[#GPT summary:|GPT summary:]]
--- 
## features
- analyzes system/resource config
- monitors activity + provides insight into assessment targets
- uses an API and optional agent for easy deployment/automation
## key benefits
- single-step deployment across all accounts
- automated discovery and real-time vulnerability findings
- central management with delegated admin account
- contextual risk scores for accurate response prioritization
- integration with [[security-identity-compliance-aws-security-hub#^d7ac3d|security hub]] and EventBridge for workflow automation
## concepts
- inspector agent
	- software for assessing [[compute-EC2#^e5d497|EC2 instance]] security
- assessment run
	- process of evaluating security issues in assessment targets
- assessment target
	- AWS resource collection assessed for security
- assessment template
	- config for assessment runs
- rule
	- security check leading to findings
- rules package:
	- collection of rules for security goals
- telemetry:
	- EC2 instance data collected for analysis
	- JSON format
		- delivered to Inspector, is encrypted, then stored in [[storage-s3#^939999|S3]]
## rules and rule packages
- Inspector assesses behavior and security config of assessment targets using selected security rules packages.
- Rules are grouped into packages by category, severity, or pricing.
- Each rule has an assigned severity level:
    - High, Medium, and Low levels indicate potential security issues 
    - Informational level highlights security configuration details.
- Findings from the Network Reachability package indicate 
	- port accessibility from the internet  
	- highlight network configurations including security group and ACL issues
- <mark style="background: #FF000094;">rules are analogous to unit tests</mark>
	- <mark style="background: #930083;">rule packages are analogous to predefined unit test suites </mark>
## assessment reports
- details tested items and results
- 2 report types: findings report and full report
	- findings report 
		- includes broad summary of assessment
		- evaluated EC2 instances, rules packages, and detailed findings
	- full report
		- includes findings report info 
		- lists rules that passed on all target instances
## pricing
- based on 2 criteria:
	- number of EC2 instances in each assessment
	- type(s) of rule packages
## GPT summary:
### Overview: %% fold %% 
- Amazon Inspector: Assess security config and behavior of AWS resources.
- Predefined rules/packages for security assessments on EC2, ECR, Lambda.
- IAM roles for authentication/authorization.
### Key Features and Benefits: %% fold %% 
- Analyze config, monitor activity, provide insight into targets.
- Easy deployment, automated discovery, real-time findings, central management.
- Integrates with Security Hub, EventBridge.
- API and optional agent for deployment/automation.
### Key Concepts: %% fold %% 
- Agent, assessment run, target, template, rule, package, telemetry.
### Assessment and Reporting: %% fold %% 
- Creates findings for vulnerabilities with resource details and guidance.
- Reports: Findings report, full report.
- Findings from Network Reachability package highlight network configs.
### Pricing: 
- Based on EC2 instances and rule packages.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-inspector/)
- [inspector user guide](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html)
- [[]]
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/inspector  
---