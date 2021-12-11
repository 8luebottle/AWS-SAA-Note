# Amazon EMR
> Amazon EMR is a cloud big data platform for running large-scale distributed data processing jobs, interactive SQL queries, and machine learning (ML) applications using open-source analytics frameworks such as Apache Spark, Apache Hive, and Presto.

![Amazon EMR](https://user-images.githubusercontent.com/48475824/145659862-e3d4dd52-df60-41b0-93cb-a2ab33910a89.png)

Elastic MapReduce

- for `big data processing`.

- `Cluster`:  

  ![EMR Cluster](https://user-images.githubusercontent.com/48475824/145660019-ae6c6d15-ca46-4080-9833-3425cee96f6f.png)

  - A cluster is a `collection of Amazon Elastic Compute Cloud (Amazon EC2) instances`.

- [`consists of`][node types]:  

  - `Master node`: A node that manages the cluster.
    - tracks the status of task.
    - monitor the health of the cluster.
    - by default, log data is stored on the master node.

  - `Core node`: A node with software components that run tasks and store data in the Hadoop Distributed File System (HDFS) on your cluster.
    - managed by the master node.

  - `Task node` (optional): A node with software components that only runs tasks and does not store data in HDFS.
    - add power to perform parallel computation tasks on data.

- You can configure replication to S3 on 5 min intervals for all log data from the master node. ⇒ you have to create a cluster.

<!-- Labeling -->
[node types]: https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-master-core-task-nodes.html
