# AWS WAF
> AWS WAF is a web application firewall that lets you monitor the HTTP(S) requests that are forwarded to an Amazon CloudFront distribution, an Amazon API Gateway REST API, an Application Load Balancer, or an AWS AppSync GraphQL API.

<img width="800" alt="AWS WAF" src="https://user-images.githubusercontent.com/48475824/146520713-a028526f-15e6-4015-ab6f-903949994523.png">

- Control access to content.

- `filtering rules`:  
  allow/deny traffic
  - IP addresses
  - Query string parameters
  - SQL query injection

- `403`:
  - Blocked traffic returns HTTP 403 Forbidden

- [`WAF rule action`][waf rule]:
  - **ALLOW** all requests, except the ones you specify.

  - **BLOCK** all request, except the ones you specify.
  - **COUNT** the request that match the properties you specify.
  - **CAPTCHA**:  
    - `like COUNT`: If the request includes a valid, unexpired CAPTCHA token, AWS WAF handles it similar to the Count action handling.
    - `like BLOCK`: If the request doesn't include a valid CAPTCHA token, AWS WAF terminates the inspection of the web request and blocks the request, similar to the Block action.

- Request properties:

  - Originating IP address

  - Originating country
  - Request size
  - Values in request headers
  - Strings in request matching regular expressions (regex) patterns
  - SQL code (injection)
  - Cross-site scripting (XSS)

<!-- Labeling -->
[waf rule]: https://docs.aws.amazon.com/waf/latest/developerguide/waf-rule-action.html
