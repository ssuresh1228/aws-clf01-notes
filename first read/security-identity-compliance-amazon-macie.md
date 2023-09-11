---
service: macie
service-type: security
---

# Amazon Macie
---
- **key insights:**  ^c13eab
	- uses ML to automatically find and protect sensitive data in AWS:
		- personally identifiable info and intellectual property
	- has data type identification, compliance verification, policy change detection, data egress alerts, and document sharing detection
---
**table of contents:**
- [[#concepts  %% fold %%|concepts  %% fold %%]]
	- [[#concepts  %% fold %%#content type classification %% fold %%|content type classification %% fold %%]]
	- [[#concepts  %% fold %%#file extension classification  %% fold %%|file extension classification  %% fold %%]]
	- [[#concepts  %% fold %%#theme classification  %% fold %%|theme classification  %% fold %%]]
	- [[#concepts  %% fold %%#regex classification %% fold %%|regex classification %% fold %%]]
	- [[#concepts  %% fold %%#pII classification %% fold %%|pII classification %% fold %%]]
	- [[#concepts  %% fold %%#support vector machine-based classification|support vector machine-based classification]]
- [[#pricing|pricing]]
--- 
## concepts  %% fold %% 
- datasource: where data originates; includes [[monitoring-CloudTrail#^718023|CloudTrail]] event logs and [[storage-s3#^939999|S3]] buckets  
- macie uses auto content classification methods to identify and prioritize your sensitive data 
- assigns risk levels from 1 (lowest) to 10 (highest)
### content type classification %% fold %% 
- uses file header identifiers 
- only 1 content type per object 
- no modification/addition of content types allowed
### file extension classification  %% fold %% 
- uses managed file extensions 
- only 1 file extension per object 
- no modification/addition of file extensions 
- can enable/disable existing file extensions
### theme classification  %% fold %% 
- based on keywords in data objects 
- multiple themes per object are possible 
- no mod/addition of themes
- enable/disable existing themes 
### regex classification %% fold %%
- uses managed regex patterns based on specific patterns 
- 1 object can have many regex-es 
- no mod/addition of regex-es 
- enable/disable existing regex-es 
### pII classification %% fold %%
- Based on industry standards like NIST-80-122 and FIPS 199
- Identifies personally identifiable information
### support vector machine-based classification
- Classifies [[storage-s3#^939999|S3]] object content and metadata
- Considers text, token n-grams, character n-grams, and document features
- Accurate content classification



## pricing
- based on content classified and [[monitoring-CloudTrail#^718023|CloudTrail]] events assessed 
- stores classified [[storage-s3^|S3]] object metadata for 30 days for free 
- optional extended data retention has monthly fees
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-macie/)
# Tags
- #aws-ccp-exam-notes/services/security-identity-compliance/macie  
---