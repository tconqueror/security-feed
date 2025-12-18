# New password spraying attacks target Cisco, PAN VPN gateways

![New password spraying attacks target Cisco, PAN VPN gateways](https://www.bleepstatic.com/content/hl-images/2025/11/05/Credit-card-hacker.jpg)

An automated campaign is targeting multiple VPN platforms, with credential-based attacks being observed on Palo Alto Networks GlobalProtect and Cisco SSL VPN.

On December 11, threat monitoring platform GreyNoise observed the number of login attempts aimed at GlobalProtect portals peaked at 1.7 million during a period of 16 hours.

Collected data showed that the attacks originated from more than 10,000 unique IP addresses and were aimed at infrastructure located in the United States, Mexico, and Pakistan.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

The malicious traffic originated almost entirely from the 3xK GmbH (Germany) IP space, indicating a centralized cloud infrastructure.

Based on researchers' observations, the threat actor reused common username and password combinations, and most of the requests were from a Firefox user agent that is uncommon for automated login activity through this provider.

"The consistency of the user agent, request structure, and timing suggests scripted credential probing designed to identify exposed or weakly protected GlobalProtect portals, rather than interactive access attempts or vulnerability exploitation," [GreyNoise explains](https://www.greynoise.io/blog/credential-based-campaign-cisco-palo-alto-networks-vpn-gateways).

“This activity reflects continued pressure against enterprise VPN authentication endpoints, a pattern GreyNoise has observed repeatedly during periods of heightened attacker activity.”

![Activity targeting GlobalProtect portals](https://www.bleepstatic.com/images/news/u/1220909/2025/December/globalprotect.jpg)

**Activity targeting GlobalProtect portals**  
_Source: GreyNoise_

On December 12, activity originating from the same hosting provider using the same TCP fingerprint started to probe Cisco SSL VPN endpoints.

GreyNoise monitors recorded a jump of unique attack IPs to 1,273, from the normal baseline of less than 200.

The activity constitutes the first large-scale use of 3xK-hosted IPs against Cisco SSL VPNs in the past 12 weeks.

In this case, too, the login payloads followed normal SSL VPN authentication flows, including CSRF handling, indicating automated credential attacks rather than exploits.

**Number of IP probing Cisco SSL VPN endpoints**  
_Source: GreyNoise_

Yesterday, Cisco warned customers of a maximum-severity zero-day vulnerability (CVE-2025-20393) in Cisco AsyncOS that is [actively exploited in attacks](https://www.bleepingcomputer.com/news/security/cisco-warns-of-unpatched-asyncos-zero-day-exploited-in-attacks/) targeting Secure Email Gateway (SEG) and Secure Email and Web Manager (SEWM) appliances.

However, GreyNoise underlines that it found no evidence linking the observed activity to CVE-2025-20393.

A Palo Alto Networks spokesperson confirmed to BleepingComputer that they are aware of the activity. The company recommends users to use strong passwords and multi-factor authentication protection.

“We are aware of the credential-based activity reported by GreyNoise targeting VPN gateways, including GlobalProtect portals. This activity reflects automated credential probing and does not constitute a compromise of our environment or an exploitation of any Palo Alto Networks vulnerability," the Palo Alto Networks spokesperson said.

"Our investigation confirms that these are scripted attempts to identify weak credentials," they added.

Apart from the recommended Palo Alto Networks action, Grey Noise also advises administrators to audit network appliances, look for unexpected login attempts, and block known malicious IPs performing these probes.