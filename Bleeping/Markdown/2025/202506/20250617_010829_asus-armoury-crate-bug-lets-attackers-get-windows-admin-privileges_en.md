# ASUS Armoury Crate bug lets attackers get Windows admin privileges

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

A high-severity vulnerability in ASUS Armoury Crate software could allow threat actors to escalate their privileges to SYSTEM level on Windows machines.

The security issue is tracked as [CVE-2025-3464](https://nvd.nist.gov/vuln/detail/CVE-2025-3464) and received a severity score of 8.8 out of 10.

It could be exploited to bypass authorization and affects the AsIO3.sys of the Armoury Crate system management software.

Armoury Crate is the official system control software for Windows from ASUS, providing a centralized interface to control RGB lighting (Aura Sync), adjust fan curves, manage performance profiles and ASUS peripherals, as well as download drivers and firmware updates.

To perform all these functions and provide low-level system monitoring, the software suite uses the kernel driver to access and control hardware features.

Cisco Talos' researcher Marcin "Icewall" Noga reported CVE-2025-3464 to the tech company.

According to a [Talos advisory](https://talosintelligence.com/vulnerability%5Freports/TALOS-2025-2150), the issue lies in the driver verifying callers based on a hardcoded SHA-256 hash of AsusCertService.exe and a PID allowlist, instead of using proper OS-level access controls.

Exploiting the flaw involves creating a hard link from a benign test app to a fake executable. The attacker launches the app, pauses it, and then swaps the hard link to point to AsusCertService.exe. 

When the driver checks the file's SHA-256 hash, it reads the now-linked trusted binary, allowing the test app to bypass authorization and gain access to the driver.

This grants the attacker low-level system privileges, giving them direct access to physical memory, I/O ports, and model-specific registers (MSRs), opening the path to full OS compromise.

It is important to note that the attacker must already be on the system (malware infection, phishing, compromised unprivileged account) to exploit CVE-2025-3464.

However, the extensive deployment of the software on computers worldwide may represent an attack surface large enough for exploitation to become attractive.

Cisco Talos validated that CVE-2025-3464 impacts Armoury Crate version 5.9.13.0, but [ASUS' bulletin](https://www.asus.com/content/asus-product-security-advisory/) notes that the flaw impacts all versions between 5.9.9.0 and 6.1.18.0.

To mitigate the security problem, it is recommended to apply the latest update by opening the Armoury Crate app and going to "Settings"> "Update Center"> "Check for Updates"> "Update."

Cisco reported the flaw to ASUS in February but no exploitation in the wild has been observed so far. However, "ASUS strongly recommends that users update their Armoury Crate installation to the latest version."

Windows kernel driver bugs that lead to local privilege escalation are [popular among hackers](https://www.bleepingcomputer.com/news/security/windows-kernel-bug-fixed-last-month-exploited-as-zero-day-since-august/), including [ransomware actors](https://www.bleepingcomputer.com/news/security/ransomware-gangs-exploit-paragon-partition-manager-bug-in-byovd-attacks/), [malware operations](https://www.bleepingcomputer.com/news/security/new-steelfox-malware-hijacks-windows-pcs-using-vulnerable-driver/), and [threats to government agencies](https://www.bleepingcomputer.com/news/security/windows-kernel-bug-now-exploited-in-attacks-to-gain-system-privileges/).