# Amazon Virtual Private Cloud
> Amazon Virtual Private Cloud (Amazon VPC) enables you to launch Amazon Web Services resources into a virtual network you've defined.

![Amazon VPC](https://user-images.githubusercontent.com/48475824/145788506-5632633c-03d4-4302-9498-3ecf0c7f2811.png)

- `Logical datacenter` in AWS
  - A virtual network dedicated to your AWS account.

- [`Consists of`][VPC]:
  - `IGWs` (or Virtual Private Gateway):  
    A gateway that you attach to your VPC to enable communication between resources in your VPC and the internet.

  - [`Route Tables`][route tables]:  
    A set of rules, called routes, that are used to determine where network traffic is directed.

  - `Network Access Control Lists (NACLs)`:  
    A NACL is an optional layer of security for your VPC that `acts as a firewall` for `controlling traffic in and out` of one or more subnets.

    - `Lowest numbered rule`  
       As soon as a rule matches traffic, it's applied regardless of any higher-numbered rule that might contradict it.
      - Best Practice: start by creating rules in increments (10, 100)  
        - you can insert new rules where you need to later on.

    - NACLs are `STATELESS`

    - NACLs has `inbound and outbound rules` (just like SGs).
      - Rules can either `allow` or `deny` traffic (unlike Security Groups which can only allow)
      - Custom Network ACLS: `denies` all inbound and outbound traffic.

    - If you needed to `block a single IP address` you could via NACLs. (Security Groups cannot deny)

  - `Subnets`:  
    A `range of IP addresses` in your VPC.

    - Each subnet within a VPC must be associated with a network ACL.

    - can only be associated with 1 NACL at a time.
      - associating a subnet with a new NACL will remove the previous association.

  - [`Security Groups`][security groups]  
    Acts as a `virtual firewall` for your instance.
    - You can specify allow rules, but not deny rules.
    - Security group rules enable you to filter traffic based on protocols and port numbers.

- 1 Subnet = 1 AZ

- `State`
  - Security Group : `STATEFUL`
  - NACL : `STATELESS`
    - have separate inbound and outbound rules
      - rules: `allow` or `deny` traffic

- No Transitive Peering

- `Automatically given when a new VPC is created`:
  - **(O)** Route Table (default), NACL, Security Group (default)
    - the subnet is automatically associated with the default network ACL.
  - **(X)** Subnet, IGW

- Account 1's AZ type A ≠ Account 2's AZ type A
  - The AZ's are randomized.

- Reserves 5 IP within your subnets

- can only have 1 Internet Gateway in VPC

- `Block IP Address`
  - (X) Security Group
  - (O) ACL

<!-- Labeling -->
[VPC]: https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html
[route tables]: https://docs.aws.amazon.com/vpc/latest/userguide/how-it-works.html#what-is-route-tables
[security groups]: https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html