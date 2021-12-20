# AWS Storage Gateway
> AWS Storage Gateway is a set of `hybrid cloud storage services that provide on-premises access` to virtually unlimited cloud storage.

![AWS Storage Gateway](https://user-images.githubusercontent.com/48475824/146778366-3592a69a-bdd1-450a-bc2d-e7cad1a7bf44.png)

- Hybrid storage solution.

- support standard storage protocols such as `NFS`, `SMB`, `iSCSI`, and `iSCSI-VTL`

- `Minimal changes` are required to existing applications.

- ideal solution for customers that must support a hybrid storage environment that bridges both on-premises and cloud.

- All data is **encrypted** `in-transit` and `at-rest` in the cloud.

- `Back up`:
  provides three types of storage interfaces to back up customers’ on-premises applications:
  
  - `File Gateway`: Amazon S3 File Gateway,  Amazon FSx File Gateway

    <img width="400" alt="File Gateway" src="https://user-images.githubusercontent.com/48475824/146778688-e2987f0b-054a-45c7-a70b-21a68e907258.png">

    **store and access objects in Amazon S3** from file-based applications with local caching. Each file is stored as an object in Amazon S3 with a one-to-one mapping.

    - lets S3 act a local file system using `NFS or SMB`, extends your local hard drive to S3. (for flat files)

  - `Volume Gateway`:

    provides on-premises block storage over iSCSI, backed by Amazon S3, with local caching, [Amazon EBS snapshots][ebs snapshots], and clones.

    ![Volume Gateway](https://user-images.githubusercontent.com/48475824/146778781-16d09c05-9534-4551-bd4e-a7412117b545.png)

    - `Stored Volume Gateway`: continuously backups local storage to S3 as EBS snapshots Primary Data on-premise.
      - Entire Dataset is stored on site and asynchronously backed up to S3.
      - Stored Volumes are `1GB to 16TB` in size.

    - `Cached Volume Gateway`: caches the frequently used files on-premise.
      - Primary Data is stored on S3 Cached Volumes are `1GB to 32GB` in size.

  - `Tape Gateway`:
    storage with local caching for `low-latency` data access.

    ![Tape Gateway](https://user-images.githubusercontent.com/48475824/146778877-167968ae-3707-416f-b308-55424fd1e964.png)

    - backups virtual tapes to `S3 Glacier for long archiving storage`

<!-- Labeling -->
[ebs snapshots]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html
