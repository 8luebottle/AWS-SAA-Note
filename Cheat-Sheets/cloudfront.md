# Amazon CloudFront
> Amazon CloudFront is a web service that speeds up the distribution of your static and dynamic web content, such as .html, .css, .js, and image files, to your users.

![AWS CloudFront](https://user-images.githubusercontent.com/48475824/146166686-f759f387-f898-4a49-bb48-31e0f1fffca0.png)

- CloudFront is a `CDN` (Content Distribution Network).  
  ⇒ It makes the website load fast by serving cached content that is nearby.

- Access to **cached content can be protected** via `Signed URLs` or `Signed Cookies`

    ⇒ (e.g., Netflix paid user)

  - `Signed URLs` for 1 file
    - can filter by date, path, IP address, expiration, etc.

  - `Signed Cookies` for n files

- [`Edge Location`][edge location] aren't just not read-only, you can write to them. (e.g., PUT object)
  - read & write

- `TTL(Time to Live)` defines how long until the cache expires. (refreshes cache)
  - when you invalidate your cache, you are forcing it to immediately expire.

- `Cache`:
  - refreshing the cache costs money, because of transfer costs to update Edge locations.

- `Distribution`:
  - defines a collection of Edge Locations and behavior on how it should handle your cached content.

  - **2 Types:**
    - `Web Distribution` (static website content)
    - `RTMP`: Realtime Messaging Protocol (Streaming Media)
      - files using Adobe Flash Media Server.

- [`Origin`][origin]:
  - Origin is the address of where the original copies of your files reside.
    - e.g., S3, EC2, ELB, Route53

  - If your origin is EC2, then use CloudFront.

  - On-demand Video 또는 Live Streaming Video 제공 | Serve video on demand or live streaming video
    - use `Origin Access Identity (OAI)` to easily restrict access to your S3 content.  
      OAI is used to access private S3 buckets.

- [`Lambda@Edge`][lambda edge]:
  - Serve private content by using Lambda@Edge customization

- `Geographic Match feature` (Geo restriction feature)
  - To allow or block web requests based on country of origin.

<!-- Labeling -->
[edge location]: https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/cache-hit-ratio-explained.html
[origin]: https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/DownloadDistS3AndCustomOrigins.html
[lambda edge]: https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/lambda-at-the-edge.html
