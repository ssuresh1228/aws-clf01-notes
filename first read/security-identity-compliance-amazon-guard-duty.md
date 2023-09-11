
---
Table of Contents:

---
# Amazon GuardDuty
---
- **key insights:**  ^04cebc
	- intelligent threat detection (regional) service
	- analyzes events across your AWS accounts via 
		- [[monitoring-CloudTrail#^718023|AWS CloudTrail]] 
		- Amazon VPC Flow Logs (network traffic data) ^a02e20
		- DNS logs (name-query patterns)
	- provides 3 severity levels (low, med, high) to prioritize response
---
**table of contents:**
- [[#threat detection categories|threat detection categories]]
	- [[#threat detection categories#reconnaissance %% fold %%|reconnaissance %% fold %%]]
	- [[#threat detection categories#instance compromise  %% fold %%'|instance compromise  %% fold %%']]
	- [[#threat detection categories#account compromise %% fold %%|account compromise %% fold %%]]
- [[#GuardDuty vs macie|GuardDuty vs macie]]
- [[#GuardDuty findings|GuardDuty findings]]
	- [[#GuardDuty findings#summary section %% fold %%|summary section %% fold %%]]
	- [[#GuardDuty findings#resource affected section %% fold %%|resource affected section %% fold %%]]
	- [[#GuardDuty findings#action section  %% fold %%|action section  %% fold %%]]
	- [[#GuardDuty findings#actor section %% fold %%|actor section %% fold %%]]
	- [[#GuardDuty findings#details section %% fold %%|details section %% fold %%]]
- [[#trusted IPs and threat lists|trusted IPs and threat lists]]
- [[#pricing|pricing]]
--- 
## threat detection categories
### reconnaissance %% fold %%
- signs of an attacker probing
	- odd API behavior
	- port scanning in VPC 
	- unusual failed logins 
	- unblocked port probing from a known malicious IP
### instance compromise  %% fold %%'
-  crypto mining
- malware using domain generation
- DoS (denial of service)
- unusually high network traffic/protocols
- instance comms with a malicious IP
- EC2 credentials used by external IP
- data exfil using DNS
### account compromise %% fold %%
- API calls from unusual location(s)/known malicious IPs
- disabling [[monitoring-CloudTrail#^718023]|CloudTrail]]
- weaker password policy
- unusual instance/infra launches
- strange region deployments 

--- 
## GuardDuty vs macie
- GuardDuty identifies threats; [[security-identity-compliance-amazon-macie#^c13eab|macie]] classifies and protects data in [[storage-s3#^939999|S3]] 
## GuardDuty findings
- generates findings on threats:
### summary section %% fold %%
- includes
	- type: concise description of problem
	- severity: high, med, or low
	- [[AWS-Regions-and-Availability-Zones.jpg|region]]
	- count: number of times detected after GuardDuty activation
	- account ID: AWS account ID where finding occurred
	- resource ID: AWS resource affected
	- threat list name: name of threat list containing IP/domain involved in finding
	- last seen: timestamp (local in console, UTC in API and CLI)
### resource affected section %% fold %% 
- includes:
	- resource role: usually the target
	- resource type
	- instance ID
	- port number
	- access key ID
	- principal ID
	- user type
	- username
### action section  %% fold %%
- includes
	- action type
	- API operation
	- AWS service name
	- connection direction (inbound, outbound, unknown)
	- network connection protocol
### actor section %% fold %%
- includes
	- IP location
	- ISP organization
	- IP address
	- port number 
	- domain
### details section %% fold %%
- includes:
	- threat purpose - can have the following values:
		- backdoor
		- (unusual) behavior
		- cryptocurrency
		- pentest
		- persistence - established user does something they never did
		- policy - behavior goes against security best practices
		- privilege escalation
		- recon
		- resource consumption
		- stealth - attacker is trying to hide actions/tracks
		- trojan
		- unauthorized access
	- resource type affected
	- threat family name
	- threat family variant
	- artifact - specific resource used 
## trusted IPs and threat lists
- trusted IPs
	- whitelisted IPs for secure comms
	- no GuardDuty findings
- threat lists
	- known malicious IPs
	- generate GuardDuty findings
	- up to 6 threat lists per AWS account per [[AWS-Regions-and-Availability-Zones.jpg|region]]
## pricing
- based on [[monitoring-CloudTrail#^718023|CloudTrail events]] per 1,000,000 events
- based on [[security-identity-compliance-amazon-guard-duty#^a02e20|VPC flow logs]] and [[security-identity-compliance-amazon-guard-duty#^04cebc|DNS log]] data per GB

---
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-guardduty/)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/guard-duty  
---