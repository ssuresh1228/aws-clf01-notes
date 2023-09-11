---
security: WAF - web application firewall
network security:
---

# AWS WAF - web app firewall
---
- **key insights:**  ^e1b31b
	- web application firewall 
	- defends web apps by configuring rules based on defined conditions:
		- IP addresses, HTTP headers, HTTP body, URI strings, SQL injection, cross-site scripting
---
**table of contents:**
- [[#features|features]]
- [[#conditions, rules, and web ACLs|conditions, rules, and web ACLs]]
- [[#pricing|pricing]]
--- 
## features 
- enables rule creation for filtering web traffic 
- for application layer attacks, proactive rules like Rate Based Blacklisting can be set up.
- WAF provides real-time metrics and captures request details including IP addresses, geo locations, URIs, User-Agent, and Referers
- parses JSON request body content for specific keys or values to protect APIs and reduce false positives
- AWS WAF Security Automations offers a solution with pre-configured WAF rules for filtering common web-based attacks
## conditions, rules, and web ACLs 
- Conditions define characteristics in web requests for WAF monitoring
- Conditions are combined into rules
- There are regular rules and rate-based rules with rate limits
- WAF Managed Rules offer pre-configured protection against common threats
- Rules are combined into web ACLs, each with defined actions
- HTTP headers can be inserted for request validation or application behavior
- WAF allows configuring HTTP status codes and response bodies when blocking requests
## pricing 
- based on 
	- number of web access control lists (ACLs) created
	- number of rules per ACL
	- number of web requests received 
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-waf/) 
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/waf  
---


	

