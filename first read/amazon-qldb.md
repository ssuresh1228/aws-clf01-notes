---
database: "amazon qldb: serverless quantum ledger database"
serverless: no manual capacity provisioning
---

# amazon QLDB - quantum ledger database
---
- **key insights:** 
	- Fully managed ledger database - automatically scales based on workload 
	- maintains complete and verifiable history of changes over time
	- **serverless:** No capacity provisioning required or setting read/write limits.
	- transactions are ACID (atomicity, consistency, isolation, and durability) compliant.
	- multiple ledger replications in across AZs in a region  
	- doesn't support backup/restore, cross-region replication, point-in-time restores, and [[security-aws-kms#CMKs - customer managed keys|KMS CMKs]]
---
**table of contents:**
- [[#common use cases|common use cases]]
	- [[#common use cases#banks:|banks:]]
	- [[#common use cases#insurance|insurance]]
- [[#pricing|pricing]]
--- 
## common use cases
### banks:
- store accurate/complete record of all financial transactions 
### insurance 
- track entire history of claim transactions 
- if a conflict arises, QLDB can use cryptographically verify integrity of claims data
## pricing 
- read/write I/Os : charged per million requests
- Journal/Indexed Storage Rate: GB/month
- Data Transfer OUT From Amazon QLDB To Internet:
    - charged based on the amount of data transferred per month. The 
    - rate varies for different regions.
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-quantum-ledger-database-qldb/) 
# Tags
- #aws-ccp-exam-notes/services/databases/qldb 
---


	

