# Hackers abuse IPv6 networking feature to hijack software updates

![Malware](https://www.bleepstatic.com/content/hl-images/2022/05/05/malware-header.jpg)

A China-aligned APT threat actor named "TheWizards" abuses an IPv6 networking feature to launch adversary-in-the-middle (AitM) attacks that hijack software updates to install Windows malware.

According to ESET, the group has been active since at least 2022, targeting entities in the Philippines, Cambodia, the United Arab Emirates, China, and Hong Kong. Victims include individuals, gambling companies, and other organizations.

The attacks utilize a custom tool dubbed "Spellbinder" by ESET that abuses the IPv6 Stateless Address Autoconfiguration (SLAAC) feature to conduct [SLACC attacks](https://wirewatcher.wordpress.com/2011/04/04/the-slaac-attack-using-ipv6-as-a-weapon-against-ipv4/).

SLAAC is a feature of the IPv6 networking protocol that allows devices to automatically configure their own IP addresses and default gateway without needing a DHCP server. Instead, it utilizes Router Advertisement (RA) messages to receive IP addresses from IPv6-supported routers.

The hacker's Spellbinder tool abuses this feature by sending spoofed RA messages over the network, causing nearby systems to automatically receive a new IPv6 IP address, new DNS servers, and a new, preferred IPv6 gateway.

This default gateway, though, is the IP address of the Spellbinder tool, which allows it to intercept communications and reroute traffic through attacker-controlled servers.

"Spellbinder sends a multicast RA packet every 200 ms to ff02::1 ("all nodes"); Windows machines in the network with IPv6 enabled will autoconfigure via [stateless address autoconfiguration](https://www.rfc-editor.org/rfc/rfc4862) (SLAAC) using information provided in the RA message, and begin sending IPv6 traffic to the machine running Spellbinder, where packets will be intercepted, analyzed, and replied to where applicable," explains ESET.

![Abusing IPv6 SLAAC using the Spellbinder tool](https://www.bleepstatic.com/images/news/security/malware/s/spellbinder/figure-4%5B1%5D.png)

**Abusing IPv6 SLAAC using the Spellbinder tool**  
_Source: ESET_

ESET said attacks deploy Spellbinder using an archive named AVGApplicationFrameHostS.zip, which extracts into a directory mimicking legitimate software: "%PROGRAMFILES%\\AVG Technologies."

Within this directory are AVGApplicationFrameHost.exe, wsc.dll, log.dat, and a legitimate copy of winpcap.exe. The WinPcap executable is used to side-load the malicious wsc.dll, which loads Spellbinder into memory.

Once a device is infected, Spellbinder begins capturing and analyzing network traffic attempting to connect specific domains, such as those related to Chinese software update servers.

ESET says the malware monitors for domains belonging to the following companies: Tencent, Baidu, Xunlei, Youku, iQIYI, Kingsoft, Mango TV, Funshion, Yuodao, Xiaomi, Xiaomi Miui, PPLive, Meitu, Quihoo 360, and Baofeng.

The tool then redirects those requests to download and install malicious updates that deploy a backdoor named "WizardNet."

The WizardNet backdoor gives attackers persistent access to the infected device and allows them to install additional malware as needed.

To protect against these types of attacks, organizations can monitor IPv6 traffic or turn off the protocol if it is not required in their environment.

In January, ESET also reported on another hacking group named "Blackwood" [hijacking the WPS Office software update feature](https://www.bleepingcomputer.com/news/security/blackwood-hackers-hijack-wps-office-update-to-install-malware/) to install malware.