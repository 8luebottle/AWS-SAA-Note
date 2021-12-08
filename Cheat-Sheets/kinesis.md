# Amazon Kinesis
> Amazon Kinesis is the AWS solution for collecting, processing, and `analyzing streaming data` in the cloud.

![Kinesis Input Output](https://user-images.githubusercontent.com/48475824/145224077-98786e43-401e-47ea-9026-931bd5e38581.png)

- `streaming data`:
  - e.g. Purchase from the online store (amazon.com), IoT Sensor Data, Stock Prices, Geospatial data (uber.com), Social Network Data (Twitter), etc.

- When you need `real-time` ⇒ Kinesis

- `Kinesis Data Streams`

  ![Kinesis Data Stream](https://user-images.githubusercontent.com/48475824/145223533-c7ee1042-6487-4895-97e4-42b16664c37a.png)

  - per running shard, data can persist within the `stream`, data is `ordered` and every consumer keeps its own position.
  - Consumers have to manually added(coded)
  - Data persists for 24 hours to 168 hours.  
    - default: 24 h

- [`Kinesis Firehose`][firehose]

  <img width="800" alt="Kinesis Firehose" src="https://user-images.githubusercontent.com/48475824/145223732-845f218b-0def-4a02-98d2-353fe632d69a.png">

  - pay for only the data ingested, data immediately disappear once processed.
  - Consumer of choice is from a predefined set of services: S3, Redshift, Eleasticsearch, or Splunk.

- `Analytics`:
  - [`Kinesis Data Analytics`][data-analytics]:

    <img width="800" alt="Kinesis Data Analytics" src="https://user-images.githubusercontent.com/48475824/145223879-af2e5c52-008b-43f1-8571-cc42bbf56100.png">

    - allows you to **perform queries in real-time**.
    - Needs a Kinesis Data Streams (input) / Firehose (output).

  - `Kinesis Video Analytics`:
    - securely ingests and stores video and audio encoded data to consumers such as SageMaker, Recognition, or other services to apply Machine learning and video processing.

- You can write data to stream using AWS SDK, but KPL is more efficient
  - [`KPL(Kinesis Producer Library)`][kpl] is a Java library to write data to a stream.

<!-- Labeling -->
[firehose]: https://docs.aws.amazon.com/streams/latest/dev/kdf-consumer.html
[data-analytics]: https://docs.aws.amazon.com/streams/latest/dev/kda-consumer.html
[kpl]: https://docs.aws.amazon.com/streams/latest/dev/developing-producers-with-kpl.html
