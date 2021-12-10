# Amazon DynamoDB
> DynamoDB has two capacity modes, **Provisioned** and **On-Demand**. You can switch between these modes **once every 24 hours**.

- fully managed `NoSQL` `key/value` database.
- for `difficult to predict and control`.
- for workload has `large spikes of short duration`.
- New applications, or applications whose database workload is complex to forecast.
- Developers working on serverless stacks with pay-per-use pricing.
- Applications that contain `large amounts of data` but `require predictable read and write performance` while scaling is a good fit for Dynamo DB.

- stores 3 Copies of data on SSD drives across 3 regions.
  - Spread across 3 geographically distinct data centers.

- [`Read Consistency`][read-consistency]:
  - DynamoDB can be set to have `Eventually Consistent Reads` (default) and `Strongly Consistent Reads`.
    - **Eventually Consistent Reads**:
      - data is returned immediately, but data can be inconsistent.
      - copies of data will be generally consistent in 1 s.
      - Best Read Performance.

    - **Strongly Consistent Reads:**
      - will wait until data in consistent.
      - Data will never be inconsistent.
      - Higher latency.

- **fits for:**
  - Game, mobile, Web, ad-tech, IoT, ect.

- [`DAX: DyanmoDB Accelerator`][DAX]:  
  This is an `in-memory cache` for DynamoDB.

  - Use for latency.
  - Fully managed, highly available, in-memory cache.
  - 10x performance than DynamoDB.
  - Reduces request time from milliseconds to microseconds - even under load.
  - No need for developers to manage caching logic.

- [Read/Write Capacity Mode][r-w mode]:
  - `Provisioned`:
    - default, free-tire eligible.
    - for predictable or steady state workloads.

  - `On-Demand`:
    - for **new** or **unpredictable** workloads.
    - No hard limit == **become very expensive** based on emerging scenarios.
    - Pay-per-request pricing.
    - Use for new product launches.

- [`PITR (Point-in-Time Recovery)`][PITR]:  
  - Restore to any point in the last `35 days`.
  - Not enabled by default, you have to turn on.
  - Protect against accidental writes or delete.

- [`Global tables`][global-tables]:  

  ![Global Tables](https://user-images.githubusercontent.com/48475824/145569476-2c51fca8-2f3c-4994-a7b6-49b57848a852.png)

  - Globally distributed applications.
  - Based on DynamoDB Streams.
  - Multi-region redundancy for DR or HA.
  - No application rewrites.
  - Replication latency under 1 sec.

- [`DMS (Database Migration Service)`][db-migration-svc]:  

  ![db-migration svc](https://user-images.githubusercontent.com/48475824/145569689-766abd85-1883-4f53-864d-9ec0b54ac6db.jpg)

  - DB ⇒ DynamoDB through DMS

- [`Security`][security]:
  - Encryption at rest using KMS.
  - Site-to-site VPN.
  - Direct Connect (DX).
  - IAM policies and roles.
  - Fine-grained access.
  - VPC endpoints (private IP address).
  - CloudWatch and CloudTrail.

<!-- Labeling -->
[read-consistency]: https://docs.amazonaws.cn/en_us/amazondynamodb/latest/developerguide/HowItWorks.ReadConsistency.html
[DAX]: https://docs.amazonaws.cn/en_us/amazondynamodb/latest/developerguide/DAX.html
[r-w mode]: https://docs.amazonaws.cn/en_us/amazondynamodb/latest/developerguide/HowItWorks.ReadWriteCapacityMode.html
[PITR]: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/PointInTimeRecovery.html
[global-tables]: https://aws.amazon.com/dynamodb/global-tables/
[db-migration-svc]: https://aws.amazon.com/blogs/database/aws-database-migration-service-and-amazon-dynamodb-what-you-need-to-know/
[security]: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/security.html
