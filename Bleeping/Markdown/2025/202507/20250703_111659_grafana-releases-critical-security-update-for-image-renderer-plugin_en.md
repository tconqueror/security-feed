# Grafana releases critical security update for Image Renderer plugin

![Grafana releases critical security update for Image Renderer plugin](https://www.bleepstatic.com/content/hl-images/2025/07/03/header-grafana.jpg)

Grafana Labs has addressed four Chromium vulnerabilities in critical security updates for the Grafana Image Renderer plugin and Synthetic Monitoring Agent.

Although the issues impact Chromium and were fixed by the open-source project two weeks ago, Grafana received a bug bounty submission from security researcher Alex Chapman proving their exploitability in the Grafana components.

Grafana describes the update as a "critical severity security release" and advises users to [apply the fixes](http://grafana.com/blog/2025/07/02/grafana-security-update-critical-severity-security-release-for-cve-2025-5959-cve-2025-6554-cve-2025-6191-and-cve-2025-6192-in-grafana-image-renderer-plugin-and-synthetic-monitoring-agent/) for the vulnerabilities below as soon as possible:

[**CVE-2025-5959**](https://nvd.nist.gov/vuln/detail/CVE-2025-5959) (high-severity, 8.8 score) – type confusion bug in the V8 JavaScript and WebAssembly engine allows remote code execution inside a sandbox via a crafted HTML page  
[**CVE-2025-6554**](https://nvd.nist.gov/vuln/detail/CVE-2025-6554) (high-severity, 8.1 score) – type confusion in V8 enables attackers to perform arbitrary memory read/write through a malicious HTML page  
[**CVE-2025-6191**](https://nvd.nist.gov/vuln/detail/CVE-2025-6191) (high-severity, 8.8 score) – integer overflow in V8 allows out-of-bounds memory access, potentially leading to code execution  
[**CVE-2025-6192**](https://nvd.nist.gov/vuln/detail/CVE-2025-6192) (high-severity, 8.8 score) – use-after-free vulnerability in Chrome's Metrics component could cause heap corruption exploitable via crafted HTML

The security problems impact the Grafana Image Renderer versions prior to 3.12.9, and the Syntentic Monitoring Agent versions before 0.38.3.

The Grafana Image Renderer is a widely deployed plugin in production environments where automated dashboard rendering for scheduled email reports and embedding in third-party systems is crucial.

Even though it is not bundled by default in Grafana, the plugin is officially maintained by the project and has millions of downloads.

The Synthetic Monitoring Agent is part of Grafana Cloud's Synthetic Monitoring, used by customers who need custom probe locations, low-latency, high-visibility checks from internal nodes, and enterprises with hybrid or multi-cloud infrastructure needing synthetic tests behind firewalls.

It is not as widely deployed as the Image Rendered, but it can still be found in a significant number of high-value environments.

The two components are vulnerable because they include a headless Chromium browser for rendering dashboards.

To get the latest version of the Image Rendered plugin, use the command: `grafana-cli plugins install grafana-image-renderer`. For container installations, use: `docker pull grafana/grafana-image-renderer:3.12.9`.

The latest Synthetic Monitoring Agent version [can be downloaded from GitHub](https://github.com/grafana/synthetic-monitoring-agent/releases/tag/v0.38.3). For container upgrade, use: `docker pull grafana/synthetic-monitoring-agent:v0.38.3-browser`.

Grafana Labs says that Grafana Cloud and Azure Managed Grafana instances have been patched, so users relying on externally hosted instances don't have to take any action.

Grafana users have not shown good reflexes against urgent update notices recently. Ox Security highlighted last month that over [46,000 instances remained vulnerable](https://www.bleepingcomputer.com/news/security/over-46-000-grafana-instances-exposed-to-account-takeover-bug/) to an account takeover flaw with public exploit for which the vendor released fixes in May.