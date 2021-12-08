# AWS Fargate
> Technology that you can use with Amazon ECS to run container without having to manager servers or clusters of Amazon ECS instances.

<img width="800" alt="AWS Fargate" src="https://user-images.githubusercontent.com/48475824/145221219-43e55796-3c11-4c6a-8e0c-f7aba1419612.png">

- Serverless

- Components:
  - `Clusters`: a logical grouping of tasks or services.
  - `Tasks`: the instantiation of task definition within a cluster.

- Use it when:
  - Have a `large workload` but are overhead conscious.
  - Have `small or burst style` workloads.
  - Use `batch or period` workloads.
