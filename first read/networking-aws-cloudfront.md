---
network: "aws CloudFront: distributes your content via edge locations for optimal performance"
---

# AWS CloudFront
---
- **key insights:**  ^00eb30
	- distributes your content via a global network of data centers, or edge locations. 
	- Users are directed to the fastest edge location for optimal performance. 
	- If the content is already there, it's delivered instantly. If not, CloudFront fetches it from your specified origin.
--- 
## price class 
- Select the price tier matching your maximum CloudFront service payment. 
- Typically, CloudFront serves your objects from all regions' edge locations.
## monitoring
- billing report summarizes all AWS services activities, including CloudFront 
- usage report provides a service activity summary, including usage charts for CloudFront.  
- CloudFront console offers reports like Cache Statistics, Popular Objects, Top Referrers, Usage, and Viewers, all derived from access logs. 
- [[monitoring-config#^64534d|AWS Config]] records CloudFront distribution changes
- [[monitoring-cloudwatch#^7382c4|CloudWatch]] metrics enable website or application monitoring. 
- Update global services in CloudTrail to view CloudFront requests.
## security 
- CloudFront, [[security-identity-compliance-aws-shield#^4cbf08|AWS Shield]], [[security-identity-compliance-aws-waf|AWS WAF]], and [[networking-route-53#^82e4b9|route 53]] create a secure perimeter against different attacks, including DDoS. 
- Content, APIs, or applications can be delivered via SSL/TLS with automatic advanced SSL features. 
- Geo-restriction allows you to control user access based on location. 
- Custom HTTP headers can limit access to ALBs, while Origin Access Control restricts S3 bucket access to CloudFront distributions. 
- Field-Level Encryption secures user-submitted data like credit card numbers. 
- AWS-managed prefix list restricts inbound traffic to CloudFront’s servers. 
- To omit headers from the origin response, use a CloudFront response headers policy.
## pricing
- costs for storing data in [[storage-s3#^939999|S3 bucket]].
- costs for data sent from edge location to user 
	- Data Transfer Out
- costs for Sending data to your origin,
	- Moving data out,
	- Making HTTP/HTTPS requests,
	- Asking to make old data invalid,
	- Using special security certificates with a CloudFront distribution.
- You will be charged more for secure requests and requests that use special encryption.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-cloudfront/)
# Tags
- #aws-ccp-exam-notes/services/networking/cloudfront 
---