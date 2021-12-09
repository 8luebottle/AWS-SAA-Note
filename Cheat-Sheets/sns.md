# Amazon SNS
> Fully managed pub/sub messaging, SMS, email, and mobile push notifications.

![AWS SNS](https://user-images.githubusercontent.com/48475824/145394578-fcce4ace-eefc-4bf3-b9ab-5731825e5969.png)

- Simple Notification Service (SNS) is a fully managed pub/sub messaging service.

- SNS is for `Application Integration`.
  It allows `decoupled` services and apps to communicate with each other.

- `Topic`: a logical access point and communication channel.
  - a topic is **able to deliver to multiple protocols.**

- [`encrypt`][encrypt]:
  - You can encrypt topics via **KMS**.

- `pub/sub`:  
  ![AWS SNS pub:sub](https://user-images.githubusercontent.com/48475824/145394659-e6a76245-c33e-45d5-a8d1-77f8e8ddd225.png)
  - `Publishers`: use the AWS API via AWS CLI or SDK to push messages to a topic.
  - `Subscriptions`: subscribe to topics.
    - When a topic receives a message it automatically and immediately pushes messages to subscribers.

- All messages published to SNS are stored redundantly across multiple AZs.

<!-- Labeling -->
[encrypt]: https://docs.aws.amazon.com/streams/latest/dev/kdf-consumer.html