# Microsoft to disable Excel workbook links to blocked file types

![Microsoft Excel](https://www.bleepstatic.com/content/hl-images/2025/07/31/Microsoft-Excel.jpg)

Microsoft has announced that it will start disabling external workbook links to blocked file types by default between October 2025 and July 2026.

After the rollout, Excel workbooks referencing blocked file types will display a #BLOCKED error or fail to refresh, eliminating security risks associated with accessing unsupported or high-risk file types, including, but not limited to, phishing attacks that utilize workbooks to redirect targets to malicious payloads.

This change is being introduced as a new FileBlockExternalLinks group policy, which expands File Block Settings to include external workbook links.

As the company explained in a [Microsoft 365 admin center message](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1125497) on Wednesday, Microsoft 365 will display a business bar warning of this upcoming change when opening workbooks containing external links to blocked file types, starting with Build 2509.

However, after updating to Build 2510, if the policy is unconfigured, users will no longer be able to refresh or create new references to blocked file types.

"If not configured, no changes will take effect immediately. However, starting October 2025, the default behavior will block external links to file types currently blocked by the Trust Center," the company said.

"We recommend reviewing existing workbooks and communicating this change to users who rely on external links to ensure continuity of workflows."

Microsoft 365 admins who want to re-enable refreshing external links to blocked file types can edit the HKCU\\Software\\Microsoft\\Office\\<version>\\Excel\\Security\\FileBlock\\FileBlockExternalLinks registry key using the detailed instructions [in this support document](https://support.microsoft.com/en-us/topic/external-workbook-links-to-blocked-file-types-will-be-disabled-by-default-6dd12903-0592-463d-9e68-0741cf62ee58).

Since the start of the year, the company has also [added the .library-ms and .search-ms file types](https://www.bleepingcomputer.com/news/security/microsoft-outlook-to-block-more-risky-attachments-used-in-attacks/) to the list of blocked Outlook attachments and started [turning off all ActiveX controls](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) in Windows versions of Microsoft 365 and Office 2024 applications.

These changes are part of a broader effort to remove or disable Office and Windows features that have been exploited to infect Microsoft users with malware.

This initiative began in 2018 when Microsoft [expanded support](https://www.bleepingcomputer.com/news/security/microsoft-office-365-customers-get-protection-against-malicious-macros/) for its Antimalware Scan Interface (AMSI) in Office 365 client apps, enabling the blocking of attacks that use Office VBA macros.

Since then, the company has [started blocking VBA Office macros](https://www.bleepingcomputer.com/news/microsoft/microsoft-starts-blocking-office-macros-by-default-once-again/) by default, introduced [XLM macro protection](https://www.bleepingcomputer.com/news/security/microsoft-office-365-gets-protection-against-malicious-xlm-macros/), [disabled Excel 4.0 (XLM) macros](https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-excel-40-macros-by-default-to-block-malware/), announced that it would soon [kill off VBScript](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-start-killing-off-vbscript-in-second-half-of-2024/), and begun [blocking untrusted XLL add-ins by default](https://www.bleepingcomputer.com/news/microsoft/microsoft-excel-now-blocking-untrusted-xll-add-ins-by-default/) across Microsoft 365 tenants.

Earlier today, Microsoft also announced that it [has increased bounty payouts](https://www.bleepingcomputer.com/news/microsoft/microsoft-now-pays-up-to-40-000-for-some-net-vulnerabilities/) to $40,000 for some .NET and ASP.NET Core vulnerabilities.