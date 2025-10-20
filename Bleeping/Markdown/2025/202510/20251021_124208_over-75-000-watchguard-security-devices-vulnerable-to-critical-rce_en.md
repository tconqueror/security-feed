# Over 75,000 WatchGuard security devices vulnerable to critical RCE

![Over 75,000 WatchGuard security devices vulnerable to critical RCE](https://www.bleepstatic.com/content/hl-images/2025/09/18/WatchGuard.jpg)

Nearly 76,000 WatchGuard Firebox network security appliances are exposed on the public web and still vulnerable to a critical issue (CVE-2025-9242) that could allow a remote attacker to execute code without authentication.

Firebox devices act as a central defense hub that controls traffic between internal and external networks, providing protection through policy management, security services, VPN, and real-time real-time visibility through WatchGuard Cloud.

Scans from The Shadowserver Foundation currently show that there are 75,835 [vulnerable Firebox appliances](https://x.com/Shadowserver/status/1979902019696509099) across the world, most of them in Europe and North America.

Specifically, the United States tops the list with 24,500 endpoints, followed by Germany (7,300), Italy (6,800), United Kingdom (5,400), Canada (4,100), and France (2,000).

[![Heatmap of vulnerable Firebox devices](https://www.bleepstatic.com/images/news/u/1220909/2025/October/map.jpg)](https://x.com/Shadowserver/status/1979902019696509099) 

**Heatmap of vulnerable Firebox devices**  
_Source: The Shadowserver Foundation_

WatchGuard [disclosed CVE-2025-9242](https://www.bleepingcomputer.com/news/security/watchguard-warns-of-critical-vulnerability-in-firebox-firewalls/) in a security bulletin on September 17 and rated the vulnerability with a critical-severity score of 9.3\. The security problem is an out-of-bounds write in the Fireware OS ‘iked’ process, which handles IKEv2 VPN negotiations.

The flaw can be exploited without authentication by sending specially crafted IKEv2 packets to vulnerable Firebox endpoints, forcing it to write data to unintended memory areas.

It only affects Firebox appliances that use IKEv2 VPNs with dynamic gateway peers, on versions 11.10.2 through 11.12.4\_Update1, 12.0 through 12.11.3, and 2025.1

The vendor suggested an upgrade to one of the following versions:

* 2025.1.1
* 12.11.4
* 12.5.13
* 12.3.1\_Update3 (B722811)

Users should know that version 11.x has reached end of support and will not receive security updates. The recommendation for them is to move to a version that is still supported.

For devices set up only with Branch Office VPNs to static gateway peers, the vendor points to the documentation for securing the connection using the IPSec and IKEv2 protocols as a temporary workaround.

On October 19, The Shadowserver Foundation detected 75,955 vulnerable Firebox firewalls. A spokesperson told BleepingComputer that the current scan is considered reliable, and the figures reflect real deployments and not honeypots, yet.

Although no active exploitation of CVE-2025-9242 has been reported yet, administrators who haven’t applied the security updates are strongly advised to install the patch as soon as possible.