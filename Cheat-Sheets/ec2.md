# Amazon Elastic Compute Cloud
> Elastic Compute Cloud is a web service that provides resizable compute capacity in the cloud.

- [`Instances`][instances]:
  - Instance RAM must be < 150GB.
  - Instance families:
    - c3, c4, c5
    - m3, m4, m5
    - r3, r4, r5

- 4 different `price models`:
  - **On Demand**  
    Allows you to pay a fixed rate by the hour (or by the second) with no commitment.

  - **Reserved**  
    Provides you with a capacity reservation, and offers a significant discount on the hourly charge for instance.
    - Contract Terms: 1 Y or 3 Ys
  - **Spot**  
    Enable you to bid whatever price you want for instance capacity, providing for even greater saving if your applications have flexible start and end times.
  - **Dedicated Hosts**  
    Physical EC2 server dedicated for your use. Dedicated Hosts can help you reduce costs by allowing you to use your existing server-bound software licenses.

- [`Placement Groups`][placement groups]:
  - `Cluster` Placement Group:  

    ![placement-group-cluster](https://user-images.githubusercontent.com/48475824/145578805-b34e720b-4124-46ed-b3e7-18cc898209cd.png)

    - Low Latency / High Network Throughput

  - `Spread` Placement Group:  

    ![placement-group-spread](https://user-images.githubusercontent.com/48475824/145578887-8861147d-34c2-46a2-abff-ad98f9d95927.png)

    - Individual Critical EC2 Instances

  - `Partitioned` Placement Group:  

    ![placement-group-partition](https://user-images.githubusercontent.com/48475824/145578858-3c2adada-d29e-4e50-86ec-865a0b891f8f.png)

    - Multiple EC2 instances HDFX, HBase, and Cassandra.

- `Hibernate`:
  - Max: 60 days
  - much faster to boot up because you do not need to reload the OS.
  - [Charge in Hibernate state][charge-in-HS] (like stopped instance)
    - Elastic IP Address.
    - EBS Volumes attached to EC2 Instance

- `Termination`:
  - **Termination Protection**:  
    - default: turned off ⇒ must turn it on.

- `Metadata`:
  - Used to get information about an instance (such as public IP)
  - GET Metadata:  
    curl `https://169.254.169.254/latest/meta-data/`
  - GET Userdata:  
    curl `https://169.254.169.254/latest/user-data/`

<!-- Labeling -->
[instances]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Instances.html
[placement groups]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html
[charge-in-HS]: https://aws.amazon.com/blogs/aws/new-hibernate-your-ec2-instances/
