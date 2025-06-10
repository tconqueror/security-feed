# Microsoft Outlook to block more risky attachments used in attacks

![Outlook](https://www.bleepstatic.com/content/hl-images/2025/04/29/Outlook.jpg)

Microsoft announced it will expand the list of blocked attachments in Outlook Web and the new Outlook for Windows starting next month.

The company said on Monday in a Microsoft 365 Message Center update that Outlook will block .library-ms and .search-ms file types beginning in July.

"As part of our ongoing efforts to enhance security in Outlook Web and the New Outlook for Windows, we're updating the default list of blocked file types in OwaMailboxPolicy," [Microsoft said](http://admin.microsoft.com/#/MessageCenter/:/messages/MC1090702). "Starting in early July 2025, the \[.library-ms and .search-ms\] file types will be added to the BlockedFileTypes list."

Windows Library files (.library-ms), which define virtual collections of folders and files in the Windows file system, were [used earlier this year](https://www.bleepingcomputer.com/news/security/windows-ntlm-hash-leak-flaw-exploited-in-phishing-attacks-on-governments/) in phishing attacks targeting government entities and private companies to exploit a Windows vulnerability ([CVE-2025-24054](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-24054)) that exposes NTLM hashes.

The .search-ms URI protocol handler has also been exploited in [phishing](https://www.bleepingcomputer.com/news/security/phishing-emails-abuse-windows-search-protocol-to-push-malicious-scripts/) and [malware](https://www.bleepingcomputer.com/news/security/new-voldemort-malware-abuses-google-sheets-to-store-stolen-data/) attacks since at least June 2022, when Hacker House co-founder and security researcher Matthew Hickey found that it could be used to [automatically launch Windows Search windows](https://www.bleepingcomputer.com/news/security/new-windows-search-zero-day-added-to-microsoft-protocol-nightmare/) on recipients' devices to trick them into launching malware when chained with a Windows Support Diagnostic Tool (MSDT) remote code execution vulnerability ([CVE-2022-30190](https://msrc.microsoft.com/update-guide/en-US/vulnerability/CVE-2022-30190)).

"The newly blocked file types are rarely used, so most organizations will not be affected by the change. However, if your users are sending and receiving affected attachments, they will report that they are no longer able to open or download them in Outlook Web or the New Outlook for Windows," the company added on Monday.

"No action is required if your organization does not rely on these file types. The update will automatically apply to all OWA Mailbox policies in your organization. If your organization needs to allow these file types, you can add them to the AllowedFileTypes property of your users' OwaMailboxPolicy objects before the rollout."

You can find the complete list of blocked Outlook attachments on [Microsoft's documentation website](https://learn.microsoft.com/en-us/powershell/module/exchange/set-owamailboxpolicy?view=exchange-ps#-blockedfiletypes). Enterprise users with a Microsoft Exchange Server account can ask Exchange Server administrators to adjust security settings for their mailboxes to accept attachments blocked by Outlook if they can't be shared as an archive, using a different extension, or using OneDrive or SharePoint.

This move is part of a much broader effort to remove or turn off Office and Windows features that have been abused and exploited to infect Microsoft customers with malware.

It started in 2018 when Microsoft [expanded support for its Antimalware Scan Interface (AMSI)](https://www.bleepingcomputer.com/news/security/microsoft-office-365-customers-get-protection-against-malicious-macros/) to Office 365 client apps to block attacks using Office VBA macros.

Since then, the company began [blocking VBA Office macros](https://www.bleepingcomputer.com/news/microsoft/microsoft-starts-blocking-office-macros-by-default-once-again/) by default, [disabled Excel 4.0 (XLM) macros](https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-excel-40-macros-by-default-to-block-malware/), introduced [XLM macro protection](https://www.bleepingcomputer.com/news/security/microsoft-office-365-gets-protection-against-malicious-xlm-macros/), and started [blocking untrusted XLL add-ins by default](https://www.bleepingcomputer.com/news/microsoft/microsoft-excel-now-blocking-untrusted-xll-add-ins-by-default/) across Microsoft 365 tenants.

Microsoft also announced in May 2024 that it would [kill off VBScript](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-start-killing-off-vbscript-in-second-half-of-2024/) and [disabled all ActiveX controls](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) in Windows versions of Microsoft 365 and Office 2024 applications in April 2025.