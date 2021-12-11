# Amazon EFS
> Elastic File System is a Simple, serverless, set-and-forget, elastic file storage system.

- Hierarchical storage system.

- for Linux & Unix

- Supports the `Network File System version 4 (NFSv4) Protocol`.
  - version 4.0
  - version 4.1

- [`Storage classes`][storage-classes]:  
  - `EFS Standard`:  
    - for frequently accessed data.

  - `EFS Standard-Infrequent Access (Standard-IA)`:  
    – for infrequently accessed data.

  - `EFS One Zone`:  
    - for frequently accessed files stored redundantly.
    - within a single Availability Zone in an AWS Region.

  - `EFS One Zone-IA (One Zone-IA)`:  
    - for lower-cost storage & infrequently accessed files.
    - within a single Availability Zone in an AWS Region.

- **Charge:**
  - Only pay for the storage you use (no pre-provisioning required.)
  - Pay GB of storage per month.

- **Volumes:**
  - can scale `Petabyte size` storage.
  - will **shrink** and **grow** to meet current data stored.

- support thousands of `concurrent connections` over NFS(Network File System).

- can mount `multiple EC2 instances to a single EFS` (as long as they are all in the same VPC).

- `Read After Write Consistency`.

- Encryption through KMS.

<!-- Labeling -->
[storage-classes]: https://docs.aws.amazon.com/efs/latest/ug/how-it-works.html
