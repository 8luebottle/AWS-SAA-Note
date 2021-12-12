# Amazon CloudWatch
> Amazon CloudWatch `monitors` your Amazon Web Services (AWS) resources and the applications you run on AWS in `real time`.

![Amazon CloudWatch](https://user-images.githubusercontent.com/48475824/145699344-f0ed26db-c1b0-496d-bc69-6e61b6a1f588.png)

- `Collections`:

  - [`Dashboards`][dashboard]: create visualizations based on metrics

  - `Events`: trigger an event based on a condition
    > e.g. every hour take snapshot of server

  - [`Alarms`][alarms]: triggers notification based on metrics when a defined threshold is breached.
    > e.g. Billing alarm w/ SNS

    - `Metric alarm`: watches a single CloudWatch metric or the result of a math expression based on CloudWatch metrics.

      - `Metric alarm states`:
        - `OK`: within the defined threshold.

        - `ALARM`: outside of the defined threshold.

        - `INSUFFICIENT_DATA`:  the metric is not available, or not enough data is available for the metric.  
          - e.g. alarm has just started

    - `Composite alarm`: includes a rule expression that takes into account the alarm states of other alarms that you have created.

  - `Logs`: Log data from AWS Services
    > e.g. CPU Utilization
    - Logs must belongs to a **Log Group**

    - You can stream custom log files
      > e.g. `production.log`

  - `Metrics`: Represents a time-ordered set of dat points, A variable to monitor.
    > e.g. CPU Utilization over time
    - Custom Metrics allows you to track High Resolution Metrics a sub min intervals all the way down to 1 sec.

- `Monitor`:
  - EC2: 5 min intervals | Detailed Monitoring: 1 min Intervals

  - Most other service: 1 min intervals | 1, 3, 5... min

- `CloudWatch Agent`:
  - needs to be installed on EC2 Host
    - track: `Memory Usage` and `Disk Size`

    ```bash
    sudo yum install amazon-cloudwatch-agent
    ```

  - Available as a package in Amazon Linux 2

  - Make sure that the IAM Role attached to the instance has the `CloutWatchAgentServerPolicy` attached.

<!-- Labeling -->
[dashboard]: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html
[alarms]: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html
