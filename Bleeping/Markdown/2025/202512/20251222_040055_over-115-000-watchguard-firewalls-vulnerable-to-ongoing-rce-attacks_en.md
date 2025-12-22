# Critical RCE flaw impacts over 115,000 WatchGuard firewalls

![WatchGuard](https://www.bleepstatic.com/content/hl-images/2025/09/18/WatchGuard_headpic.jpg)

Over 115,000 WatchGuard Firebox devices exposed online remain unpatched against a critical remote code execution (RCE) vulnerability actively exploited in attacks.

The security flaw, tracked as [CVE-2025-14733](https://nvd.nist.gov/vuln/detail/CVE-2025-14733), affects Firebox firewalls running Fireware OS 11.x and later (including 11.12.4\_Update1), 12.x or later (including 12.11.5), and 2025.1 up to and including 2025.1.3.

Successful exploitation enables unauthenticated attackers to execute arbitrary code remotely on vulnerable devices, following low-complexity attacks that don't require user interaction.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

As WatchGuard explained in a Thursday advisory, when it [released CVE-2025-14733 security updates](https://www.bleepingcomputer.com/news/security/watchguard-warns-of-new-rce-flaw-in-firebox-firewalls-exploited-in-attacks/) and tagged it as exploited in the wild, unpatched Firebox firewalls are only vulnerable to attacks if configured for IKEv2 VPN. It also warned that even if vulnerable configurations are removed, the firewall may still be at risk if a Branch Office VPN (BOVPN) to a static gateway peer is still configured.

"WatchGuard Fireware OS iked process contains an out of bounds write vulnerability in the OS iked process," an [NVD advisory explains](https://nvd.nist.gov/vuln/detail/CVE-2025-14733). "This vulnerability may allow a remote unauthenticated attacker to execute arbitrary code and affects both the mobile user VPN with IKEv2 and the branch office VPN using IKEv2 when configured with a dynamic gateway peer."

WatchGuard has [shared indicators of compromise](https://www.watchguard.com/wgrd-psirt/advisory/wgsa-2025-00027#:~:text=Indicators%20of%20Attack) to help customers identify compromised Firebox appliances on their network, advising those who find signs of malicious activity to rotate all locally stored secrets on vulnerable firewalls. It also [provided a temporary workaround](http://techsearch.watchguard.com/KB?type=Article&SFDCID=kA1Vr000000DMXNKA4&lang=en%5FUS) for network defenders who can't immediately patch vulnerable devices, requiring them to disable dynamic peer BOVPNs, add new firewall policies, and disable the default system policies that handle VPN traffic.

On Saturday, the Internet security watchdog group Shadowserver found [over 124,658 unpatched Firebox instances exposed online](https://bsky.app/profile/shadowserver.bsky.social/post/3majeq7gru22k), with 117,490 [still exposed](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2025-12-19&d2=2025-12-21&source=isakmp%5Fvulnerable&source=isakmp%5Fvulnerable6&tag=cve-2025-14733%2B&dataset=unique%5Fips&limit=100&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) on Sunday.

![WatchGuard firewall instances exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/WatchGuard%20firewalls%20exposed%20online.jpg)

_WatchGuard firewall instances exposed online (Shadowserver)_

​One day after WatchGuard released patches, CISA [added](https://www.cisa.gov/news-events/alerts/2025/12/19/cisa-adds-one-known-exploited-vulnerability-catalog) CVE-2025-14733 to its [Known Exploited Vulnerabilities (KEV) Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-14733).

The U.S. cybersecurity agency also ordered Federal Civilian Executive Branch (FCEB) agencies (executive branch non-military agencies, such as the Department of Energy, the Department of the Treasury, and the Department of Homeland Security) to patch Firebox firewalls within a week, by December 26th, as mandated by the Binding Operational Directive (BOD) 22-01.

"This type of vulnerability is a frequent attack vector for malicious cyber actors and poses significant risks to the federal enterprise," CISA warned. "Apply mitigations per vendor instructions, follow applicable BOD 22-01 guidance for cloud services, or discontinue use of the product if mitigations are unavailable."

In September, WatchGuard [patched an almost identical RCE vulnerability](https://www.bleepingcomputer.com/news/security/watchguard-warns-of-critical-vulnerability-in-firebox-firewalls/) (CVE-2025-9242) impacting Firebox firewalls. One month later, Shadowserver [found over 75,000 Firebox firewalls](https://www.bleepingcomputer.com/news/security/over-75-000-watchguard-security-devices-vulnerable-to-critical-rce/) vulnerable to CVE-2025-9242 attacks, most in North America and Europe, with CISA later tagging the security flaw as actively exploited in the wild and [ordering federal agencies](https://www.bleepingcomputer.com/news/security/cisa-warns-of-watchguard-firewall-flaw-exploited-in-attacks/) to secure their Firebox appliances from ongoing attacks.

Two years ago, CISA also ordered U.S. government agencies to patch another actively exploited WatchGuard flaw (CVE-2022-23176) [impacting Firebox and XTM firewall appliances](https://www.bleepingcomputer.com/news/security/cisa-warns-orgs-of-watchguard-bug-exploited-by-russian-state-hackers/).

WatchGuard works with over 17,000 security resellers and service providers to protect the networks of more than 250,000 small and mid-sized companies worldwide.