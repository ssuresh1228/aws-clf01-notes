---
database: migration service between same/different DBs
sticker: lucide//arrow-left-right
---

# amazon DMS - database migration service 
---
- **key insights:** 
	- migration service between same/different DBs
	- can use for one time data migration into [[database-RDS#^b3267c|RDS]] and [[meta-compute#EC2|EC2]] based DBs
	- replicate your data with high availability (enable multi-AZ) 
		- does not support on-premises to on-premises migration
	- consolidate DBs into petabyte-scale data warehouse by streaming to [[database-redshift#^fd71f3|amazon RedShift]] and [[meta-storage#Amazon S3 (Simple Storage Service)|amazon S3]]   
	- AWS schema conversion tool converts source DB schema + most of its code to target DB compatible format 
	- pay only for compute resources used during migration 
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/aws-database-migration-service/)
# Tags
- #aws-ccp-exam-notes/services/databases/dms 
---


	

