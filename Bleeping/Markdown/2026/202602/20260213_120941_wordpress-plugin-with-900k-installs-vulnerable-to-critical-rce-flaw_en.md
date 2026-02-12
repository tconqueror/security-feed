# WordPress plugin with 900k installs vulnerable to critical RCE flaw

![WordPress plugin with 900k installs vulnerable to critical RCE flaw](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

A critical vulnerability in the WPvivid Backup & Migration plugin for WordPress, installed on more than 900,000 websites, can be exploited to achieve remote code execution by uploading arbitrary files without authentication.

The security issue is tracked as CVE-2026-1357 and received a severity score of 9.8\. It impacts all versions of the plugin up to 0.9.123 and could lead to a complete website takeover.

Despite the severity of the issue, researchers at WordPress security company Defiant say that only sites with the non-default “receive backup from another site” option enabled are critically impacted.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices) 

Furthermore, attackers have a 24-hour exploitation window, which is the validity of the generated key required by other sites to send backup files.

This requirement limits realistic exposure; however, the plugin is [commonly used](https://wordpress.org/plugins/wpvivid-backuprestore/#description) for site migrations and backup transfers between hosts, so website administrators are very likely to enable this feature at some point, at least temporarily.

Researcher Lucas Montes (NiRoX) reported the vulnerability to Defiant on January 12\. The root cause is the improper error handling in RSA decryption, combined with a lack of path sanitization.

Specifically, when the ‘_openssl\_private\_decrypt()_’ function fails, the plugin does not halt execution and instead passes the failed result (false) to the AES (Rijndael) routine.

The cryptographic library treats this as a string of null bytes, creating a predictable encryption key that an attacker can use to craft malicious payloads that the plugin would accept.

Additionally, the plugin failed to properly sanitize uploaded file names, allowing directory traversal. This allows writing files outside the intended backup directory and uploading malicious PHP files for remote code execution.

Defiant notified the vendor, WPVividPlugins, on January 22, following validation of the provided proof-of-concept exploit. A security update addressing [CVE-2026-1357](https://nvd.nist.gov/vuln/detail/CVE-2026-1357) was released in version 0.9.124 on January 28.

The fix includes adding a check to stop execution if RSA decryption fails, adding filename sanitization, and restricting uploads to allowed backup file types only, such as ZIP, GZ, TAR, and SQL.

Users of the WPvivid Backup & Migration WordPress plugin should be aware of the risks associated with the vulnerability and upgrade to version 0.9.124 as soon as possible.