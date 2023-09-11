---
gpt-summary: "aws ccp: design principles"
---
# GPT summary: AWS design principles
--- 
- <span style='color:#8854d0'>note(s) summarized: </span>
	-  [[aws-design-principles]]
--- 
- **Scalability**:
  - Increase resources horizontally (more) or vertically (better specs).

- **Disposable resources instead of fixed servers**:
  - Automate setup of new resources, use infrastructure as code.

- **Automation**:
  - Focus on code deployment automation, let AWS handle management tasks.

- **Loose coupling**:
  - Reduce interdependencies, use well-defined interfaces and service discovery.

- **Services, not servers**:
  - Use managed services and serverless architecture to reduce complexity.

- **Databases**:
  - Choose the right DB for each workload, such as relational, NoSQL, data warehouse, or graph DB.

- **Managing increasing volumes of data**:
  - Use a data lake for central storage and analysis.

- **Removing single points of failure**:
  - Introduce redundancy, detect failure, and use durable data storage.

- **Optimize for cost**:
  - Right size resources, take advantage of elasticity and purchasing options.

- **Caching**:
  - Use app data caching and edge caching for faster content delivery.

- **Security**:
  - Use AWS features for defense in depth, share security responsibility, reduce privileged access, implement security as code, and enable real-time auditing.

- **Cloud architecture for best practices**:
  - Decouple components, think parallel, implement elasticity, and design for failure.

---
# tags:
- #gpt-summary/aws-ccp/design-principles 