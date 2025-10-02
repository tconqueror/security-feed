# Microsoft Outlook stops displaying inline SVG images used in attacks

![Outlook](https://www.bleepstatic.com/content/hl-images/2025/04/29/Outlook.jpg)

Microsoft says Outlook for Web and the new Outlook for Windows will no longer display risky inline SVG images that are being used in attacks.

This change began rolling out worldwide in early September 2025 and is expected to be completed for all customers by mid-October 2025.

Redmond added that this change will affect less than 0.1% of all images sent using Outlook, so the actual impact after the rollout ends is expected to be minimal.

"Inline SVG images will no longer be displayed in Outlook for Web or the new Outlook for Windows. Instead, users will see blank spaces where these images would have appeared," the company [said](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1130385) in a Microsoft 365 Message Center update on Tuesday.

"SVG images sent as classic attachments will continue to be supported and viewable from the attachment well. This update helps mitigate potential security risks, such as cross-site scripting (XSS) attacks. "

Malicious actors [have extensively used](https://www.bleepingcomputer.com/news/security/phishing-emails-increasingly-use-svg-attachments-to-evade-detection/) SVG (Scalable Vector Graphics) files over the past few years to deploy malware and display phishing forms. Cybersecurity companies have also reported a significant increase in phishing attacks [using this particular document format](https://www.bleepingcomputer.com/news/security/phishing-emails-increasingly-use-svg-attachments-to-evade-detection/), driven by PhaaS platforms such as Tycoon2FA, Mamba2FA, and Sneaky2FA.

For instance, Trustwave [reported in April](http://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/pixel-perfect-trap-the-surge-of-svg-borne-phishing-attacks/) that SVG-based attacks have pivoted toward phishing campaigns, seeing a staggering 1800% increase between early 2025 and April 2024.

The retirement of inline SVG images in Microsoft Outlook is part of a broader effort to remove or disable Office and Windows features that have been abused in attacks targeting Microsoft customers.

In June, Microsoft also announced that Outlook Web and the new Outlook for Windows will [start blocking .library-ms and .search-ms file types.](https://www.bleepingcomputer.com/news/security/microsoft-outlook-to-block-more-risky-attachments-used-in-attacks/) These file [types were previously used](https://www.bleepingcomputer.com/news/security/windows-ntlm-hash-leak-flaw-exploited-in-phishing-attacks-on-governments/) in attacks targeting government entities and have been exploited in [phishing](https://www.bleepingcomputer.com/news/security/phishing-emails-abuse-windows-search-protocol-to-push-malicious-scripts/) and [malware](https://www.bleepingcomputer.com/news/security/new-voldemort-malware-abuses-google-sheets-to-store-stolen-data/) attacks since at least June 2022\. The complete list of blocked Outlook attachments is available on [Microsoft's documentation website](https://learn.microsoft.com/en-us/powershell/module/exchange/set-owamailboxpolicy?view=exchange-ps#-blockedfiletypes).

Since 2018, Redmond has also [expanded support for its Antimalware Scan Interface (AMSI)](https://www.bleepingcomputer.com/news/security/microsoft-office-365-customers-get-protection-against-malicious-macros/) to block attacks using Office VBA macros in Office 365 client apps, started [blocking VBA Office macros](https://www.bleepingcomputer.com/news/microsoft/microsoft-starts-blocking-office-macros-by-default-once-again/) by default, introduced [XLM macro protection](https://www.bleepingcomputer.com/news/security/microsoft-office-365-gets-protection-against-malicious-xlm-macros/), [disabled Excel 4.0 (XLM) macros](https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-excel-40-macros-by-default-to-block-malware/), and began [blocking untrusted XLL add-ins by default](https://www.bleepingcomputer.com/news/microsoft/microsoft-excel-now-blocking-untrusted-xll-add-ins-by-default/) across Microsoft 365 tenants.

In April 2025, it also [disabled all ActiveX controls](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) in Windows versions of Microsoft 365 and Office 2024 apps, following its announcement in May 2024 that it would [deprecate VBScript](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-start-killing-off-vbscript-in-second-half-of-2024/) in the second half of 2024.