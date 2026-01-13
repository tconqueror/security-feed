# New Windows updates replace expiring Secure Boot certificates

![Windows](https://www.bleepstatic.com/content/hl-images/2025/10/20/Windows-headpic.jpg)

Microsoft has started automatically replacing expiring Secure Boot certificates on eligible Windows 11 24H2 and 25H2 systems.

[Secure Boot](https://www.bleepingcomputer.com/tag/Secure-Boot/) is a security feature that blocks malicious software (like rootkit malware) from executing during the system startup sequence by ensuring that only trusted bootloaders can load on computers with UEFI firmware. This is done by checking the software's digital signature against a set of trusted digital certificates that are stored in the device's firmware.

Today's announcement comes after Microsoft [warned IT admins](https://techcommunity.microsoft.com/blog/windows-itpro-blog/secure-boot-playbook-for-certificates-expiring-in-2026/4469235) in November to update the security certificates used to validate UEFI firmware before they expire.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"Secure Boot certificates used by most Windows devices are set to expire starting in June 2026\. This might affect the ability of certain personal and business devices to boot securely if not updated in time," [Microsoft said](https://x.com/WindowsUpdate/status/2011140448274800881).

"Starting with this update, Windows quality updates include a subset of high confidence device targeting data that identifies devices eligible to automatically receive new Secure Boot certificates. Devices will receive the new certificates only after demonstrating sufficient successful update signals, ensuring a safe and phased deployment," it [added](https://support.microsoft.com/en-us/topic/january-13-2026-kb5074109-os-builds-26200-7623-and-26100-7623-3ec427dd-6fc4-4c32-a471-83504dd081cb#:~:text=%5BSecure%20Boot%5D%C2%A0Starting%20with%20this%20update).

IT admins who want to maintain Secure Boot functionality and ensure their endpoints' security should install the new certificates before the old certificates expire this summer.

Failing to do so could result in losing Windows Boot Manager and Secure Boot protections, as security updates for pre-boot components will no longer be provided to Secure Boot-enabled devices.

"Without updates, the Secure Boot-enabled Windows devices risk not receiving security updates or trusting new boot loaders which will compromise both serviceability and security," Microsoft [explains](https://support.microsoft.com/en-us/topic/windows-secure-boot-certificate-expiration-and-ca-updates-7ff40d33-95dc-4c3c-8725-a9b95457578e).

While Microsoft will automatically update high-confidence devices via Windows Update, organizations can also deploy Secure Boot certificates using registry keys, the Windows Configuration System (WinCS), and Group Policy settings.

According to [Microsoft's Secure Boot playbook](https://techcommunity.microsoft.com/blog/windows-itpro-blog/secure-boot-playbook-for-certificates-expiring-in-2026/4469235), admins should first inventory their device fleets, verify Secure Boot status using PowerShell commands or registry keys, and then apply manufacturer firmware updates before installing Microsoft's certificate updates.