---
service: memoryDB for redis
service-type: database
service-description: Redis-compatible, durable, in-memory database service
---

# amazon memoryDB for Redis
---
- **key insights:** 
	- Redis-compatible, durable, in-memory database service.
	- microsecond read latency, single-digit millisecond write latency, high throughput.
	- Ideal for modern applications with microservices architectures.
	- Entire dataset stored in memory with distributed transactional log for speed and data durability.
	- Fully managed primary database, no need for separate cache or durable database management.
---
**table of contents:**
- [[#features|features]]
- [[#pricing|pricing]]
	- [[#pricing#on demand nodes|on demand nodes]]
	- [[#pricing#reserved nodes|reserved nodes]]
	- [[#pricing#data written|data written]]
	- [[#pricing#snapshot storage|snapshot storage]]
--- 
## features
- Strong consistency for primary nodes and eventual consistency for replica nodes.
- Microsecond read and single-digit millisecond write latencies with high TPS.
- Flexible and friendly Redis data structures and APIs for easy application building and migration.
- Data durability with fast recovery and restart using Multi-AZ transactional log.
- Multi-AZ availability with automatic failover and recovery from node failures.
- Easy horizontal and vertical scaling for increased throughput.
- Read-after-write consistency for primary nodes and eventual consistency for replicas.
- supports encryption in transit, at rest, and user authentication.
- Automatic [[storage-ebs#snapshots|snapshot]] storage in [[storage-s3#^939999|S3]] with retention for up to 35 days.
- Support for large clusters with up to 500 nodes and over 100 TB of storage.
- Encryption in-transit with TLS and at-rest with [[security-aws-kms#^bed19a|KMS keys]] 
- User authentication and authorization with Redis ACLs.
- Support for AWS Graviton2 instance types.
- Integration with [[monitoring-cloudwatch#^7382c4|CloudWatch]], [[monitoring-CloudTrail#^718023|CloudTrail]], and [[monitoring-amazon-sns#^2bd9c4|amazon SNS]]
- Fully-managed software patching and upgrades.
- [[security-identity-compliance-aws-iam#^ab9f15|IAM integration]] and tag-based access control for management APIs.
## pricing 
### on demand nodes
- pay by the instance hour with no long-term commitments or upfront fees
### reserved nodes 
- Pay low hourly charges with no upfront payment (No Upfront)
- Make a one-time, partial upfront payment with lower hourly charges (Partial Upfront)
- Pay all upfront for even lower hourly charges (All Upfront)
### data written 
- pay only for the volume of data (in GB) you write to your MemoryDB cluster
- includes the Redis key, value, and command volume
- no associated costs for reads
### snapshot storage
- snapshot is a copy of an entire cluster at the time when the snapshot was taken.
- no additional charge for snapshot storage of up to 100% of your total MemoryDB cluster storage for a region
- Additional snapshot storage is billed at various storage rates by region
  
--- 
# Resources
- [FAQs](https://aws.amazon.com/memorydb/faqs/)
- [developer guide](https://docs.aws.amazon.com/memorydb/latest/devguide/servicename-feature-overview.html)
# Tags
- #aws-ccp-exam-notes/services/databases/memorydb-redis  
---


	

