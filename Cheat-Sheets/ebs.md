# Amazon Elastic Block Storage
> Amazon Elastic Block Store (Amazon EBS) is an easy-to-use, scalable, high-performance block-storage service designed for Amazon Elastic Compute Cloud (Amazon EC2). Elastic Block Storage is a `virtual hard disk`.

- can create AMIs from Volumes or from Snapshots.

- `Volumes`:
  - are durable, `block-level storage` device that you can attach to a single EC2 instance.
  - `can be modified on the fly`.
    - e.g. storage type, volume size
  - always exist in the same AZ as the EC2 instance.

  - **Instance Store Volumes:**  

    ![Instance Storage](https://user-images.githubusercontent.com/48475824/145576108-9805060b-be81-473e-bc09-2f74f2e35f31.png)

    - A `temporary storage` type located on disk that are physically attached to a host machine.
      - host fails == lose data.

- [`Volume types`][volume-types]:
  - General Purpose (SSD).  
    - for most workloads.

  - Provisioned IOPS (SSD).
    - for mission-critical, low-latency, or high-throughput workloads.

  - Throughput Optimised Hard Disk Drive.  
    - for frequently accessed, throughput-intensive workloads.

  - Cold Hard Disk Drive.  
    - for lowest-cost and less frequently accessed workloads.

  - Magnetic.

- [`Snapshots`][snapshots]:  

  Snapshot == photograph of the disk.  
  - Snapshots `exist on S3` while volumes exist on EBS.
  - are a point-in-time copy of that disk.
  - are `incremental`, only changes made since the last snapshot are moved to S3.  

    ![EBS Incremental snapshots](https://user-images.githubusercontent.com/48475824/145575800-a94e37a9-87b4-4410-abed-1a3ee2db1dc7.png)

    - reduce cost.
    - reduce time.

  - **Initial Snapshots** of an EC2 instance will take longer to create than subsequent Snapshots
  - If taking a Snapshot of a root volume, the EC2 instance should be stopped before Snapshotting (Best Practice).
  - can take Snapshots while the instance is still running.

- `Termination`:  
  - By default, root volumes are deleted on termination.
  - EBS Volumes can have **termination protection**. (don't delete the volume on termination) ⇒ only `reboot` or `terminate`

- `Stopped`:
  - **EBS Backed instances** can be stopped and you will not lose any data.
  - **Instance Store Volumes** cannot be stopped. If the host fails then you lose your data. (Ephemeral)

- [`Encryption`][encryption]:
  - EBS Root Volumes of your DEFAULT AMI's CAN be encrypted.
  - Additional Volume can also be encrypted.
  - Snapshots or restored encrypted volumes will also be encrypted.
  - Unencrypted snapshots can be shared with other AWS accounts or made public.
  - `Unencrypted root volume → Encrypted root volume`:
    - Snapshot ⇒ Create an AMI (Image) ⇒ Launch EC2 Instance.

- `Migration`:
  - **to Another AZ**:
    - Snapshot ⇒ Create an AMI ⇒ Launch EC2 instance in new AZ.
  - **to Another Region**:
    - Snapshot ⇒ Create an AMI ⇒ Copy the AMI from one region to the other ⇒ Use the copied AMI to Launch the new EC2 instance in the Region.

<!-- Labeling -->
[volume-types]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html
[snapshots]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html
[encryption]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volumes.html
