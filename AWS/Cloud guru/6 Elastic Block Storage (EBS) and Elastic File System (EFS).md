## EBS
Elastic block storage, can attach to EC2
### SSD
#### GP2
- up to maximum 16,000 IOPS per volume
- smaller than 1 TB
- **good for boot volumes**
#### GP3
- 3,000 IOPS baseline per volume
- **ideal for application that require high performance at a low cost**
- can scale up to 16000 IOPS and 1000 MiB/s
- can be 4 times faster than GP2
#### io1
High performance and most expensive 
#### io2
Same price as io1
Higher durability and more IOPS

### HHD
Low-cost HDD volume
#### st1
- Frequently accessed, throughput-intensive workloads
- ﻿﻿Big data, data warehouses, ETL, and log processing
- ﻿﻿A cost-effective way to store mountains of data
- ﻿﻿Cannot be a boot volume
#### sc1
**Lowest cost option**

### IOPS vs Throughput
| **Aspect**                 | **IOPS**                                                      | **Throughput**                                                |
| -------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| **Definition**             | Measures the number of read and write operations per second   | Measures the number of bits read or written per second (MB/s) |
| **Best for**               | Quick transactions, low-latency apps, transactional workloads | Large datasets, large I/O sizes, complex queries              |
| **Strength**               | Ability to action reads and writes very quickly               | Ability to deal with large datasets                           |
| **Recommended AWS Option** | Provisioned IOPS SSD (io1 or io2)                             | Throughput Optimized HDD (st1)                                |
