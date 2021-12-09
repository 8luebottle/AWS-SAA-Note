# Amazon SQS
> Simple Queue Service is a way of storing messages in a queue.

- A **queue** is a temporary repository for messages that are awaiting processing.

- `Pull` base.

- `Batch messages` for future processing.

- Size: **1 B - 256 KB**
  - can be increase through Extended Client Library for JAVA ⇒ 2GB.

- SQS is used for **Application Integration**, it lets decoupled services and apps talk to each other.

- `Decoupling` infrastructure, microservices
  - Any component of a distributed application can store messages in a fail-safe queue.

- To read SQS use need to pull the queue using the AWS SDK. SQS is not pushed-based.

- SQS can `retain message` from **60 sec - 14 days**. Default: 4 days.

- [**2 types:**][queue-types]

  1. `Standard`:  
    ![SQS standard](https://user-images.githubusercontent.com/48475824/145396845-369b4e23-3296-4193-9456-8026a563ac85.png)
      - **limit:** nearly `unlimited messages` per second
      - (X) order of delivery. (`insequence`)
        - because of the highly-distributed architecture that allows high throughput more than one copy of a message might be delivered out of order.
      - Guarantee that a message is `delivered at least once`.
      - Delivers at least once, you **must protect against duplicate messages** being processed.

  2. `FIFO`:  
    ![SQS FIFO](https://user-images.githubusercontent.com/48475824/145397007-e44adbc8-62ec-457b-923b-74f8609a5e1b.png)
      - **limit:** 300 per second
      - (O) order of messages.
      - Message delivery and exactly-once.

- [**2 kinds of polling:**][short-and-long-polling]  
  In the majority of cases, Long Polling is preferred over Short Polling.

  - `Short polling` (Default):
    - returns messages immediately, even if the message queue being polled is empty
      - empty ⇒ fee is charged ([for reduce price then use long polling][reduce-cost])

  - `Long polling`:
    - waits until a message arrives in the queue, or the long poll timeout expires.

- `Visibility time-out`:  

  ![SQS Visibility timeout](https://user-images.githubusercontent.com/48475824/145398571-edf9dd5f-0b86-4205-b70c-8494ad39af95.png)

  Visibility time-out is the period of time that messages are invisible in the SQS queues.
  - **Min**: 0 s
  - **Max**: 12 h
  - **Default**: 30 s

<!-- Labeling -->
[queue-types]: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html
[short-and-long-polling]: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-short-and-long-polling.html
[reduce-cost]: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/reducing-costs.html
