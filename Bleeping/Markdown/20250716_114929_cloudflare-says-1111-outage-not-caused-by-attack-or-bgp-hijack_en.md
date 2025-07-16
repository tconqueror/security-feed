# Cloudflare says 1.1.1.1 outage not caused by attack or BGP hijack

![Cloudflare says 1.1.1.1 outage not caused by attack or BGP hijack](https://www.bleepstatic.com/content/hl-images/2025/06/12/Cloudflare.jpg)

To quash speculation of a cyberattack or BGP hijack incident causing the recent 1.1.1.1 Resolver service outage, Cloudflare explains in a post mortem that the incident was caused by an internal misconfiguration.

The outage occurred on July 14 and impacted most users of the service all over the world, rendering internet services unavailable in many cases.

“The root cause was an internal configuration error and not the result of an attack or a BGP hijack,” [Cloudflare says in the announcement](https://blog.cloudflare.com/cloudflare-1-1-1-1-incident-on-july-14-2025/).

This statement comes after people reported on social media that the outage was caused by a BGP hijack.

## Global outage unfolding

Cloudflare's 1.1.1.1 public DNS resolver launched in 2018 promising a private and fast internet connectivity service to users worldwide.

The company explains that behind the outage was a configuration change for a future Data Localization Suite (DLS) performed on June 6, which mistakenly linked 1.1.1.1 Resolver IP prefixes to a non-production DLS service.

On July 14 at 21:48 UTC, a new update added a test location to the inactive DLS service, refreshing the network configuration globally and applying the misconfiguration.

This withdrew 1.1.1.1 Resolver prefixes from Cloudflare’s production data centers and routed them to a single offline location, making the service globally unreachable.

Less than four minutes later, DNS traffic to the 1.1.1.1 Resolver began to drop. By 22:01 UTC, Cloudflare detected the incident and disclosed it to the public.

The misconfiguration was reverted at 22:20 UTC, and Cloudflare began re-advertising the withdrawn BGP prefixes. Finally, full service restoration at all locations was achieved at 22:54 UTC.

The incident affected multiple IP ranges, including 1.1.1.1 (main public DNS resolver), 1.0.0.1 (secondary public DNS resolver), 2606:4700:4700::1111 and 2606:4700:4700::1001 (main and secondary IPv6 DNS resolvers), and multiple IP ranges that support routing within Cloudflare infrastructure.

![Outage impacting key IP ranges](https://www.bleepstatic.com/images/news/u/1220909/2025/July/ip-ranges.jpg)

**Outage impacting key IP ranges**  
_Source: Cloudflare_

Regarding the incident’s impact on protocols, UDP, TCP, and DNS-over-TLS (DoT) queries to the above addresses saw a significant drop in volume, but DNS-over-HTTPS (DoH) traffic was largely unaffected as it follows a different routing via cloudflare-dns.com.

![Incident's impact for each protocol](https://www.bleepstatic.com/images/news/u/1220909/2025/July/protocol.jpg)

**Incident's impact for each protocol**  
_Source: Cloudflare_

## Next steps

The misconfiguration could have been rejected if Cloudflare had used a system that performed progressive rollout, the internet giant admits, blaming the use of legacy systems for this failure.

For this reason, it plans to deprecate legacy systems and accelerate migration to newer configuration systems that utilize abstract service topologies instead of static IP bindings, allowing for gradual deployment, health monitoring at each stage, and quick rollbacks in the event that issues arise.

Cloudflare also points out that the misconfiguration had passed peer review and wasn’t caught due to insufficient internal documentation of service topologies and routing behavior, an area that the company also plans to improve.