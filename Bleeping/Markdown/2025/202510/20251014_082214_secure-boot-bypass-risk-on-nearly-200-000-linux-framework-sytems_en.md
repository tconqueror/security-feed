# Secure Boot bypass risk on nearly 200,000 Linux Framework sytems

![Secure Boot bypass risk on nearly 200,000 Linux Framework sytems](https://www.bleepstatic.com/content/hl-images/2025/10/14/framework.jpg)

Around 200,000 Linux computer systems from American computer maker Framework were shipped with signed UEFI shell components that could be exploited to bypass Secure Boot protections.

An attacker could take advantage to load bootkits (e.g. [BlackLotus](https://www.bleepingcomputer.com/news/security/blacklotus-bootkit-bypasses-uefi-secure-boot-on-patched-windows-11/), [HybridPetya](https://www.bleepingcomputer.com/news/security/new-hybridpetya-ransomware-can-bypass-uefi-secure-boot/), and [Bootkitty](https://www.bleepingcomputer.com/news/security/bootkitty-uefi-malware-exploits-logofail-to-infect-linux-systems/)) that can evade OS-level security controls and persist across OS re-installs.

### Powerful _mm_ command

According to firmware security company Eclypsium, the problem stems from including a 'memory modify' (_mm_) command in legitimately signed UEFI shells that Framework shipped with its systems.

The command provides direct read/write access to system memory and is intended for low-level diagnostics and firmware debugging. However, it can also be leveraged to break the Secure Boot trust chain by targeting the gSecurity2 variable, a critical component in the process of verifying the signatures of UEFI modules.

The _mm_ command can be abused to overwrite gSecurity2 with NULL, effectively disabling signature verification.

"Once the address is identified, the mm command can overwrite the security handler pointer with NULL or redirect it to a function that always returns "success" without performing any verification," - [Eclypsium](https://eclypsium.com/blog/bombshell-the-signed-backdoor-hiding-in-plain-sight-on-framework-devices/)

"This command writes zeros to the memory location containing the security handler pointer, effectively disabling signature verification for all subsequent module loads."

The researchers also note that the attack can be automated via startup scripts to persist across reboots.

### Around 200,000 systems impacted

Framework is a US-based hardware company known for designing modular and easily repairable laptops and desktops.

The presence of the risky _mm_ command is not the result of a compromise but appears more of an oversight. After learning of the issue, Framework started to work on remediating the vulnerabilities.

Eclypsium researchers estimates that the problem has impacted roughly 200,000 Framework computers:

* Framework 13 (11th Gen Intel), fix planned in 3.24
* Framework 13 (12th Gen Intel), fixed in 3.18, DBX update planned in 3.19
* Framework 13 (13th Gen Intel), fixed in 3.08, DBX update issued in 3.09
* Framework 13 (Intel Core Ultra), fixed in 3.06
* Framework 13 (AMD Ryzen 7040), fixed in 3.16
* Framework 13 (AMD Ryzen AI 300), fixed in 3.04, DBX update planned in 3.05
* Framework 16 (AMD Ryzen 7040), fixed in 3.06 (Beta), DBX update issued in 3.07
* Framework Desktop (AMD Ryzen AI 300 MAX), fixed in 3.01, DBX update planned in 3.03

Impacted users are recommended to apply the available security updates. Where a patch isn't available yet, secondary protection measures like physical access prevention is crucial. Another temporary mitigation is to delete Framework's DB key via the BIOS.