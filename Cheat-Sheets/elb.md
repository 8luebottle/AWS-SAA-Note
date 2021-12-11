# AWS Elastic Load Balancing
> Elastic Load Balancing (ELB) automatically distributes incoming application traffic across multiple targets and virtual appliances in one or more Availability Zones (AZs).

- Instances monitored by ELB are reported as; `InService`, or `OutofService`

- [`Load Balancer Types`][types]
  `ALB`, `NLB`, `CLB`  

  - **ALB | Application Load Balancer**

    ![ALB](https://user-images.githubusercontent.com/48475824/145672848-5f930787-b2d0-42be-939a-6edff54c1304.png)

    - has `Listeners`, `Rules`, and `Target Groups` to route traffic.
    - for `HTTP` and `HTTPS` traffic (OS Layer 7)
    - can create advanced request routing, sending specified requests to specific web servers.
    - (O) can attach a Web Application Firewall(WAF)
      - (X) no WAF for NLB and CLB.

  - **NLB | Network Load Balancer**

    ![NLB](https://user-images.githubusercontent.com/48475824/145672873-f9e36a01-9f41-4496-9781-30100f21b13c.png)

    - uses `Listeners` and `Target Groups` to route traffic.
    - for `TCP` traffic (OS Layer 4)
    - can handling millions of requests per second, while maintaining ultra-low latencies.
    - for extreme performance.
    - handle sudden and volatile traffic patterns while using a single static IP address per Availability Zone.

  - **CLB | Classic Load Balancer** (legacy)
    - uses `Listeners` and EC2 instances are directly registered as targets to CLB
    - HTTP/HTTPS (OS Layer 7), TCP (OS Layer 4)
    - recommended to use ALB or NLB

- [`Load Balancer Sate`][state]
  - `provisioning`:  
    The load balancer is being set up.

  - `active`:  
    The load balancer is fully set up and ready to route traffic.

  - `active_imparied`:  
    The load balancer is routing traffic but does not have the resources it needs to scale.

  - `failed`:  
    The load balancer could not be set up.

- [`504 Error`][504 error]:
  - `Gateway has timed out` ⇒ the application not responding within the idle timeout period.
    - Issue could be either at the Web Server layer or at the Database Layer.

- [`X-Forwarded-For Header`][x-forwarded-for]:  
  If you need the IPv4 address of your end user
  - get the original IP of incoming traffic passing through ELB.
  - helps you identify the IP address of a client when you use an HTTP or HTTPS load balancer.

- [`Health Check`][health check]  
  > Your Application Load Balancer periodically sends requests to its registered targets to test their status. These tests are called health checks.

  ![ELB health check](https://user-images.githubusercontent.com/48475824/145673042-b55c47ae-44cc-440d-9308-ec1acb0aeeaf.png)

  - health check don't support WebSockets.  

- [`Sticky Sessions`][sticky sessions]
  - enable your users to `stick to the same EC2 instance`.
    ⇒ Can be useful if you are storing information locally to that instance.
  - can be enabled for CLB or ALB and sessions are remembered via Cookie.

- Cross Zone Load Balancing  
  - enables you to load balance across multiple AZs.

- [`Path Pattern`][path conditions] allow you to direct traffic to different EC2 instances based on the URL contained in the request.
  - Route based on path patterns in the request URLs.  
    - e.g. `/img/*/pics`

<!-- Labeling -->
[types]: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/load-balancer-types.html
[state]: https://docs.aws.amazon.com/elasticloadbalancing/latest/application/application-load-balancers.html
[504 error]: https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/ts-elb-error-message.html#ts-elb-errorcodes-http504
[x-forwarded-for]: https://docs.aws.amazon.com/elasticloadbalancing/latest/application/x-forwarded-headers.html
[health check]: https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html
[sticky sessions]: https://docs.aws.amazon.com/elasticloadbalancing/latest/application/sticky-sessions.html
[path conditions]: https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html#path-conditions
