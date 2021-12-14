# Amazon VPC Endpoints
> VPC Endpoint help keep traffic between AWS services within the AWS network.

![VPC Endpoint](https://user-images.githubusercontent.com/48475824/145993819-315945a9-f810-44c5-abe1-f211f5023da6.png)

- enables you to privately connect your `VPC ←→ AWS services`

- horizontally scaled

- `Type of VPC Endpoints`:
  - [`Interface Endpoint`][Interface Endpoint] :
    - Cost Money
    - use ENI with Private IP (powered by AWS [`PrivateLink`][private link])
    - support many AWS services

  - `Network Endpoint` :
    - No Charge
    - target for a specific route in your route table.
    - DynamoDB, and S3 only.

<!-- Labeling -->
[private link]: https://docs.aws.amazon.com/vpc/latest/privatelink/endpoint-services-overview.html
[Interface Endpoint]: https://docs.aws.amazon.com/vpc/latest/privatelink/vpce-interface.html
