# Botnet hacks 9,000+ ASUS routers to add persistent SSH backdoor

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

Over 9,000 ASUS routers are compromised by a novel botnet dubbed "AyySSHush" that was also observed targeting SOHO routers from Cisco, D-Link, and Linksys.

The campaign was [discovered by GreyNoise](https://www.greynoise.io/blog/stealthy-backdoor-campaign-affecting-asus-routers) security researchers in mid-March 2025, who reports that it carries the hallmarks of a nation-state threat actor, though no concrete attributions were made.

The threat monitoring firm reports that the attacks combine brute-forcing login credentials, bypassing authentication, and exploiting older vulnerabilities to compromise ASUS routers, including the RT-AC3100, RT-AC3200, and RT-AX55 models.

![Observed brute-forcing attempts](https://www.bleepstatic.com/images/news/u/1220909/2025/May/bruteforce.jpg)

**Observed brute-forcing attempts**  
_Source: GreyNoise_

Specifically, the attackers exploit an old command injection flaw tracked as [CVE-2023-39780](https://nvd.nist.gov/vuln/detail/CVE-2023-39780) to add their own SSH public key and enable the SSH daemon to listen on the non-standard TCP port 53282. This modifications allow the threat actors to retain backdoor access to the device even between reboots and firmware updates.

"Because this key is added using the official ASUS features, this config change is persisted across firmware upgrades," explains another [related report](http://www.labs.greynoise.io/grimoire/2025-03-28-ayysshush/) by GreyNoise.

"If you've been exploited previously, upgrading your firmware will **NOT** remove the SSH backdoor."

The attack is particularly stealthy, involving no malware, while the attackers also turn off logging and Trend Micro's AiProtection to evade detection.

Characteristically, GreyNoise reports logging just 30 malicious requests associated with this campaign over the past three months, though 9,000 ASUS routers have been infected.

![Malicious requests targeting ASUS routers](https://www.bleepstatic.com/images/news/u/1220909/2025/May/timeline(1).jpg)

**Malicious requests targeting ASUS routers**  
_Source: GreyNoise_

Still, three of those requests were enough to trigger GreyNoise's AI-powered analysis tool that flagged them for human inspection.

The campaign likely overlaps with the activity Sekoia tracks as "[Vicious Trap](https://blog.sekoia.io/vicioustrap-infiltrate-control-lure-turning-edge-devices-into-honeypots-en-masse/)," disclosed last week, though the French cybersecurity firm reported that threat actors leveraged CVE-2021-32030 to breach ASUS routers.

In the campaign seen by Sekoia, the threat actors were observed targeting SOHO routers, SSL VPNs, DVRs, and BMC controllers from D-Link, Linksys, QNAP, and Araknis Networks.

The exact operational goal of AyySSHush remains unclear, as there are no signs of distributed denial of service (DDoS) or using the devices to proxy malicious traffic through the ASUS routers.

However, in the router breaches observed by Sekoia, a malicious script was downloaded and executed to redirect network traffic from the compromised system to third-party devices controlled by the attacker.

Currently, it appears the campaign quietly builds a network of backdoored routers to create the groundwork for a future botnet.

## Protect your ASUS routers

ASUS has released security updates that address CVE-2023-39780 for the impacted routers, though the exact time of availability varies per model.

Users are recommended to upgrade their firmware as soon as possible and look for suspicious files and the addition of the attacker's SSH key ([IoCs here](https://www.labs.greynoise.io/grimoire/2025-03-28-ayysshush/)) on the 'authorized\_keys' file.

Also, GreyNoise lists four IP addresses associated with this activity, which should be added to a block list.

```
101.99.91[.]151
101.99.94[.]173 
79.141.163[.]179   
111.90.146[.]237
```

If a compromise is suspected, a factory reset is recommended to clean the router beyond doubt and then reconfigure it from scratch using a strong password.