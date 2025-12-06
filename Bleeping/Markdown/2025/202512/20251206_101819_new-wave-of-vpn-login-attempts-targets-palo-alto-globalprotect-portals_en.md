# New wave of VPN login attempts targets Palo Alto GlobalProtect portals

![Palo Alto Networks](https://www.bleepstatic.com/content/hl-images/2024/04/16/Palo_Alto_Networks.jpg)

A campaign has been observed targeting Palo Alto GlobalProtect portals with login attempts and launching scanning activity against SonicWall SonicOS API endpoints.

The activity started on December 2nd and originated from more than 7,000 IP addresses from infrastructure operated by the German IT company 3xK GmbH, which runs its own BGP network (AS200373) and operates as a hosting provider.

Initially, the actor targeted GlobalProtect portals with bruteforce and login attempts, then pivoted to scanning SonicWall API endpoints, threat intelligence company GreyNoise says in a [report](https://www.greynoise.io/blog/hidden-pattern-credential-based-attacks-palo-alto-sonicwall) this week.

GlobalProtect is the VPN and remote access component of Palo Alto Networks’ firewall platform, used by large enterprises, government agencies, and service providers.

![Number of IP addresses driving the attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ips.jpg)

**Number of IP addresses driving the attacks**  
_Source: GreyNoise_

According to GreyNoise, the GlobalProtect login attempts targeted two profiles in the company's sensor network for passive capture of scanning and exploitation activity.

The researchers say that the surge used three client fingerprints previously observed in scanning attempts recorded between late September and mid-October.

This past activity originated from four ASNs with no history of malicious activity, generating over 9 million non-spoofable HTTP sessions, mostly targeting GlobalProtect portals.

In mid-November, GreyNoise also observed activity from 3xK Tech GmbH's infrastructure probing GlobalProtect VPN portals with 2.3 million scan sessions. Most of the attacking IPs (62%) were located in Germany, and used the same TCP/JA4t fingerprints.

Based on the analyzed indicators, the company confidently attributes both activities to the same actor.

On December 3, the same three fingerprints were seen in scanning activity targeting SonicWall SonicOS API.

![SonicWall scanning activity](https://www.bleepstatic.com/images/news/u/1220909/2025/December/sonicwall.jpg)

**SonicWall scanning activity**  
_Source: GreyNoise_

SonicOS is the operating system running on SonicWall firewalls, exposing API endpoints for configuration, remote management, and monitoring.

Malicious scanning targeting these endpoints is typically done to identify vulnerabilities and misconfigurations. GreyNoise has previously [noted](https://www.bleepingcomputer.com/news/security/spikes-in-malicious-activity-precede-new-cves-in-80-percent-of-cases/) that these scans may also help discover exposed infrastructure in preparation for potential exploitation of upcoming flaws.

For this reason, defenders are advised to monitor for IPs associated with this type of activity and block them.

It is also recommended to monitor authentication surfaces for abnormal velocity/repeated failures, track recurring client fingerprints, and use dynamic, context-aware blocking instead of static reputation lists.

BleepingComputer has contacted Palo Alto Networks and SonicWall about this activity.

Palo Alto Networks said that it detected increased scanning aimed at GlobalProtect interfaces, and confirmed that it "represents credential-based attacks, not an exploit of a software vulnerability."

"Furthermore, our internal telemetry and Cortex XSIAM protection confirm this activity does not constitute a compromise of our products or services," the company told BleepingComputer.

Palo Alto Networks recommends customers enforce Multi-Factor Authentication (MFA) to protect against credential abuse.