# Cloudflare: Outage not caused by security incident, data is safe

![Cloudflare: Outage not caused by security incident, data is safe](https://www.bleepstatic.com/content/hl-images/2023/11/02/cloudflare.jpg)

Cloudflare has confirmed that the massive service outage yesterday was not caused by a security incident and no data has been lost.

The issue has been largely mitigated. It started 17:52 UTC yesterday when the Workers KV (Key-Value) system went completely offline, causing [widespread service losses](https://www.bleepingcomputer.com/news/technology/google-cloud-and-cloudflare-hit-by-widespread-service-outages/) across multiple edge computing and AI services.

Workers KV is a globally distributed, consistent key-value store used by Cloudflare Workers, the company’s serverless computing platform. It is a fundamental piece in many Cloudflare services and a failure can cause cascading issues across many components.

The disruption also impacted other services used by millions, most notably the Google Cloud Platform.

![Workers KV error rate during the incident](https://www.bleepstatic.com/images/news/u/1220909/2025/June/error-rates.png)

**Workers KV error rate during the incident**  
_Source: Cloudflare_

In a post mortem, Cloudflare explains that the outage lasted almost 2.5 hours and the root cause was a failure in the Workers KV underlying storage infrastructure due to a third-party cloud provider outage.

“The cause of this outage was due to a failure in the underlying storage infrastructure used by our Workers KV service, which is a critical dependency for many Cloudflare products and relied upon for configuration, authentication, and asset delivery across the affected services,” [Cloudflare](https://blog.cloudflare.com/cloudflare-service-outage-june-12-2025/)[ says](http://blog.cloudflare.com/cloudflare-service-outage-june-12-2025/).

“Part of this infrastructure is backed by a third-party cloud provider, which experienced an outage today and directly impacted the availability of our KV service.”

Cloudflare has determined the impact of the incident on each service:

* _**Workers KV**_ – experienced a 90.22% failure rate due to backend storage unavailability, affecting all uncached reads and writes.
* _**Access, WARP, Gateway**_ – all suffered critical failures in identity-based authentication, session handling, and policy enforcement due to reliance on Workers KV, with WARP unable to register new devices, and disruption of Gateway proxying and DoH queries.
* **_Dashboard, Turnstile, Challenges_** – experienced widespread login and CAPTCHA verification failures, with token reuse risk introduced due to kill switch activation on Turnstile.
* _**Browser Isolation & Browser Rendering**_ – failed to initiate or maintain link-based sessions and browser rendering tasks due to cascading failures in Access and Gateway.
* **_Stream, Images, Pages_** – experienced major functional breakdowns: Stream playback and live streaming failed, image uploads dropped to 0% success, and Pages builds/serving peaked at \~100% failure.
* _**Workers AI & AutoRAG**_ – were completely unavailable due to dependence on KV for model configuration, routing, and indexing functions.
* _**Durable Objects, D1, Queues**_ – services built on the same storage layer as KV suffered up to 22% error rates or complete unavailability for message queuing and data operations.
* **_Realtime & AI Gateway_** – faced near-total service disruption due to inability to retrieve configuration from Workers KV, with Realtime TURN/SFU and AI Gateway requests heavily impacted.
* **_Zaraz & Workers Assets_** – saw full or partial failure in loading or updating configurations and static assets, though end-user impact was limited in scope.
* _**CDN, Workers for Platforms, Workers Builds**_ – experienced increased latency and regional errors in some locations, with new Workers builds failing 100% during the incident.

In response to this outage, Cloudflare says it will be accelerating several resilience-focused changes, primarily eliminating reliance on a single third-party cloud provider for Workers KV backend storage.

Gradually, the KV’s central store will be migrated to Cloudflare’s own R2 object storage to reduce external dependency.

Cloudflare also plans to implement cross-service safeguards and develop new tooling to gradually restore services during storage outages, preventing traffic surges that could overwhelm recovering systems and cause secondary failures.