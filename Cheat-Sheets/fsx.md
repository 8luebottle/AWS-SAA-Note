# Amazon FSx
> Amazon FSx for Window File service provides a fully managed native Microsoft Windows file system.

<img width="700" alt="AWS FSx" src="https://user-images.githubusercontent.com/48475824/145661823-ee439d12-4103-4b63-89c0-02d1d16957f0.png">

- Fully managed Microsoft Windows file servers.

- `Pricing`:  
  - no upfront HW or SW cost.
  - Pay for only the resources used.
  - No min commitements, setup costs, or additional fees.

- [`Amazon FSx for Lustre`][lustre]:
  - fully managed file system that is optimized for `compute-intensive workloads`, such as `high-performance computing (HPC)`, `machine learning`, media data processing workflows, and electronic design automation (EDA).

  - Lets you launch and run a file system that provides sub-millisecond access to your data and allows you to read and write data at speeds of up to 100's of GB per second of throughput and millions of IOPS.

- `FSx Vs. EFS`:
  | Windows FSx | EFS |
  | --- | --- |
  | A managed Windows Server that runs Windows Server Message Block (SMB) - based file services. | A managed NAS filer for EC2 instances based on Network File System (NFS) version 4. |
  | for Windows and Windows Apps. | for Unix and Linux. |
  | Supports AD users, access control lists, groups and security policies, along with Distributed File System (DFS) namespaces and replication. |  |

<!-- Labeling -->
[lustre]: https://docs.aws.amazon.com/fsx/latest/LustreGuide/what-is.html
