---
relational database: AWS RDS - relational database service
---

# AWS RDS  - relational database service

^b3267c

---
- **key insights:**  ^5a198f
	- easy to set up, operate, and scale relational database in cloud
	- Supports MySQL, MariaDB, Oracle, SQL Server, PostgreSQL
	- Automatic backups and software updates
	- Flexible scaling of compute resources and storage capacity
	- Replication for availability, durability, and scalability
	- No upfront investments, pay for resources used
--- 
## read replicas 
- creates one or more read-only copies of your source (primary) RDS instance
- automatically synchronized with the source instance
	- typically a primary database used for read and write operations
## deployments 

### read replicas
- scales read workload of DB
- can create up to 5 read replicas 
- data is only written to main DB
- ![[Pasted image 20230903202850.png]]
### multi AZ
- high availability - failover in case of AZ outage 
- data is only read/written to in main DB
- can only have 1 AZ as failover
- ![[Pasted image 20230903202900.png]]
### multi-region
- read replicas in different regions 
- disaster recovery in case of region issue 
- local performance for global reads 
- higher cost of read replication 
- ![[DB_multi_region.png]]
## pricing 
- Pay only for what you use, no minimum or setup fees.
- Billed based on DB instance type/hours, storage, I/O requests, provisioned IOPS, backup storage, and data transfer.
- free tier:
	- use of Single-AZ Micro DB instances w/ MySQL, MariaDB, PostgreSQL, Oracle (BYOL), and SQL Server Express. 
	- 750 instance hours/month. 
	- Free 20GB General Purpose (SSD) database storage + 20GB backup storage/month.
# Resources
- [RDS overview](https://github.com/kananinirav/AWS-Certified-Cloud-Practitioner-Notes/blob/master/sections/databases.md#aws-rds-overview)
- [FAQs](https://aws.amazon.com/rds/faqs/)
# Tags
- #aws-ccp-exam-notes/services/databases/rds  
---


	

