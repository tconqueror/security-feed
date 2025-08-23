# Microsoft unveils new security defaults for Windows 365 Cloud PCs

![Windows](https://www.bleepstatic.com/content/hl-images/2025/05/28/Windows-headpic.jpg)

Microsoft has announced new Windows 365 security defaults starting in the second half of 2025 and affecting newly provisioned and reprovisioned Cloud PCs.

The company said these changes include disabling the clipboard, drive, USB, and printer redirections by default to block users from copying files between Cloud PCs and physical devices through clipboard functions to reduce risks of data theft and block malware attacks.

However, while USB redirections will be disabled by default, they only target low-level device access, which means that USB mice, keyboards, and webcams will not be affected since they're managed through high-level redirection. These new security defaults will also be applied to newly created host pools for Azure Virtual Desktop.

Starting last month, Microsoft has also enabled virtualization-based security, Credential Guard, and hypervisor-protected code integrity (HVCI) by default on Windows 365 Cloud PCs running Windows 11 gallery images to create secure memory enclaves and prevent malicious code execution at the kernel level.

"Windows 365 is enhancing Cloud PC security by having clipboard, drive, USB, and printer redirections disabled by default for all newly provisioned and reprovisioned Cloud PCs," [Microsoft said](https://techcommunity.microsoft.com/blog/windows-itpro-blog/enhanced-security-defaults-for-windows-365-cloud-pcs/4424914).

"Since May 2025, all newly provisioned and reprovisioned Windows 365 Cloud PCs running a Windows 11 gallery image have VBS, Credential Guard, and HVCI enabled by default."

Microsoft will also display notification banners in the Intune Admin Center to alert IT administrators about the changes and allow them to override the new defaults using Intune device configuration policies or Group Policy Objects if their end-users require specific redirection capabilities.

![Intune admin center banner about new redirection defaults](https://www.bleepstatic.com/images/news/u//1109292/2025/Intune%20admin%20center%20banner%20about%20new%20redirection%20defaults.jpg)

_Intune admin center banner about new redirection defaults (Microsoft)_

​"When new Cloud PCs are provisioned, the new defaults for disabling redirections will be applied," the company explained. "Subsequently, Intune will sync and implement the IT admin's desired settings from the existing policies, overriding the default configurations. This process assumes that the new Cloud PC is being added to an existing group that has been assigned to the relevant policy."

On Tuesday, Microsoft announced it would begin [updating security defaults for all Microsoft 365 tenants](https://www.bleepingcomputer.com/news/microsoft/microsoft-365-to-block-file-access-via-legacy-auth-protocols-by-default/) in July to block access to SharePoint, OneDrive, and Office files via legacy authentication protocols.

Starting next month, Microsoft 365 will automatically block legacy browser authentication to OneDrive and SharePoint using RPS (Relying Party Suite), together with FPRPC (FrontPage Remote Procedure Call) protocol for Office file opens.

Since January, the company has also started [disabling all ActiveX controls](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) in Windows versions of Microsoft 365 and Office 2024 apps and said it will begin rolling out a new Teams feature designed to [block screenshots during meetings](https://www.bleepingcomputer.com/news/microsoft/microsoft-teams-will-soon-block-screen-capture-during-meetings/) in July.

Microsoft also [announced](https://www.bleepingcomputer.com/news/security/microsoft-outlook-to-block-more-risky-attachments-used-in-attacks/) last week that it will add .library-ms and .search-ms file types to the list of blocked Outlook attachments starting in July.