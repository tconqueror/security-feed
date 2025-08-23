# Ivanti Workspace Control hardcoded key flaws expose SQL credentials

![Ivanti](https://www.bleepstatic.com/content/hl-images/2024/04/03/Ivanti.jpg)

Ivanti has released security updates to fix three high-severity hardcoded key vulnerabilities in the company's Workspace Control (IWC) solution.

IWC helps enterprise admins manage desktops and applications, acting as an intermediary between the operating system and users and regulating access and workspace configuration.

It provides centralized control over user workspaces and dynamically configures desktops, applications, and user settings based on policies and user roles.

All three security bugs are caused by the use of a hard-coded, unchangeable cryptographic key, and they can lead to privilege escalation and system compromise following successful exploitation and depending on the account targeted during a potential attack.

Two security flaws (CVE-2025-5353 and CVE-2025-22455) allow local authenticated attackers to decrypt stored SQL credentials on systems running IWC version 10.19.0.0 and earlier. The third vulnerability patched today (CVE-2025-22463) also enables local authenticated attackers to decrypt the stored environment password.

"Ivanti has released updates for Ivanti Workspace Control which address three high severity vulnerabilities. Successful exploitation could lead to credential compromise," the company [said](http://forums.ivanti.com/s/article/Security-Advisory-Ivanti-Workspace-Control-CVE-2025-5353-CVE-CVE-2025-22463-CVE-2025-22455?language=en%5FUS) today.

| **Product**                    | **Affected versions** | **Resolved versions** | **Patch**                                                                                                                                                                   |
| ------------------------------ | --------------------- | --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ivanti Workspace Control (IWC) | 10.19.0.0 and prior   | 10.19.10.0            | [Download Link](https://download.ivanti.com/downloads/RES/Ivanti%20Workspace%20Control/Ivanti%5FWorkspace%5FControl%5F10.19.10.0.zip "Ivanti Workspace Control 10.19.10.0") |

## No active exploitation in the wild

Luckily, the company has yet to find evidence that these vulnerabilities have been targeted in attacks before being disclosed.

"We are not aware of any customers being exploited by these vulnerabilities prior to public disclosure. These vulnerabilities were disclosed through our responsible disclosure program," Ivanti added.

Ivanti previously announced that IWC will [reach the end of life](https://forums.ivanti.com/s/article/Product-Life-Cycle-Policy-for-Ivanti-Workspace-Control-formerly-RES-ONE-Workspace-and-VDX?language=en%5FUS#:~:text=58%3A18%20AM-,Ivanti%20Workspace%20Control%20and%20Ivanti%20Virtual%20Desktop%20Extender,Life%20Date%3A%20December%2031%2C%202026) in December 2026, after which security patches and technical support will no longer be available.

In May, the company also [fixed a critical authentication bypass vulnerability](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-critical-neurons-for-itsm-auth-bypass-flaw/) in the Neurons for ITSM IT service management solution and two zero-day flaws in the Endpoint Manager Mobile (EPMM) software [chained in remote code execution attacks](https://www.bleepingcomputer.com/news/security/ivanti-fixes-epmm-zero-days-chained-in-code-execution-attacks/).

One of the zero-days (a remote code execution flaw tracked as CVE-2025-4428) [was exploited by Chinese hackers](https://www.bleepingcomputer.com/news/security/ivanti-epmm-flaw-exploited-by-chinese-hackers-to-breach-govt-agencies/) to breach government agencies and high-profile organizations worldwide.

One month earlier, Ivanti [patched a critical Connect Secure zero-day](https://www.bleepingcomputer.com/news/security/ivanti-patches-connect-secure-zero-day-exploited-since-mid-march/) exploited by a China-linked espionage group (UNC5221) in remote code execution attacks to deploy malware since mid-March 2025.