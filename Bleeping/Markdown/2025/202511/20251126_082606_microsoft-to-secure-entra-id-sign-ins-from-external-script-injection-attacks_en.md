# Microsoft to secure Entra ID sign-ins from script injection attacks

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/04/24/Microsoft.jpg)

Microsoft plans to enhance the security of the Entra ID authentication system against external script injection attacks starting in mid-to-late October 2026.

This update will implement a strengthened Content Security Policy that allows script downloads only from Microsoft-trusted content delivery network domains and inline script execution only from Microsoft-trusted sources during sign-ins.

After rollout, it will protect users against various security risks, including cross-site scripting attacks in which attackers inject malicious code into websites to steal credentials or compromise systems.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

The update policy will apply only to browser-based sign-in experiences at URLs beginning with login.microsoftonline.com, and Microsoft Entra External ID will not be affected.

"This update strengthens security and adds an extra layer of protection by allowing only scripts from trusted Microsoft domains to run during authentication, blocking unauthorized or injected code from executing during the sign-in experience," [said](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/enhance-protection-of-microsoft-entra-id-authentication-by-blocking-external-scr/4435200) Megna Kokkalera, product manager for Microsoft Identity and Authentication Experiences.

Microsoft urged organizations to test sign-in scenarios before the October 2026 deadline to identify and address any dependencies on code-injection tools.

IT administrators can identify potential impact by reviewing sign-in flows in the browser developer console: violations will appear in red text with details about the blocked scripts.

![CSP policy violation](https://www.bleepstatic.com/images/news/u/1109292/2025/Entra-ID-script-CSP-violation.png)

_CSP policy violation (Microsoft)_

​Microsoft also advised enterprise customers to stop using browser extensions and tools that inject code or scripts into sign-in pages before the change takes effect. These will no longer be supported and will stop working, although users will still be able to sign in.

"This update to our Content Security Policy adds an additional layer of protection by blocking unauthorized scripts, further helping safeguard your organization against evolving security threats," Kokkalera added.

This move is part of Microsoft's Secure Future Initiative (SFI), a company-wide effort launched two years ago, in November 2023, following a report from the Cyber Safety Review Board of the U.S. Department of Homeland Security, which [found](https://www.cisa.gov/sites/default/files/2025-03/CSRBReviewOfTheSummer2023MEOIntrusion508.pdf) that the company's security culture was "inadequate and requires an overhaul."

As part of the same initiative, Microsoft also [updated Microsoft 365 security defaults](https://www.bleepingcomputer.com/news/microsoft/microsoft-365-to-block-file-access-via-legacy-auth-protocols-by-default/) to block access to SharePoint, OneDrive, and Office files via legacy authentication protocols, [disabled all ActiveX controls](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) in Windows versions of Microsoft 365 and Office 2024 apps.

Earlier this month, it also began rolling out a new Teams feature [announced in May](https://www.bleepingcomputer.com/news/microsoft/microsoft-teams-will-soon-block-screen-capture-during-meetings/) and designed to [block screen capture attempts](https://www.bleepingcomputer.com/news/microsoft/microsoft-rolls-out-screen-capture-prevention-for-teams-users/) during meetings.