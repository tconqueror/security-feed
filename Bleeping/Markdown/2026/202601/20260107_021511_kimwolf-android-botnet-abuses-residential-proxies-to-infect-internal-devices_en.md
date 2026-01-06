# Kimwolf Android botnet abuses residential proxies to infect internal devices

![Kimwolf Android botnet abuses residential proxies to infect internal devices](https://www.bleepstatic.com/content/hl-images/2024/09/12/android-tv-malware.jpg)

The Kimwolf botnet, an Android variant of the Aisuru malware, has grown to more than two million hosts, most of them infected by exploiting vulnerabilities in residential proxy networks to target devices on internal networks.

Researchers observed increased activity for the malware since last August. Over the past month, Kimwolf has intensified its scanning of proxy networks, searching for devices with exposed Android Debug Bridge (ADB) services.

Common targets are Android-based TV boxes and streaming devices that allow unauthenticated access over ADB. Compromised devices are primarily used in distributed denial-of-service (DDoS) attacks, proxy resale, and monetizing app installations via third-party SDKs like Plainproxies Byteconnect.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

The Aisuru botnet is currently responsible for the largest DDoS attack publicly disclosed, which peaked at [29.7 terabits per second](https://www.bleepingcomputer.com/news/security/aisuru-botnet-behind-new-record-breaking-297-tbps-ddos-attack/) as measured by Cloudflare.

A report from [XLab notes](https://blog.xlab.qianxin.com/kimwolf-botnet-en/) that the Kimwolf Android botnet had more than 1.8 million compromised devices on December 4.

Researchers at threat intelligence and anti-fraud cybersecurity company Synthient have been tracking Kimwolf activity. They say that the number of compromised devices has climbed to nearly two million, and produced around 12 million unique IP addresses each week.

Most of the infected Android devices are in Vietnam, Brazil, India, and Saudi Arabia. In many cases, the systems were compromised by proxy SDKs before purchase, which was [reported in the past](https://www.bleepingcomputer.com/news/security/android-tv-box-on-amazon-came-pre-installed-with-malware/).

![Kimwolf infection heatmap](https://www.bleepstatic.com/images/news/u/1220909/2026/January/map.jpg)

**Kimwolf infections heatmap**  
_Source: Synthient_

### Abusing residential proxies

According to Synthient, Kimwolf’s rapid growth is largely due to its abuse of residential proxy networks to reach vulnerable Android devices. Specifically, the malware takes advantage of proxy providers that permit access to local network addresses and ports, allowing direct interaction with devices running on the same internal network as the proxy client.

Starting on November 12, 2025, Synthient observed elevated activity scanning for unauthenticated ADB services exposed through proxy endpoints, targeting ports 5555, 5858, 12108, and 3222.

The Android Debug Bridge (ADB) is a development and debugging interface that allows installing and removing apps, running shell commands, transferring files, and debugging Android devices. When exposed over a network, ADB can allow unauthorized remote connections to modify or take control of Android devices.

When reachable, botnet payloads were delivered via _netcat_ or _telnet_, piping shell scripts directly into the exposed device for local execution, written to _/data/local/tmp_.

Synthient captured multiple payload variants throughout December, but the delivery methods remained unchanged.

**Infection overview**  
_Source: Synthient_

The researchers found high exposure rates in one sample residential proxy pool, underscoring that such devices can be exploited within minutes of joining these networks.

"Upon analyzing exposed devices part of IPIDEAs proxy pool, we found that 67% of all Android devices are unauthenticated, leaving them vulnerable to remote code execution," [Synthient explains](https://synthient.com/blog/a-broken-system-fueling-botnets).

"From our scans, we found approximately 6 million vulnerable IPs \[…\] These devices are often shipped pre-infected with SDKs from proxy providers," the researchers say.

IPIDEA, one of the impacted proxy providers and a top Kimwolf target because it enabled access to all ports, responded to Synthient’s alert on December 28 by blocking access to local networks and a broad range of ports.

In total, the researchers sent almost a dozen vulnerability reports "to the top proxy providers" observed in Kimwolf activity. However, researchers cannot confidently determine all the proxy providers targeted by the malware.

### Protecting against Kimwolf

Synthient has published an [online scanner tool](https://synthient.com/check) to help users identify if any of their network devices are part of the Kimwolf botnet.

In the case of a positive result, the researchers suggest that infected TV boxes should be "wiped or destroyed," otherwise the botnet will persist.

The general recommendation is to avoid [low-cost](https://www.bleepingcomputer.com/news/security/mirai-variant-infects-low-cost-android-tv-boxes-for-ddos-attacks/) generic [Android TV boxes](https://www.bleepingcomputer.com/news/security/fbi-badbox-20-android-malware-infects-millions-of-consumer-devices/) and to prefer ‘Google Play Protect certified’ devices from reputable OEMs, such as Google’s Chromecast, NVIDIA Shield TV, and Xiaomi Mi TV Box.