# Malicious 7-Zip site distributes installer laced with proxy tool

![Malicious 7-zip site pushes malware that turns devices into proxies](https://www.bleepstatic.com/content/hl-images/2025/02/04/7-zip-red-bright.jpg)

A fake 7-Zip website is distributing a trojanized installer of the popular archiving tool that turns the user’s computer into a residential proxy node.

Residential proxy networks use home user devices to route traffic with the goal of evading blocks and performing various malicious activities such as [credential stuffing](https://www.bleepingcomputer.com/news/security/fbi-warns-of-residential-proxies-used-in-credential-stuffing-attacks/), phishing, and malware distribution.

The new campaign became better known after a [user reported](https://www.malwarebytes.com/blog/threat-intel/2026/02/fake-7-zip-downloads-are-turning-home-pcs-into-proxy-nodes) that they downloaded a malicious installer from a website impersonating the 7-Zip project while following instructions in a YouTube tutorial on building a PC system. BleepingComputer can confirm that the malicious website, 7zip\[.\]com, is still live.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices) 

The threat actor registered the domain _7zip\[.\]com_ (still live at the time of writing) that can easily trick users into thinking they landed on the site of the legitimate tool.

Furthermore, the attacker copied the text and mimicked the structure of the original 7-Zip website located at 7-zip.org.

![Malicious website dropping the trojanized 7-Zip](https://www.bleepstatic.com/images/news/u/1220909/2026/February/site.jpg)

**Malicious website dropping the trojanized 7-Zip**  
_Source: BleepingComputer_

The installer file was [analyzed by researchers](https://www.malwarebytes.com/blog/threat-intel/2026/02/fake-7-zip-downloads-are-turning-home-pcs-into-proxy-nodes) at cybersecurity company Malwarebytes, who found that it is digitally signed with a now-revoked certificate originally issued to Jozeal Network Technology Co., Limited.

The malicious copy also contains the 7-Zip program, thus providing the regular functions of the tool. However, the installer drops three malicious files:

1. **Uphero.exe** – service manager and update loader
2. **hero.exe** – main proxy payload
3. **hero.dll** – support library

These files are placed in the ‘C:\\Windows\\SysWOW64\\hero\\’ directory, and an auto-start Windows service running as SYSTEM is created for the two malicious executables.

Additionally, firewall rules are modified using ‘netsh’ to allow the binaries to establish inbound and outbound connections.

Eventually, the host system is profiled with Microsoft's Windows Management Instrumentation (WMI) and Windows APIs to determine the hardware, memory, CPU, disk, and network characteristics. The collected data is then sent to _‘iplogger\[.\]org.’_

"While initial indicators suggested backdoor‑style capabilities, further analysis revealed that the malware’s primary function is proxyware," Malwarebytes explains about the malware’s operational goal.

“The infected host is enrolled as a residential proxy node, allowing third parties to route traffic through the victim’s IP address.”

According to the analysis, _hero.exe_ pulls config from rotating “smshero”-themed C2 domains, then opens outbound proxy connections on non-standard ports such as 1000 and 1002\. Control messages are obfuscated using a lightweight XOR key.

Malwarebytes found that the campaign is larger than the 7-Zip lure and also uses trojanized installers for HolaVPN, TikTok, WhatsApp, and Wire VPN.

The malware uses a rotating C2 infrastructure built around hero/smshero domains, with traffic going through the Cloudflare infrastructure and carried over TLS-encrypted HTTPs.

It also relies on DNS-over-HTTPS via Google’s resolver, which reduces visibility for defenders monitoring standard DNS traffic.

The malware also checks for virtualization platforms such as VMware, VirtualBox, QEMU, Parallels, as well as for debuggers, to identify when it’s being analyzed.

Malwarebytes' investigation started after noticing research from independent security researchers who analyzed the malware and uncovered its true purpose. Researcher [Luke Acha discovered](https://blog.lukeacha.com/2026/01/beware-of-fake-7zip-installer-upstage.html) the purpose of the Uphero/hero malware.

The xor-based communication protocol was reverse-engineered and decoded by [s1dhy](https://x.com/s1dhy/status/2016095714405687542), who confirmed the proxy behavior. Digital forensics and incident response (DFIR) engineer [Andrew Danis](https://x.com/andrewdanis/status/2012366129746911396) connected the fake 7-Zip installer to the larger campaign impersonating multiple software brands.

Malwarebytes lists indicators of compromise (domains, file paths, IP addresses) and host-related data observed during their analysis.

Users are recommended to avoid following URLs from YouTube videos or promoted search results, and instead bookmark the download portal domains for the software they use often.