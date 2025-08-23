# Over 46,000 Grafana instances exposed to account takeover bug

![Over 46,000 Grafana instances exposed to account takeover bug](https://www.bleepstatic.com/content/hl-images/2023/06/23/header-grafana.jpg)

More than 46,000 internet-facing Grafana instances remain unpatched and exposed to a client-side open redirect vulnerability that allows executing a malicious plugin and account takeover.

The flaw is tracked as [CVE-2025-4123](https://nvd.nist.gov/vuln/detail/CVE-2025-4123) and impacts multiple versions of the open-source platform used for monitoring and visualizing infrastructure and application metrics.

The vulnerability was discovered by bug bounty hunter [Alvaro Balada](https://www.linkedin.com/in/alvarobalada) and was addressed in [security updates](https://grafana.com/security/security-advisories/cve-2025-4123/) that Grafana Labs released on May 21.

However, as of writing this, more than a third of all Grafana instances reachable over the public internet have not been patched, according to researchers at application security company OX Security, who refer to the bug as ‘The Grafana Ghost’.

The analysts told BleepingComputer that their work focused on demonstrating the ability to weaponize Balada's finding.

After identifying versions vulnerable to the attack, they assessed the exposure by correlating the data with the platform's distribution across the ecosystem.

They found 128,864 instances exposed online, with 46,506 still running vulnerable versions that can still be exploited. This corresponds to a percentage of about 36%.

![Vulnerable Grafana endpoints as of June 13](https://www.bleepstatic.com/images/news/u/1220909/2025/June/vulnerable.png)

**Vulnerable Grafana endpoints**  
_Source: BleepingComputer_

OX Security’s in-depth analysis of CVE-2025-4123 uncovered that, through a series of exploitation steps combining client-side path traversal with open redirect mechanics, attackers can lure victims into clicking URLs that lead to loading a malicious Grafana plugin from a site controlled by the threat actor.

The malicious links could be used to execute arbitrary JavaScript in the user’s browser, the [researchers say](https://www.ox.security/confirmed-critical-the-grafana-ghost-exposes-36-of-public-facing-instances-to-malicious-account-takeover/).

![The exploitation process](https://www.bleepstatic.com/images/news/u/1220909/2025/June/exploiitation.jpg)

**The exploitation process**  
_Source: OX Security_

The exploit does not require elevated privileges and can function even if anonymous access is enabled.

The flaw permits attackers to hijack user sessions, change account credentials, and, in cases where the Grafana Image Renderer plugin is installed, perform server-side request forgery (SSRF) to read internal resources.

While the default Content Security Policy (CSP) in Grafana provides some protection, it does not prevent exploitation due to limitations in client-side enforcement.

OX Security’s exploit demonstrates that CVE-2025-4123 can be exploited client-side and could be leveraged to bypass modern browser normalization mechanisms by through JavaScript routing logic native to Grafana.

This allows attackers to exploit URL handling inconsistencies to serve malicious plugins, which in turn modify user email addresses, making account hijacking via password resets trivial.

Although CVE-2025-4123 has several exploitation requirements, like user interaction, an active user session when the victim clicks the link, and having the plugin feature enabled (is enabled by default), the large number of exposed instances and the lack for need of authentication create a significant attack surface.

To mitigate the risk of exploitation, it is recommended that Grafana administrators upgrade to versions 10.4.18+security-01, 11.2.9+security-01, 11.3.6+security-01, 11.4.4+security-01, 11.5.4+security-01, 11.6.1+security-01, and 12.0.0+security-01.