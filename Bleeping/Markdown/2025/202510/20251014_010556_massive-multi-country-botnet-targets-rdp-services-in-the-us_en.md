# Massive multi-country botnet targets RDP services in the US

![Massive multi-country botnet targets RDP services in the US](https://www.bleepstatic.com/content/hl-images/2023/11/01/botnet-kill-switch.jpg)

A large-scale botnet is targeting Remote Desktop Protocol (RDP) services in the United States from more than 100,000 IP addresses.

The campaign started on October 8 and based on the source of the IPs, researchers believe the attacks are launched by a multi-country botnet.

RDP is a network protocol that enables remote connection and control of Windows systems. It is typically used by administrators, helpdesk staff, and remote workers.

Attackers often scan for open RDP ports or try to brute-force logins, exploit vulnerabilities, or perform timing attacks.

In this case, researchers at threat monitoring platform GreyNoise found that the botnet relies on two types of RDP-related attacks:

1. **RD Web Access timing attacks** – Probes RD Web Access endpoints and measures response-time differences during anonymous authentication flows to infer valid usernames
2. **RDP web client login enumeration** – Interacts with the RDP Web Client login flow to enumerate user accounts by observing the difference in server behavior and responses

GreyNoise detected the campaign after an unusual traffic spike from Brazil, followed by similar activity from a wider geography, which includes Argentina, Iran, China, Mexico, Russia, South Africa, and Ecuador.

The company says that the full list of countries with compromised devices in the botnet exceeds 100.

![Unusual activity spike from Brazil](https://www.bleepstatic.com/images/news/u/1220909/2025/October/brazilspike.jpg)

**Unusual activity spike from Brazil**  
_Source: GreyNoise_

Nearly all IP addresses share a common TCP fingerprint, and although there are variations in the (Maximum Segment Size), the [researchers believe](https://www.greynoise.io/blog/botnet-launches-coordinated-rdp-attack-wave) that these are due to the clusters forming the botnet.

To defend against this activity, system administrators are recommended to block the IP addresses that launch the attacks and to check the logs for suspicious RDP probing.

As a general recommendation, a remote desktop connection should not be exposed to the public internet and [adding a VPN](https://learn.microsoft.com/en-us/windows-server/remote/remote-desktop-services/remotepc/remote-desktop-allow-outside-access?source=recommendations#use-a-vpn) and multi-factor authentication ([MFA](https://learn.microsoft.com/en-us/windows-server/remote/remote-desktop-services/rds-plan-mfa)) adds a layer of protection.