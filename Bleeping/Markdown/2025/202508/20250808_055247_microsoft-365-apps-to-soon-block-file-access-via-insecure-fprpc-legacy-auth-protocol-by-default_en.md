# Microsoft 365 apps to soon block file access via FPRPC by default

![Microsoft 365](https://www.bleepstatic.com/content/hl-images/2025/07/25/Microsoft-365.jpg)

Microsoft has announced that the Microsoft 365 apps for Windows will start blocking access to files via the insecure FPRPC legacy authentication protocol by default starting late August.

These changes apply only to Microsoft 365 apps for Windows and will not affect Microsoft Teams users across Windows, Mac, web, iOS, or Android.

"Microsoft 365 apps will block insecure file open protocols like FPRPC by default starting version 2508, with new Trust Center settings to manage these protocols," the company [said](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1130392) in a new Microsoft 365 Admin Center message on Wednesday.

"These changes enhance security by reducing exposure to outdated technologies like FrontPage Remote Procedure Call (FPRPC), FTP, and HTTP."

Starting with version 2508 of Microsoft 365 apps, file opens using the legacy FPRPC protocol will be blocked by default and will instead open using a more secure fallback protocol. The changes will become generally available in late August 2025, with an estimated time of arrival for all tenants by late September.

New Trust Center settings will allow users to re-enable FPRPC, unless managed by Group Policy or the Cloud Policy service (CPS). They will also be able to disable FTP and HTTP file opens, which will still be allowed by default.

Admins can manage authentication protocol settings through the Cloud Policy service (CPS), under Microsoft 365 Apps settings. If a protocol is disabled via CPS, users will not be able to re-enable it through Trust Center.

This comes on the heels of a [June announcement](https://www.bleepingcomputer.com/news/microsoft/microsoft-365-to-block-file-access-via-legacy-auth-protocols-by-default/) that the company will start updating security defaults for all Microsoft 365 tenants to block file access via legacy auth protocols, such as RPS (Relying Party Suite) and FPRPC (FrontPage Remote Procedure Call), and protect users against brute-force and phishing attacks exploiting outdated authentication methods.

Since the start of the year, Microsoft has also started [disabling all ActiveX controls](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) in Windows versions of Microsoft 365 and Office 2024 apps, and revealed that it will roll out a new Teams feature designed to [block screenshots during meetings](https://www.bleepingcomputer.com/news/microsoft/microsoft-teams-will-soon-block-screen-capture-during-meetings/) in July.

More recently, Microsoft [announced](https://www.bleepingcomputer.com/news/security/microsoft-outlook-to-block-more-risky-attachments-used-in-attacks/) that it will include the .library-ms and .search-ms file types in the list of blocked Outlook attachments starting in July.