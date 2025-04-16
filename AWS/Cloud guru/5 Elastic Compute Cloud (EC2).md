## Pricing options

### On-demand

- Flexible: Low cost and flexibility of Amazon EC2 without any upfront payment or long-term commitment.
- Short-Term: Applications with short-term, spiky, or unpredictable workloads that cannot be interrupted.
- Testing the Water: Applications being developed or tested on Amazon EC2 for the first time.

### Reserved

Reserved capacity for 1 or 3 years. Up to **72% discount** on the hourly charge. Great if you have known, fixed requirements.

**Predictable Usage**: Applications with steady state or predictable usage.
**Specific Capacity Requirements**: Applications that require reserved capacity.
Pay up Front: You can make upfront payments to reduce the total computing costs event further.
Standard RIs: **Up to 72% off** the on-demand price.
Convertible RIs:
Scheduled RIs:

### Spot

Purchase unused capacity at a **discount of up to 90%**. Prices fluctuate with supply and demand. Great for applications with flexible start and end times.

Flexible, for range of time.

### Dedicated

- Compliance
- Licensing
- On-demand (hourly)
- Reserved **up to 70% off**

![[Screenshot 2025-04-13 at 11.46.01.png]]

## Role

- Temporary access
- Can be assign to AWS services or AWS account
- Preferred option, avoid hard-coding your credential

## Security Group

- All inbound traffic is blocked by default.
- All outbound traffic is allowed.
- You can have multiple security group attached to EC2 instances.

### Metadata

IP: http://169.254.169.254/latest/meta-data/public-ipv4

## Networking

3 different types of virtual networking cards:

### ENI: Elastic Network interface

Give you:

- Private and Public IPv4
- Many IPv6 addresses
- MAC address
- 1 or more security groups

For basic networking. Perhaps you need a separate management network from your production network or a separate logging network, and you need to do this at a low cost. In this scenario, use multiple ENIs for each network.

### EN: Enhance network

Give you:
Speed 10 Gbps - 100 Gbps
Higher I/O low CPU utilization
-> **Always choose ENA**

For when you need speeds between 10 Gbps and 100 Gbps. Anywhere you need reliable, high throughput.

### EFA: Elastic Fabric Adapter

OS-bypass, high performance, only support Linux, machine learning

### Placement group

3 types

#### Cluster Placement group

Grouping of instance within a single AZ.

#### Spread Placement group

Each placed on distance underlying hardware.

#### Partition Placement group

Each partition placement group has it own set of racks. Each rack has it own network, power source.

### Spot Instance

Must declare your max spot price
Spot fleets

If your Spot Instance has been marked for termination, a notification will be best-effort posted to the metadata of your EC2 instance two minutes before it is stopped or terminated. Reference: [Spot Instance Interruption Notices](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-interruptions.html#spot-instance-termination-notices "null")

### Deploy vCenter using VMware on AWS

Use cases:

- Hybrid cloud
- Cloud migration (old system)
- Disaster Recovery

### Outposts

Outposts brings the AWS data center directly to you, on-permises.

Outposts family:

- Outposts rack: 42U rack -> scale up to 96 racks (**larger**)
- Outpost server: 1U -> 2U form factor (**smaller than rack**)
