# Microsoft fixes Exchange Online bug flagging Gmail emails as spam

![Exchange Online](https://www.bleepstatic.com/content/hl-images/2025/05/02/Exchange_Online.jpg)

Microsoft has resolved an issue with a machine learning model that mistakenly flagged emails from Gmail accounts as spam in Exchange Online.

Tracked as [EX1064599](http://admin.microsoft.com/#/MessageCenter/:/messages/EX1064599) in the Microsoft 365 admin center, the issue started impacting users on April 25 at 09:24 UTC, automatically moving emails erroneously tagged as malicious to the junk folder.

"We've identified that our machine learning (ML) model, which safeguards Exchange Online against risky email messages, is incorrectly identifying legitimate email messages as spam due to their similarity to email messages used in spam attacks, which is resulting in impact," the company explained when it acknowledged the ML model bug.

In a final update to the incident report added on May 1 at 16:31 UTC, Microsoft said it successfully reverted the buggy ML model to the previous working version, mitigating the false positive issue. It also added that admins and users may have also been able to create custom allow rules to ensure that Gmail messages weren't sent to the junk folder while the service was impacted.

"After a period of monitoring, we've confirmed through our service health telemetry that the completion of reverting to the previous ML model has successfully remediated impact," Microsoft added. "We're continuing to investigate opportunities to improve our ML detection process to reduce false positive detections and prevent similar future impact."

While Redmond has yet to share what regions or how many customers were affected, this service issue was tagged as an incident, which typically involves noticeable user impact.

Microsoft has handled similar issues since the start of the year, leading to emails being incorrectly tagged as spam or quarantined. For instance, last week, the company mitigated another machine-learning issue that [mistakenly flagged Adobe emails](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-machine-learning-bug-flagging-adobe-emails-as-spam/) in Exchange Online as spam.

In March, it addressed [another Exchange Online false positive](https://www.bleepingcomputer.com/news/microsoft/microsoft-exchange-online-bug-mistakenly-quarantines-user-emails/), causing anti-spam systems to quarantine some users' emails incorrectly.

In October 2023, it also had to [disable a bad anti-spam rule](https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-bad-spam-rule-flagging-all-sent-emails-as-junk/) flooding Microsoft 365 admins' inboxes with blind carbon copies (BCC) of outbound emails mistakenly flagged as spam, while in August 2024, it [mitigated an Exchange Online bug](https://www.bleepingcomputer.com/news/microsoft/microsoft-exchange-online-mistakenly-tags-emails-as-malware/) tagging emails containing images as malicious and automatically quarantining them.