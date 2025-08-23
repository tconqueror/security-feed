# New Lenovo UEFI firmware updates fix Secure Boot bypass flaws

![Lenovo](https://www.bleepstatic.com/content/hl-images/2024/10/29/lenovo-logo.jpg)

Lenovo is warning of high-severity BIOS flaws that could let attackers bypass Secure Boot on all-in-one desktops using customized Insyde UEFI firmware.

Devices confirmed to be impacted are IdeaCentre AIO 3 24ARR9 and 27ARR9, and the Yoga AIO 27IAH10, 32ILL10, and 32IRH8.

UEFI is the modern replacement for the traditional PC BIOS, acting as a firmware interface between the computer's hardware and the OS, controlling early initialization and booting.

The flaws, discovered by Binarly, mirror those the researchers uncovered earlier this month, which impacted [dozens of Gigabyte motherboard models](https://www.bleepingcomputer.com/news/security/gigabyte-motherboards-vulnerable-to-uefi-malware-bypassing-secure-boot/), enabling local attackers to execute arbitrary code in System Management Mode (SMM).

The SMM is a CPU mode that is separate from the operating system (OS) and hypervisor, running with higher privileges at a lower level (Ring-2). Exploiting flaws in SMM could help attackers plant 'undetectable' malware, bypassing OS-level security defenses, such as SecureBoot.

InsydeH2O is one of the most widely deployed commercial UEFI BIOS frameworks used in OEM laptops and desktops.

Insyde also [published a bulletin](https://www.insyde.com/security-pledge/sa-2025007) explaining that the flaws arise from OEM-specific customizations made by Lenovo in InsydeH2O UEFI firmware images, and do not apply to all systems using InsydeH2O UEFI.

"The newly identified Lenovo vulnerabilities arise from the same recurring challenges tied to inconsistencies within the software supply chain," commented Binarly's Alex Matrosov to BleepingComputer.

"All six vulnerabilities were found in System Management Mode (SMM)‑level code, the invisible layer of firmware that loads before your operating system and persists after every re‑image, making them perfect launch pads for stealthy implants and Secure Boot bypasses."

The six flaws are summarized as follows:

* **[CVE-2025-4421](https://www.binarly.io/advisories/brly-dva-2025-013)**: bug in an SMI handler (Callback7 via EfiSmiServices) allows an attacker to write to an attacker-controlled SMRAM address using an unvalidated RSI register, leading to SMM privilege escalation and persistent firmware compromise (CVSS score: 8.2)
* **[CVE-2025-4422](https://www.binarly.io/advisories/brly-2025-014)**: bug in an SMI handler (EfiSmiServices, via gEfiSmmCpuProtocol and EfiPcdProtocol) can lead to SMM memory corruption and privilege escalation. (CVSS score: 8.2)
* **[CVE-2025-4423](https://www.binarly.io/advisories/brly-dva-2025-015)**: bug in an SMI handler (SetupAutomationSmm) allows arbitrary memory writes in SMM, leading to SMM privilege escalation and code execution. (CVSS score: 8.2)
* **[CVE-2025-4424](https://www.binarly.io/advisories/brly-2025-017)**: improper input validation in an SMI handler (SetupAutomationSmm) allows unsanitized calls to SmmSetVariable, leading to firmware settings manipulation. (CVSS score: 6)
* **[CVE-2025-4425](https://www.binarly.io/advisories/brly-2025-016)**: stack buffer overflow in an SMI handler (SetupAutomationSmm) can lead to SMM privilege escalation and arbitrary code execution. (CVSS score: 8.2)
* **[CVE-2025-4426](https://www.binarly.io/advisories/brly-2025-018)**: bug in an SMI handler (SetupAutomationSmm) leaks SMRAM contents, enabling sensitive information disclosure. (CVSS score: 6)

Binarly reported the vulnerabilities to Lenovo on April 8, 2025, and received confirmation from the company on June 16\. The coordinated disclosure was published yesterday, following the expiration of the 90-day disclosure window.

Lenovo has [released firmware security updates](https://support.lenovo.com/us/en/product%5Fsecurity/LEN-201013) for IdeaCenter AIO 3 models, urging users to upgrade to version O6BKT1AA.

Yoga AIO updates aren't currently available, but the computer vendor plans to release fixes between September 30 and November 30, 2025.