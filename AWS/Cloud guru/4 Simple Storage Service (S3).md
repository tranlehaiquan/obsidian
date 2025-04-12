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
- Encryption

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

### Encryption 

#### Encryption in transit
- SSL/TLS
- HTTPS
#### Encryption at rest: Server-side encryption (by default)
- SSE-S3: S3 managed the keys
- SSE-KMS: AWS key management service-managed keys
- SSE-C: Customer managed keys
#### Encryption at rest: Client-side encryption
You encryption the files yourself before you upload them to S3

##### Enforcing Server-side encryption for S3 upload:
When upload files add Header `x-amz-server-side-encryption` to tell server side encryption:
- AES256
- kms
Create Bucket policy to deny user upload file doesn't include header `x-amz-server-side-encryption`

### S3 performance 
3500r/s PUT/COPY/POST/DELETE
5500r/s GET/HEAD

You can get better performance by spreading your reads across **different prefix**.
1 prefix 5500 r/s -> 2 prefix 11000 r/s

##### S3 LIMITATIONS WHEN USING KMS
- When you upload a file, you will call **GenerateDataKey** in the KMS API.
- When you download a file, you will call **Decrypt** in the KMS API.
- Can't request quota for increase KMS.
- Quota can be 5500, 10000, 30000 for specific region.
#### Multipart uploads
- Recommended for files over 100MB
- Required for files over 5GB
- Parallelize uploads
#### Byte-Range Fetches
- Parallelize download by specifying byte range
- If it failure in the download, it's only for specifying byte range
### S3 replication
- You can replicate objects from one bucket to another (must enable version for both buckets)
- Object in an existing bucket are **not replicated automatically**, replication only work after turn on.
- Delete makers are not replicated by default