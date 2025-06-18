# New Linux udisks flaw lets attackers get root on major Linux distros

![Linux](https://www.bleepstatic.com/content/hl-images/2024/05/31/Linux.jpg)

Attackers can exploit two newly discovered local privilege escalation (LPE) vulnerabilities to gain root privileges on systems running major Linux distributions.

The first flaw (tracked as [CVE-2025-6018](https://security-tracker.debian.org/tracker/CVE-2025-6018)) was found in the configuration of the Pluggable Authentication Modules (PAM) framework on openSUSE Leap 15 and SUSE Linux Enterprise 15, allowing local attackers to gain the privileges of the "allow_active" user.

The other security bug ([CVE-2025-6019](https://security-tracker.debian.org/tracker/CVE-2025-6019)) was discovered in libblockdev, and it enables an "allow_active" user to gain root permissions via the udisks daemon (a storage management service that runs by default on most Linux distributions).

While successfully abusing the two flaws as part of a "local-to-root" chain exploit can let attackers quickly gain root and completely take over a SUSE system, the libblockdev/udisks flaw is also extremely dangerous on its own.

"Although it nominally requires 'allow_active' privileges, udisks ships by default on almost all Linux distributions, so nearly any system is vulnerable," [said](https://blog.qualys.com/vulnerabilities-threat-research/2025/06/17/qualys-tru-uncovers-chained-lpe-suse-15-pam-to-full-root-via-libblockdev-udisks) Qualys TRU senior manager Saeed Abbasi.

"Techniques to gain 'allow_active,' including the PAM issue disclosed here, further negate that barrier. An attacker can chain these vulnerabilities for immediate root compromise with minimal effort."

The Qualys Threat Research Unit (TRU), which discovered and reported both flaws, has developed proof-of-concept exploits and successfully targeted CVE-2025-6019 to get root privileges on Ubuntu, Debian, Fedora, and openSUSE Leap 15 systems.

## Admins urged to patch immediately

The Qualys Security Advisory team has shared more technical details regarding these two vulnerabilities [here](https://cdn2.qualys.com/2025/06/17/suse15-pam-udisks-lpe.txt) and linked to security patches in this [Openwall post](https://www.openwall.com/lists/oss-security/2025/06/17/5).

"Root access enables agent tampering, persistence, and lateral movement, so one unpatched server endangers the whole fleet. Patch both PAM and libblockdev/udisks everywhere to eliminate this path," Abbasi added.

"Given the ubiquity of udisks and the simplicity of the exploit, organizations must treat this as a **critical, universal risk and deploy patches without delay**."

In recent years, Qualys researchers have discovered several other Linux security vulnerabilities that let attackers hijack unpatched Linux systems, even in default configurations.

Security flaws they discovered include a flaw in Polkit's pkexec component ([dubbed PwnKit](https://www.bleepingcomputer.com/news/security/linux-system-service-bug-gives-root-on-all-major-distros-exploit-released/)), one in glibc's ld.so dynamic loader ([Looney Tunables](https://www.bleepingcomputer.com/news/security/new-looney-tunables-linux-bug-gives-root-on-major-distros/)), another in the Kernel's filesystem layer ([dubbed Sequoia](https://www.bleepingcomputer.com/news/security/new-linux-kernel-bug-lets-you-get-root-on-most-modern-distros/)), and one in the Sudo Unix program (aka [Baron Samedit](https://www.bleepingcomputer.com/news/security/new-linux-sudo-flaw-lets-local-users-gain-root-privileges/)).

Shortly after the Looney Tunables flaw was disclosed, proof-of-concept (PoC) exploits were [released online](https://www.bleepingcomputer.com/news/security/exploits-released-for-linux-flaw-giving-root-on-major-distros/). One month later, attackers [began exploiting it](https://www.bleepingcomputer.com/news/security/hackers-exploit-looney-tunables-linux-bug-steal-cloud-creds/) to steal cloud service provider (CSP) credentials using Kinsing malware.

Qualys also recently [found five LPE vulnerabilities](https://www.bleepingcomputer.com/news/security/ubuntu-linux-impacted-by-decade-old-needrestart-flaw-that-gives-root/) introduced over 10 years ago in the needrestart utility used by default in Ubuntu Linux 21.04 and later.