# Microsoft Defender bug triggers erroneous BIOS update alerts

![Microsoft Defender](https://www.bleepstatic.com/content/hl-images/2023/10/11/Microsoft-Defender_for_Endpoint.jpg)

​Microsoft is working to resolve a bug that causes Defender for Endpoint to incorrectly tag some devices' BIOS (Basic Input/Output System) firmware as outdated, prompting users to update it.

In a [service alert](https://admin.cloud.microsoft/Adminportal/Home?source=applauncher#/windowsreleasehealth/:/issue/DZ1163521) seen by BleepingComputer, Redmond said that this known issue affects Dell devices and is caused by a Defender for Endpoint logic bug.

"Microsoft have identified that a code bug in the Microsoft Defender for Endpoint logic that fetches vulnerabilities for Dell devices is causing impact," the company said earlier today.

"Your organization is affected by this event, and some users receiving Microsoft Defender for Endpoint alerts for the BIOS version of their Dell devices are impacted."

While the company has already developed a fix for this bug and is currently preparing it for deployment, it has yet to disclose the regions and the number of customers impacted by these ongoing Defender XDR issues.

Today, Microsoft engineers have also [fixed black screen crashes impacting macOS devices](http://admin.cloud.microsoft/Adminportal/Home?source=applauncher#/windowsreleasehealth/:/issue/DZ1163645) that were updated after September 29, due to a deadlock in the Apple enterprise security framework that occurs when multiple security providers are listening to events.

Earlier this month, Redmond [fixed another false positive](https://www.bleepingcomputer.com/news/microsoft/microsoft-anti-spam-bug-blocks-links-in-exchange-online-teams/) that was causing an anti-spam service to erroneously block Microsoft Teams and Exchange Online users from opening URLs.

Microsoft stated at the time that the issue was caused by the anti-spam engine incorrectly flagging URLs contained within other URLs as potentially malicious, which also resulted in some emails being quarantined.

Since the start of the year, it has also addressed machine-learning bugs that [mistakenly flagged Adobe emails](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-machine-learning-bug-flagging-adobe-emails-as-spam/) in Exchange Online as spam, one that caused anti-spam systems to [quarantine some Exchange Online users' emails incorrectly](https://www.bleepingcomputer.com/news/microsoft/microsoft-exchange-online-bug-mistakenly-quarantines-user-emails/), and a third that led to [emails from Gmail accounts being tagged as spam](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-exchange-online-bug-flagging-gmail-emails-as-spam/) in Exchange Online by mistake.

_This is a developing story..._