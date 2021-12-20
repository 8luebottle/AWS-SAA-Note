# AWS Shield
> Protects against distributed denial-of-service `(DDoS) attacks`

- `2 types`:
  - [`AWS Shield Standard`][standard]
    - Automatically enabled for all customers at no cost

    - Protects against common layer 3, 4 attacks
      - SYN/UDP floods
      - Reflection attacks

  - [`AWS Shield Advanced`][advanced]
    - [$3,000][pricing] per month, per org

    - Enhanced protection for EC2, ELB, CloudFront, Global Accelerator, Route 53
    - Business and Enterprise support customers get 24x7 access to the Shield Response Team (SRT)
    - DDoS cost protection

<!-- Labeling -->
[standard]: https://docs.aws.amazon.com/waf/latest/developerguide/ddos-standard.html
[advanced]: https://docs.aws.amazon.com/waf/latest/developerguide/ddos-advanced.html
[pricing]: https://aws.amazon.com/shield/pricing/
