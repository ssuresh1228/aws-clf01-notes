---
gpt-summary: "aws ccp: databases"
---
# GPT database services summary
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	- [[database-RDS]]
	- [[database-aurora]]
	- [[database-dynamodb]]
	- [[database-elasticache]]
	- [[database-memorydb-redis]]
	- [[databases-documentdb]]
	- [[amazon-neptune]]
	- [[amazon-qldb]]
	- [[databases-amazon-dms]]
--- 
- **table of contents**
	- [[#AWS RDS - relational database service  %% fold %%|AWS RDS - relational database service  %% fold %%]]
	- [[#Amazon Aurora:  %% fold %%|Amazon Aurora:  %% fold %%]]
	- [[#Amazon Redshift:  %% fold %%|Amazon Redshift:  %% fold %%]]
	- [[#Amazon DynamoDB %% fold %%|Amazon DynamoDB %% fold %%]]
	- [[#Amazon ElastiCache:  %% fold %%|Amazon ElastiCache:  %% fold %%]]
	- [[#Amazon MemoryDB for Redis %% fold %%|Amazon MemoryDB for Redis %% fold %%]]
	- [[#AWS DocumentDB %% fold %%|AWS DocumentDB %% fold %%]]
	- [[#Amazon Neptune: Graph DB  %% fold %%|Amazon Neptune: Graph DB  %% fold %%]]
	- [[#Amazon QLDB  %% fold %%|Amazon QLDB  %% fold %%]]
	- [[#Amazon DMS %% fold %%|Amazon DMS %% fold %%]]
--- 
## AWS RDS - relational database service  %% fold %% 
### use case:  %% fold %% 
- Easy setup, operation, and scaling of relational databases in the cloud
### overview:  %% fold %% 
- Supports multiple database engines (MySQL, MariaDB, Oracle, SQL Server, PostgreSQL)
- Automatic backups and software updates
- Flexible scaling of compute resources and storage capacity
- Replication for availability, durability, and scalability
### pricing:  %% fold %% 
- Pay only for what you use, no minimum or setup fees
- Billed based on various factors such as instance type, storage, I/O requests, and data transfer amount
## Amazon Aurora:  %% fold %% 
### use case:  %% fold %% 
- Fully managed relational database service for MySQL and PostgreSQL
### overview:  %% fold %% 
- Modern relational database service with performance and high availability at scale
- Open-source MySQL- and PostgreSQL-compatible editions
- Developer tools for serverless and ML-driven apps
- Distributed, fault-tolerant, self-healing storage system
- Auto-scales up to 128 TiB per database instance (10 GB increments)
- Up to 15 low-latency read replicas
- Point-in-time recovery, continuous backup to Amazon S3
- Replication across three Availability Zones
- Fully managed service, automates administration tasks
- Security, availability, reliability at one-tenth of the cost
### pricing:  %% fold %% 
- Aurora Serverless: capacity adjusts automatically and you only pay for what you use
- Provisioned On-Demand Instances charge per DB instance-hour with no commitments or upfront features
- Charges vary based on cluster configuration (Aurora Standard or Aurora I/O-Optimized)
## Amazon Redshift:  %% fold %% 
### use case:  %% fold %% 
- Fully managed, relational cloud-based SQL analytics solution
- Integrates with AWS database, analytics, and machine learning services for real-time analytics, SQL-based machine learning, and Apache Spark analytics
### overview:  %% fold %% 
- Securely accesses, combines, and shares data from various sources without moving or copying it
- Easy and scalable analytics in a zero-administration environment
- MPP engine and architecture separate compute and storage for efficient scaling, with performance innovations like AutoMaterialized Views
- Delivers up to 5x better price performance than other cloud data warehouses
### pricing:  %% fold %% 
- Pay for capacity by the hour with on-demand pricing
- Significant discounts for steady-state workloads with Reserved Instances
- Pricing for Redshift Spectrum based on the number of bytes scanned when running SQL queries directly against data in an Amazon S3 data lake
- Concurrency Scaling provides one hour of free credits per day, with usage exceeding the free credits billed at a per-second on-demand rate
## Amazon DynamoDB %% fold %% 
### use case: %% fold %% 
- Fast and scalable NoSQL database service for storing and retrieving any amount of data.
### overview: %% fold %% 
- NoSQL database service with fast and predictable performance.
- Seamlessly scales to handle any amount of data and request traffic.
### pricing: %% fold %% 
- On-demand capacity mode: Pay for actual usage, best for unpredictable workloads.
- Provisioned capacity mode: Specify expected reads and writes per second, best for predictable traffic.
## Amazon ElastiCache:  %% fold %% 
### use case:  %% fold %% 
- Improve web app performance by using a fast, in-memory cache environment.
### overview:  %% fold %% 
- Managed service for distributed in-memory cache environment.
- Improves web app performance by using fast, in-memory systems instead of disk-based databases.
### pricing:  %% fold %% 
- Pay for on-demand nodes by the hour, no long-term commitment.
## Amazon MemoryDB for Redis %% fold %% 
### Use case: %% fold %% 
- Ideal for modern applications with microservices architectures.
### Overview: %% fold %% 
- Redis-compatible, durable, in-memory database service.
- Entire dataset stored in memory with distributed transactional log for speed and data durability.
### Pricing: %% fold %% 
- Pay by the instance hour with no long-term commitments or upfront fees.
- Pay only for the volume of data (in GB) you write to your MemoryDB cluster.
- Snapshot storage is billed at various storage rates by region.
## AWS DocumentDB %% fold %% 
### Use case: %% fold %% 
- Storing, querying, and indexing JSON data
- Migrating MongoDB databases to Amazon DocumentDB
### Overview: %% fold %% 
- Fully managed document database service
- MongoDB compatibility
- Supports native JSON workloads
- Uses MongoDB application code, drivers, and tools
- Improved performance, scalability, and availability
- No infrastructure management required
### Pricing: %% fold %% 
- On-demand instances: pricing per second with a 10-minute minimum
- Database I/O: pricing per million I/Os
- Database storage: pricing per GB/month
- Backup storage: pricing per GB/month
## Amazon Neptune: Graph DB  %% fold %% 
### use case: %% fold %% 
- Social Networking: easily process user interactions in a social network application
- Recommendation Engines: suggest personalized products based on customer's interests
### overview: %% fold %% 
- Fully managed graph database optimized for storing billions of relationships
- Supports AWS KMS encryption at rest and SNS notifications
### pricing: %% fold %% 
- Billed based on DB instance hours, I/O requests, storage, and data transfer
## Amazon QLDB  %% fold %% 
### Use case: %% fold %% 
- Banks: Store accurate and complete records of financial transactions.
- Insurance: Track the entire history of claim transactions and verify data integrity.
### Overview: %% fold %% 
- Fully managed ledger database that automatically scales based on workload.
- Maintains a complete and verifiable history of changes over time.
- Serverless architecture eliminates the need for manual capacity provisioning.
- ACID compliant transactions ensure atomicity, consistency, isolation, and durability.
- Multiple ledger replications across Availability Zones in a region.
### Pricing: %% fold %% 
- Charged per million read/write requests and GB/month for journal/indexed storage.
- Data transfer out from Amazon QLDB to the internet is charged based on the amount of data transferred per month, with varying rates for different regions.
## Amazon DMS %% fold %% 
### Use case:  %% fold %% 
- Migrate data between same/different databases
- Replicate data with high availability
- Consolidate databases into a data warehouse
### Overview:  %% fold %% 
- Migration service for databases
- Supports one-time data migration into RDS and EC2 based databases
- Enables replication of data with high availability
- Can consolidate databases into petabyte-scale data warehouse using Amazon RedShift and Amazon S3
- AWS schema conversion tool converts source database schema and code to target database format
### Pricing:  %% fold %% 
- Pay-as-you-go pricing based on compute resources used during migration
---
# tags:
- #gpt-summary/aws-ccp/database 