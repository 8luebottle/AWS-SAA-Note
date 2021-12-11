# Amazon ElastiCache
> Amazon ElastiCache is a fully managed, in-memory caching service supporting flexible, real-time use cases.

![ElastiCache](https://user-images.githubusercontent.com/48475824/145659593-954240cd-155f-46d8-89e9-66f800ff202f.png)

- **managed `in-memory` caching service**.
  - A cache is a temporary storage area.
- can launch either **Memcached** or **Redis.**
- Increase database and web App performance.
- Most frequently identical queries are stored in the cache.
- Resources only within the same VPC may connect to ElastiCache to ensure low latencies.

- [`Memcached`][memcached]:
  - is a simple key/value store preferred for caching HTML fragments.
  - faster than Redis.
  - if you need to `scale horizontally` ⇒ Memcached.

- [`Redis`][redis]:
  - richer data types and operations.
  - Great for leaderboard, geospatial data or keeping track of unread notifications.
  - Multi-AZ.
  - Backup & Restore Capabilities.
  - Ranking/Sorting Data.

<!-- Labeling -->
[memcached]: https://aws.amazon.com/elasticache/memcached/
[redis]: https://aws.amazon.com/elasticache/redis/
