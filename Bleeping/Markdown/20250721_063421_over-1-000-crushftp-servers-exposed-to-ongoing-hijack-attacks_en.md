# Over 1,000 CrushFTP servers exposed to ongoing hijack attacks

![CrushFTP](https://www.bleepstatic.com/content/hl-images/2024/04/19/CrushFTP_headpic.jpg)

Over 1,000 CrushFTP instances currently exposed online are vulnerable to hijack attacks that exploit a critical security bug, providing admin access to the web interface.

The security vulnerability ([CVE-2025-54309](https://nvd.nist.gov/vuln/detail/CVE-2025-54309)) is due to mishandled AS2 validation and impacts all CrushFTP versions below 10.8.5 and 11.3.4\_23\. The vendor [tagged the flaw as actively exploited](https://www.bleepingcomputer.com/news/security/new-crushftp-zero-day-exploited-in-attacks-to-hijack-servers/) in the wild on July 19th, noting that attacks may have begun earlier, although it has yet to find evidence to confirm this.

"July 18th, 9AM CST there is a 0-day exploit seen in the wild. Possibly it has been going on for longer, but we saw it then. Hackers apparently reverse engineered our code and found some bug which we had already fixed," reads [CrushFTP's advisory](https://www.crushftp.com/crush11wiki/Wiki.jsp?page=CompromiseJuly2025).

"They are exploiting it for anyone who has not stayed current on new versions. As always we recommend regularly and frequent patching. Anyone who had kept up to date was spared from this exploit."

However, CrushFTP added last week that servers that have been kept up to date are not vulnerable to attacks, stating that customers who use a demilitarized zone (DMZ) instance to isolate their main server aren't impacted by this vulnerability.

The company also recommends reviewing upload and download logs for unusual activity, as well as enabling automatic updates and whitelisting IPs for server and admin access to further mitigate exploitation attempts.

According to scans from the security threat monitoring platform Shadowserver, approximately 1,040 CrushFTP instances [remain unpatched against CVE-2025-54309](https://bsky.app/profile/shadowserver.bsky.social/post/3luhrfgevec24) and are vulnerable to attacks.

![Unpatched CrushFTP servers](https://www.bleepstatic.com/images/news/u/1109292/2025/CVE-2025-54309_exposure.jpg)

_Unpatched CrushFTP servers (Shadowserver)_

ShadowServer is [now notifying](https://x.com/Shadowserver/status/1874034572088033524) CrushFTP customers that their servers are unprotected against ongoing CVE-2025-54309 exploitation, exposing their contents to data theft attempts.

While it's unclear if these ongoing attacks deploy malware or were used for data theft, managed file transfer solutions like CrushFTP [have been high-value targets](https://www.bleepingcomputer.com/news/security/ransomware-attacks-now-target-unpatched-ws-ftp-servers/) for ransomware gangs in recent years.

For instance, the Clop cybercrime gang alone has been linked to multiple data theft campaigns targeting zero-day flaws in [Accelion FTA](https://www.bleepingcomputer.com/news/security/global-accellion-data-breaches-linked-to-clop-ransomware-gang/), [GoAnywhere MFT](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-it-breached-130-orgs-using-goanywhere-zero-day/), [MOVEit Transfer](https://www.bleepingcomputer.com/news/security/new-moveit-transfer-zero-day-mass-exploited-in-data-theft-attacks/), and, most recently, [Cleo](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-cleo-data-theft-attacks/) software.

One year ago, in April 2024, CrushFTP also [patched an actively exploited zero-day](https://www.bleepingcomputer.com/news/security/crushftp-warns-users-to-patch-exploited-zero-day-immediately/) (tracked as CVE-2024-4040) that allowed unauthenticated attackers to escape the user's virtual file system (VFS) and download system files.

At the time, the cybersecurity company CrowdStrike [found evidence](https://www.reddit.com/r/crowdstrike/comments/1c88788/situational%5Fawareness%5F20240419%5Fcrushftp%5Fvirtual/) that the attacks, which targeted CrushFTP instances at multiple U.S. organizations and focused on intelligence gathering, were likely politically motivated.