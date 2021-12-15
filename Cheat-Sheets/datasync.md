# AWS DataSync
> AWS DataSync is a secure, **online service** that automates and **accelerates moving data** between `on-premises and AWS Storage services`.

- All your data is **encrypted in transit** with **Transport Layer Security (TLS)**.

- used to move `large amount of data` from on-premisses to AWS.

- used with `NFS-and-SMB-compatible` file systems.
  - NFS: Network File System

  - SMB: Server Message Block

- `Replication`:
  - can be done hourly, daily, or weekly.

  - integration with S3, EFS, FSx for Windows servers.
    - can be used to replicate EFS to EFS

  - Install the `DataSync agent` to start the replication.
