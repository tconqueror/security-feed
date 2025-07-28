# Microsoft: macOS Sploitlight flaw leaks Apple Intelligence data

![Apple](https://www.bleepstatic.com/content/hl-images/2025/07/28/Apple.jpg)

Attackers could use a recently patched macOS vulnerability to bypass Transparency, Consent, and Control (TCC) security checks and steal sensitive user information, including Apple Intelligence cached data.

TCC is a security technology and a privacy framework that blocks apps from accessing private user data by providing macOS control over how their data is accessed and used by applications across Apple devices.

Apple has [fixed the security flaw](https://support.apple.com/en-us/122373) tracked as CVE-2025-31199 (reported by Microsoft's Jonathan Bar Or, Alexia Wilson, and Christine Fossaceca) in patches released in March for macOS Sequoia 15.4 with "improved data redaction."

While Apple restricts TCC access only to apps with full disk access and automatically blocks unauthorized code execution, Microsoft security researchers found that attackers could use the privileged access of Spotlight plugins to access sensitive files and steal their contents.

They showed in a report published today that the vulnerability (named **Sploitlight** and described by Apple as a "logging issue") could be exploited to harvest valuable data, including Apple Intelligence-related information and remote information of other iCloud account-linked devices.

This includes, but is not limited to, photo and video metadata, precise geolocation data, face and person recognition data, user activity and event context, photo albums and shared libraries, search history and user preferences, as well as deleted photos and videos.

![Spoitlight exploit](https://www.bleepstatic.com/images/news/u/1109292/2025/Spoitlight-exploit.jpg)

_Spoitlight exploit (Microsoft)_

Since 2020, Apple has patched other TCC bypasses that exploit Time Machine mounts ([CVE-2020-9771](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-9771)), environment variable poisoning ([CVE-2020-9934](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-9934)), and a bundle conclusion issue ([CVE-2021-30713](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-30713))_. In the past, Microsoft security researchers have also discovered several other TCC bypasses, including [powerdir](https://www.bleepingcomputer.com/news/microsoft/microsoft-powerdir-bug-gives-access-to-protected-macos-user-data/) ([CVE-2021-30970](https://www.microsoft.com/security/blog/2022/01/10/new-macos-vulnerability-powerdir-could-lead-to-unauthorized-user-data-access/)) and [HM-Surf](https://www.microsoft.com/security/blog/2024/10/17/new-macos-vulnerability-hm-surf-could-lead-to-unauthorized-data-access/), that could also be abused to gain access to users' private data.

"While similar to prior TCC bypasses like HM-Surf and powerdir, the implications of this vulnerability, which we refer to as 'Sploitlight' for its use of Spotlight plugins, are more severe due to its ability to extract and leak sensitive information cached by Apple Intelligence, such as precise geolocation data, photo and video metadata, face and person recognition data, search history and user preferences, and more," [Microsoft said](https://www.microsoft.com/en-us/security/blog/2025/07/28/sploitlight-analyzing-a-spotlight-based-macos-tcc-vulnerability/) on Monday.

"These risks are further complicated and heightened by the remote linking capability between iCloud accounts, meaning an attacker with access to a user's macOS device could also exploit the vulnerability to determine remote information of other devices linked to the same iCloud account."

In recent years, Microsoft security researchers have found multiple other severe macOS vulnerabilities, including a SIP bypass [dubbed 'Shrootless](https://www.bleepingcomputer.com/news/security/microsoft-shrootless-bug-lets-hackers-install-macos-rootkits/)' ([CVE-2021-30892](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-30892)), reported in 2021, which enables attackers to install rootkits on compromised Macs.

More recently, they discovered a SIP bypass [dubbed 'Migraine'](https://www.bleepingcomputer.com/news/security/microsoft-finds-macos-bug-that-lets-hackers-bypass-sip-root-restrictions/) ([CVE-2023-32369](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-32369)) and a security flaw [named Achilles](https://www.bleepingcomputer.com/news/security/microsoft-finds-macos-bug-that-lets-malware-bypass-security-checks/) ([CVE-2022-42821](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-42821)), which can be exploited to install malware using untrusted apps that bypass Gatekeeper execution restrictions.

Last year, they reported [another SIP bypass](https://www.bleepingcomputer.com/news/security/microsoft-macos-bug-lets-hackers-install-malicious-kernel-drivers/) flaw ([CVE-2024-44243](https://nvd.nist.gov/vuln/detail/CVE-2024-44243)) that lets threat actors deploy malicious kernel drivers by loading third-party kernel extensions.