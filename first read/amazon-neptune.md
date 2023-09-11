---
database: "amazon neptune: graph db"
---

# amazon neptune
---
- **key insights:**  ^b7b273
	- fully managed graph database service 
	- optimized for storing billions of relationships/querying the graph in ms latency 
	- use cases: recommendation engines, fraud detection, knowledge graphs, network security 
	- supports [[security-aws-kms#^bed19a|AWS KMS]] encryption at rest + [[monitoring-amazon-sns#^2bd9c4|SNS notifications]]
	- does not support:
		- cross region replicas 
		- encryption of existing neptune db
		- sharing of automatic [[storage-ebs#snapshots|snapshots]]
---
**table of contents:**
- [[#common use cases|common use cases]]
	- [[#common use cases#Social Networking|Social Networking]]
	- [[#common use cases#Recommendation Engines|Recommendation Engines]]
	- [[#common use cases#Knowledge Graphs|Knowledge Graphs]]
	- [[#common use cases#Identity Graphs|Identity Graphs]]
- [[#monitoring|monitoring]]
- [[#pricing|pricing]]
--- 
## common use cases 
### Social Networking
- easily process user’s interactions like comments, follows, and likes in a social network application through highly interactive queries.
### Recommendation Engines
- build applications for suggesting personalized and relevant products based on relationships between information such as customer’s interest and purchase history.
### Knowledge Graphs
- create a knowledge graph for search engines that will enable users to quickly discover new information. 
### Identity Graphs
- use as a graph database to easily link and update user profile data for ad-targeting, personalization, and analytics.
## monitoring 
- visualize graph with neptune workbench 
- get event notifications via [[managment-monitoring-amazon-sns#^a311ff|amazon SNS]]  
## pricing 
- billed based on the DB instance hours, I/O requests, storage, and Data transfer.
- Storage + I/O billed in GB/month and million request increments 
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-neptune)
# Tags
- #aws-ccp-exam-notes/services/databases/neptune  
---


	

