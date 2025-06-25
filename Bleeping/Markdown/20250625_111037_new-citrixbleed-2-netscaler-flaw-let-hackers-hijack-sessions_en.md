# New ‘CitrixBleed 2’ NetScaler flaw let hackers hijack sessions

![Citrix](https://www.bleepstatic.com/content/hl-images/2023/10/25/citrix-bleed.jpg)

A recent vulnerability in Citrix NetScaler ADC and Gateway is dubbed "CitrixBleed 2," after its similarity to an older exploited flaw that allowed unauthenticated attackers to hijack authentication session cookies from vulnerable devices.

Last week, Citrix published a [security bulletin](https://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX693420) warning about flaws tracked as CVE-2025-5777 and CVE-2025-5349 that impact NetScaler ADC and Gateway versions before 14.1-43.56, releases before 13.1-58.32, and also 13.1-37.235-FIPS/NDcPP and 2.1-55.328-FIPS.

The CVE-2025-5777 is a critical flaw that is caused by out-of-bounds memory read, allowing unauthenticated attacks to access portions of memory that they should not have access to.

This flaw impacts NetScaler devices that are configured as a Gateway (VPN virtual server, ICA Proxy, Clientless VPN (CVPN), RDP Proxy) or an AAA virtual server.

Cybersecurity researcher [Kevin Beaumont says](https://doublepulsar.com/citrixbleed-2-electric-boogaloo-cve-2025-5777-c7f5e349d206) the flaw echoes the infamous '[CitrixBleed](https://www.bleepingcomputer.com/news/security/citrix-bleed-exploit-lets-hackers-hijack-netscaler-accounts/)' vulnerability (CVE-2023-4966), which was extensively exploited by threat actors, including [ransomware](https://www.bleepingcomputer.com/news/security/lockbit-ransomware-exploits-citrix-bleed-in-attacks-10k-servers-exposed/) and [government attacks](https://www.bleepingcomputer.com/news/security/hackers-use-citrix-bleed-flaw-in-attacks-on-govt-networks-worldwide/).

Beaumont characterized CVE-2025-5777 as '[CitrixBleed 2](https://doublepulsar.com/citrixbleed-2-electric-boogaloo-cve-2025-5777-c7f5e349d206),' stating that the flaw could allow attackers to potentially access session tokens, credentials, and other sensitive data from public-facing gateways and virtual servers.

Leaked tokens can be replayed to hijack user sessions and bypass multi-factor authentication (MFA).

The same security bulletin lists a second, high-severity flaw tracked as CVE-2025-5349.

This is an improper access control problem in the NetScaler Management Interface, exploitable if the attacker has access to the NSIP (NetScaler Management IP), Cluster Management IP, or Local GSLB Site IP.

To address both risks, users are recommended to install DC and NetScaler Gateway 14.1-43.56, 13.1-58.32 and later, 13.1-NDcPP 13.1-37.235 (FIPS), and 12.1-55.328 (FIPS).

While Citrix has not stated whether these flaws are being actively exploited, they do recommend that admins terminate all active ICA and PCoIP sessions as soon as all appliances have been updated. This advice was also given by Citrix regarding the original CitrixBleed flaws.

Before killing active sessions, admins should first review existing sessions for suspicious activity using the `show icaconnection` command and **NetScaler Gateway** \> **PCoIP** \> **Connections** to see PCoIP sessions.

After reviewing the active sessions, admins should then terminate them using these commands:

```
kill icaconnection -all
kill pcoipconnection -all
```

In a [LinkedIn post](http://www.linkedin.com/posts/charlescarmakal%5Fcritical-alert-multiple-critical-vulnerabilities-activity-7343669191331262464-v0i2?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAAI-3eQB8RXQZlUx64%5F6arOKR8IFUX8Mj5k), Mandiant CTO Charles Carmakal warns that it is essential to kill sessions after updating devices to prevent previously stolen sessions from being used even after devices are no longer vulnerable.

"Many organizations did not terminate sessions when remediating a similar vulnerability in 2023 (CVE-2023-4966 aka "Citrix Bleed")," warns Carmakal.

"In those cases, session secrets were stolen before companies patched, and the sessions were hijacked after the patch. Many of those compromises resulted in nation-state espionage or ransomware deployment."

The flaws also impact end-of-life ADC / Gateway 12.1 (non-FIPS) and ADC / Gateway 13.0, which will not be receiving patches. Those still using these versions should upgrade to an actively supported release as soon as possible.

Beaumont's internet scans return over 56,500 publicly exposed NetScaler ADC and Gateway endpoints, though what percentage of those are running versions vulnerable to CVE-2025-5349 and CVE-2025-5777 is unknown.