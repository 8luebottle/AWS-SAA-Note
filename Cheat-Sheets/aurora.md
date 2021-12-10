# Amazon Aurora
> Amazon Aurora is a modern relational database service offering performance and high availability at scale, fully open source MySQL- and PostgreSQL-compatible editions.

- **MySQL & PostgreSQL-compatible RDBMS**  
  - fully-managed Postgres or MySQL DB that needs to scale, automatic backups, [`HA`][HA] and fault tolerance.

  - Aurora can run MySQL or Postgres DB engines.
    - `5 x faster` over regular MySQL
    - `3 x faster` over regular Postgres

- 1/10 the cost over its competitors with similar performance and availability options.

- [`Snapshots`][snapshots]  
  - You can share a manual snapshot with other AWS accounts.  
    - Max: 20 accounts

- [`Replicas`][replicas]  

  ![Aurora Replicas](https://user-images.githubusercontent.com/48475824/145566188-84bf27ee-3d12-4581-a6b7-14c6d754a89b.png)

  - Aurora replicates 6 copies for your DB across 3 AZs.
    - 2 for each AZs, min 3 AZs.

  - An Aurora DB cluster can contain up to 15 Aurora Replicas.(High Availability)

- [`endpoints types` for Aurora DB Cluster][types of endpoints]:  
    endpoint == sepcific URL

  - `Cluster endpoint` == writer endpoint  
    - The only one that can perform `write operations such as DDL statements`.
    - Each Aurora DB cluster has one cluster endpoint and one primary DB instance.

    e.g. `mydbcluster.cluster-123456789012.us-east-1.rds.amazonaws.com:3306`

  - `Reader endpoint` == reader endpoint  
    - for read operations. (e.g `SELECT`)
    - Support for read-only connections to the DB cluster.

    e.g. `mydbcluster.cluster-ro-123456789012.us-east-1.rds.amazonaws.com:3306`

  - `Custom endpoint`  
    > An Aurora DB cluster has no custom endpoints until you create one.
    - Max: 5
    - Aurora Serverless ⇒ (X) custom endpoint (can't use)
    - Provides load-balanced database connections based on criteria other than the read-only or read/write capability of the DB instances.

    e.g. `myendpoint.cluster-custom-123456789012.us-east-1.rds.amazonaws.com:3306`

  - `Instance endpoint`
    - Connects to a specific DB instance within an Aurora cluster
    - Each DB instance in a DB cluster has its own unique instance endpoint.
    - Use instance endpoints to improve the connection speed

    e.g. `mydbinstance.123456789012.us-east-1.rds.amazonaws.com:3306`

- `Aurora Serverless`  
  - allows you to stop and start Aurora and scale automatically while keeping costs low. ⇒ only paying on a per invocation basis.
  - ideal for new projects or projects with infrequent DB usage.

- [`Aurora Global Databases`][global db]  

  ![Aurora Global DB](https://user-images.githubusercontent.com/48475824/145565092-60219cfd-9b45-4e0f-be27-8079fbe29d40.png)

  - Span multiple AWS Regions
  - `Low latency` global read
  - Providing `fast recovery` from the rare outage


<!-- Labeling -->
[HA]: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Concepts.AuroraHighAvailability.html
[snapshots]: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/USER_ShareSnapshot.html
[replicas]: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Replication.html
[types of endpoints]: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.Endpoints.html#Aurora.Overview.Endpoints.Types
[global db]: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database.html