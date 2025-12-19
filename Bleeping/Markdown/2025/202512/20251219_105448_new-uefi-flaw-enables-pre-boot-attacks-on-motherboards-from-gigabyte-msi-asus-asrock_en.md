# New UEFI flaw enables pre-boot attacks on motherboards from Gigabyte, MSI, ASUS, ASRock

![New UEFI flaw enables pre-boot attacks on motherboards from Gigabyte, MSI, ASUS, ASRock](https://www.bleepstatic.com/content/hl-images/2022/06/02/cpu-motherboard.jpg)

The UEFI firmware implementation in some motherboards from ASUS, Gigabyte, MSI, and ASRock is vulnerable to direct memory access (DMA) attacks that can bypass early-boot memory protections.

The security issue has received multiple identifiers (CVE-2025-11901, CVE-2025‑14302, CVE-2025-14303, and CVE-2025-14304) due to differences in vendor implementations

DMA is a hardware feature that allows devices such as graphics cards, Thunderbolt devices, and PCIe devices to read and write directly to RAM without involving the CPU.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

IOMMU is a hardware-enforced memory firewall that sits between devices and RAM, controlling which memory regions are accessible for each device.

During early boot, when UEFI firmware initializes, IOMMU must activate before DMA attacks are possible; otherwise, there is no protection in place to stop reading or writing on memory regions via physical access.

### Valorant not launching on vulnerable systems

The vulnerability was discovered by Riot Games researchers Nick Peterson and Mohamed Al-Sharifi. It causes the UEFI firmware to show that the DMA protection is enabled even if the IOMMU did not initialize correctly, leaving the system exposed to attacks.

Peterson and Al-Sharifi disclosed the security isssue responsibly and worked with [CERT](https://tinyurl.com/twcert)[ Taiwan](https://www.twcert.org.tw/en/lp-139-2.html) to coordinate a response and reach affected vendors.

The researchers [explain](https://www.riotgames.com/en/news/vanguard-security-update-motherboard) that when a computer system is turned on, it is "in its most privileged state: it has full, unrestricted access to the entire system and all connected hardware."

Protections become available only after loading the initial firmware, which is UEFI most of the time, which initializes hardware and software in a secure way. The operating system is among the last to load in the boot sequence.

On vulnerable systems, some Riot Games titles, such as the popular Valorant, will not launch. This is due to the Vanguard system that works at the kernel level to protect against cheats.

"If a cheat loads before we do, it has a better chance of hiding where we can’t find it. This creates an opportunity for cheats to try and remain undetected, wreaking havoc in your games for longer than we are ok with" - [Riot Games](https://www.riotgames.com/en/news/vanguard-security-update-motherboard)

Although the researchers described the vulnerability from the perspective of the gaming industry, where cheats could be loaded early on, the security risk extends to malicious code that can compromise the operating system.

The attacks require physical access, where a malicious PCIe device needs to be connected for a DMA attack before the operating system starts. During that time, the rogue device may read or modify the RAM freely.

"Even though firmware asserts that DMA protections are active, it fails to properly configure and enable the IOMMU during the early hand-off phase in the boot sequence," reads the [advisory](https://www.kb.cert.org/vuls/id/382314) from the Carnegie Mellon CERT Coordination Center (CERT/CC).

"This gap allows a malicious DMA-capable Peripheral Component Interconnect Express (PCIe) device with physical access to read or modify system memory before operating system-level safeguards are established."

Due to exploitation occurring before OS boot, there would be no warnings from security tools, no permission prompts, and no alerts to notify the user.

## Broad impact confirmed

Carnegie Mellon CERT/CC confirmed that the vulnerability impacts some motherboard models from ASRock, ASUS, GIGABYTE, and MSI, but products from other hardware manufacturers may be affected.

The specific models impacted for each manufacturer are listed in the security bulletins and firmware updates from the makers ([ASUS](https://www.asus.com/security-advisory/), [MSI](https://csr.msi.com/global/product-security-advisories), [Gigabyte](https://www.gigabyte.com/Support/Security?type=1), [ASRock](https://www.asrock.com/support/Security.asp)).

Users are recommended to check for available firmware updates and install them after backing up important data.

Riot Games has updated Vanguard, its kernel-level anti-cheat system that provides protection against bots and scripts in games like Valorant and League of Legends.

If a system is affected by the UEFI vulnerability, Vannguard will block Valorant from launching and prompt users with a pop-up providing details on what is required to start the game. 

"Our VAN:Restriction system is Vanguard’s way of telling you we cannot guarantee system integrity due to the outlined disabled security features," Riot Games researchers say.