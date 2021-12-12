# AWS CloudTrail
> AWS CloudTrail is an AWS service that helps you enable governance, compliance, and operational and `risk auditing` of your AWS account.

![AWS CloudTrail](https://user-images.githubusercontent.com/48475824/145700333-c681949e-3fb4-4ee6-b7be-9fa3457a3cfa.png)

- CloudTrail == CCTV (auditing)

- CloudTrail logs calls between AWS services.

- `governance`, `compliance`, `operational auditing`, and `risk auditing`.

- for When you need to know `who to blame`

- default logs event data for the past 90 days via `Event History`.
  - [`Trail`][trail]
    - to track `> 90 days` ⇒ create trail.
    - output ⇒ S3 bucket
    - Data Events are disabled by default when creating a Trail.
    - Trail logs in S3 can be analyzed ⇒ Athena

- `Log File Validation`
  - turn on ⇒ to ensure logs have not been tampered with your need

- [`Encryption`][encryption]
  - default: CloudTrail to your bucket are encrypted by Amazon server-side encryption with Amazon S3-managed encryption keys (SSE-S3).
  - encrypted through KMS.  
    - The KMS key that you choose must be created `in the same AWS Region` as the `Amazon S3 bucket` that receives your log files.

- `Logs`
  - CloudTrail logs can be streamed to CloudWatch logs.
  - **2 kinds of events:**
    - `Management Events`  
      Log management operations (e.g., AttachRolePolicy)

    - `Data Events`  
      Log data operations for resources.
      - **operations**: `GetObject`, `DeleteObject`
      - **resources**: Lambda, S3

<!-- Labeling -->
[trail]: https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html
[encryption]: https://docs.aws.amazon.com/awscloudtrail/latest/userguide/encrypting-cloudtrail-log-files-with-aws-kms.html
