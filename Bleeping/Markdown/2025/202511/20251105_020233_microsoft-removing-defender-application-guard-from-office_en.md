# Microsoft removing Defender Application Guard from Office

![Microsoft Defender](https://www.bleepstatic.com/content/hl-images/2023/10/11/Microsoft-Defender_for_Endpoint.jpg)

Microsoft plans to remove Defender Application Guard from Office by December 2027, starting with the February 2026 release of Office version 2602.

The Microsoft Defender Application Guard for Office (MDAG) is designed for Windows 10 and Windows 11 Enterprise editions, protecting users' devices by isolating untrusted Word, PowerPoint, and Excel files in a separate, Hyper-V-enabled container. This helps keep the host operating system secure, ensuring that enterprise data remains safe from attackers if a file or website is malicious.

Microsoft announced that it would be [deprecating MDAG](https://www.bleepingcomputer.com/news/microsoft/microsoft-deprecates-defender-application-guard-for-office/) two years ago, in November 2023, when it also recommended Defender for Endpoint attack surface reduction rules, Protected View, and Windows Defender Application Control as alternatives.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Redmond retired MDAG five months later, in April 2024, and says that Office files will now open in Protected View, a read-only mode where most document editing functions are disabled.

"Files will open in Protected View instead. Admins should enable Microsoft Defender for Endpoint ASR rules and Windows Defender Application Control to maintain security. No admin action is required for removal," Microsoft said in a [Microsoft 365 message center update](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1182696) on Tuesday.

"This change aligns with the end of support for Windows 11 version 23H2 and helps streamline the security experience for users. Documents that previously opened in Application Guard will now open in Protected View, maintaining strong protection against threats."

![Application Guard for Office alert](https://www.bleepstatic.com/images/news/Microsoft/microsoft-office-application-guard.jpg)

_Application Guard for Office alert (Microsoft)_

​According to a shared timeline, the removal will start with Office version 2602, for the Current Channel in early February 2026, for the Monthly Enterprise Channel in April 2026, and for the Semi-Annual Enterprise Channel in July 2026.

Microsoft estimates that MDAG will be entirely removed from Office with the release of version 2612, which will roll out to Current Channel users in early December 2026, to the Monthly Enterprise Channel in February 2027, and the Semi-Annual Enterprise Channel in July 2027.

To maintain protection against malicious Office documents, Microsoft recommends that IT admins:

* Enable Microsoft Defender for Endpoint ASR rules to block risky behaviors in Office files.
* Enable Windows Defender Application Control (WDAC) to ensure only trusted, signed code runs on devices.

The removal announcement comes two years after Redmond rolled out Application Guard for Office [to all Microsoft 365 customers](https://www.bleepingcomputer.com/news/security/microsoft-rolls-out-application-guard-for-office-to-all-customers/) with supported licenses.

MDAG was officially launched as part of a [limited preview](https://www.bleepingcomputer.com/news/microsoft/office-365-to-prevent-malicious-docs-from-infecting-windows/) in November 2019, and it was only available to commercial users with Microsoft 365 E5 or Microsoft 365 E5 Security licenses.