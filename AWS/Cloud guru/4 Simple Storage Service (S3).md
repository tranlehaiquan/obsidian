- Size minimum from 0 to 5 TB 
- Key value store
- Object
- [[#Versioning]]
- Metadata: content-type, last-modified
- Built for:
	- Availability 99.95% - 99.99%
	- Durability 99.99..99% (9 decimal)
- Lifecycle Management
- [[#Classes]]
- ACLs
- Bucket Policies 

### Versioning
- All versions includes all writes and deleted files.
- Great backup tool
- Cannot be disabled (once enabled), only suspended
- Lifecycle Rules
- Support MFA

### Classes
#### Standard
- High Availability and Durability 
	- durability (11 9's)
	- across multiple devices in multiple facilities (>=3 AZs)
- Designed for **Frequent Access**
- Use case: Suitable for Most Workloads
#### Standard-infrequent Access
- Rapid Access when needed
- Low per-GB storage price and a per-GB retrieval fee
- Use cases: long-term storage, backups, data store disaster

#### One zone-infrequent
Like [[#Standard-infrequent Access]] but one zone, low price
#### Intelligent-tiering

Auto move your object to correct tier.
#### Three Glacier Options
- Pay each time access
- Archive data
- Cheap storage

##### Glacier types:
- Instant retrieval
- Flexible retrieval
	- Minus to 12 hours to retrieval
	- Large sets of data at no cost
- Deep archive 
	- 7-10 years or longer to meet 
	- 12-48 hours to retrieval


|**Storage Class**|**Availability and Durability**|**AZ(s)**|**Use Case**|
|---|---|---|---|
|S3 Standard|99.99% Availability, 11 9’s Durability|>= 3|Suitable for most workloads (e.g., websites, content distribution, mobile and gaming applications, and big data analytics)|
|S3 Standard-Infrequent Access|99.9% Availability, 11 9’s Durability|>= 3|Long-term, infrequently accessed critical data (e.g., backups, data store for disaster recovery files, etc.)|
|S3 One Zone-Infrequent Access|99.5% Availability, 11 9’s Durability|1|Long-term, infrequently accessed, non-critical data|
|S3 Intelligent-Tiering|99.9% Availability, 11 9’s Durability|>= 3|Unknown or unpredictable access patterns|
|S3 Glacier Instant Retrieval|99.99% Availability, 11 9’s Durability|>= 3|Provides **long-term data archiving** with instant retrieval time for your data|
|S3 Glacier Flexible Retrieval|99.99% Availability, 11 9’s Durability|>= 3|Ideal storage class for archive data that does not require immediate access but needs the flexibility to retrieve large sets of data at no cost. Can be minutes or up to 12 hours.|
|S3 Glacier Deep Archive|99.99% Availability, 11 9’s Durability|>= 3|Cheapest storage class and designed for customers that retain data sets for 7–10 years or longer to meet customer needs and regulatory compliance requirements. The standard retrieval time is 12 hours, and the bulk retrieval time is 48 hours.|