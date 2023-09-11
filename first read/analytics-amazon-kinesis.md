---
analytics: "amazon kinesis: real-time data collection, processing, analysis, and streaming"
---

# amazon kinesis 
---
- **key insights:** 
	- ingests real-time data such as video, audio, application logs, website clickstreams, and IoT telemetry data for machine learning, analytics, and other apps
---
**table of contents:**

--- 
## kinesis video streams 
- Ingests real-time video data from devices to AWS Cloud.
- Can store media data for custom retention periods.
- No infrastructure setup or management required.
- Supports real-time and batch applications.
- Provides TLS-based encryption for data streaming and at rest.
- Consists of producers, video streams, and consumers.
- Offers APIs, console, and producer libraries.
- Metadata can be embedded with fragments in a stream.
- Pricing based on data volume ingested/stored/consumed.
## kinesis data streams
- Massively scalable, durable data ingestion and processing service for streaming data. Configure many data producers to continuously put data into a Kinesis data stream.
### Monitoring %% fold %% 
- Monitor shard-level metrics in Kinesis Data Streams.
- Monitor data streams in Amazon Kinesis Data Streams using [[monitoring-cloudwatch#^7382c4|CloudWatch]], Kinesis Agent, Kinesis libraries.
- Log API calls with [[monitoring-CloudTrail#^718023|CloudTrail]].
### Security %% fold %% 
- Kinesis Data Streams automatically encrypts sensitive data using [[security-aws-kms#envelope encryption fold|master keys]] 
- Use IAM for access controls.
- Use interface [[networking-vpc#^4ff0f7|VPC]] endpoint to keep traffic within Amazon network.
### Pricing %% fold %% 
- Charged hourly for each shard.
- Charged per million PUT Payload Units.
- Enhanced fan-out incurs charges per consumer-shard hour and per GB of data retrieved.
### Limits %% fold %% 
- Enable extended data retention incurs additional charges on each shard hour.
- No upper limit on number of shards or streams in an account.
- Single shard can ingest up to 1 MiB of data per second or 1,000 records per second for writes.
- Default shard limit is 500 shards for US East (N. Virginia), US West (Oregon), and EU (Ireland) regions. For other regions, default shard limit is 200 shards.
- Each shard supports up to five read transactions per second.
## kinesis data firehouse
- easiest way to load streaming data into data stores/analytics tools 
- fully managed service - automatically scales to meet data throughput
- can batch, compress, and encrypt data before loading it
### features  %% fold %% 
- Captures, transforms, and loads streaming data into various destinations like S3, Redshift, Elasticsearch, HTTP endpoints, and service providers (Datadog, New Relic, MongoDB, Splunk).
- Allows control over batch size, batch interval, and data compression.
- Automatically scales to handle high input data rates and maintains specified data latency levels.
- Converts incoming data from JSON to Parquet or ORC formats before storing in S3.
- Provides pre-built [[compute-lambda#^74b901|Lambda]] blueprints for converting common data sources to JSON and CSV formats, which can be customized or replaced with custom functions.
### security  %% fold %%
- can encrypt data automatically after uploaded to destination 
- control access with IAM
### pricing   %% fold %%
- pay only for data transmitted/ingested through firehouse
- additional cost for data format conversion 
## kinesis data analytics 
- analyze streaming data to get insights and respond to customer/business needs in real time 
### features  %% fold %%
- serverless - automatically provisions infrastructure
- [[compute-EC2-autoscaling#Overview fold|elastically scales]] apps to keep up with data volume
- sub second processing latency 
### pricing  %% fold %% 
- hourly rate for average number of kinesis processing units (KPUs) used to run app
- java apps:
	- charged for single additional KPU per app for orchestration
	- also charged for app storage + backups 
--- 
# Resources
- [cheat sheet](https://tutorialsdojo.com/amazon-kinesis/)
# Tags
- #aws-ccp-exam-notes/services/analytics/kinesis 
---


	

