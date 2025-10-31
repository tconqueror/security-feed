# Microsoft Edge gets scareware sensor for faster scam detection

![Microsoft Edge](https://www.bleepstatic.com/content/hl-images/2025/09/26/Microsoft_Edge.jpg)

Microsoft is introducing a new scareware sensor for the Microsoft Edge web browser, which helps detect scam pages more quickly and ensures that Defender SmartScreen blocks them faster.

In scareware scams (also known as [tech support scams](https://www.bleepingcomputer.com/tag/tech-support-scam/)), fraudsters use aggressive landing pages to trick potential victims into believing that their devices have been compromised with malware and attempt to gain remote access to their systems by pressuring them into calling a fake tech support number.

Microsoft's Defender SmartScreen, which protects Edge users from such scams, activates after an abusive site is added to its index of malicious web pages, while the [built-in Edge scareware blocker](https://www.bleepingcomputer.com/news/microsoft/microsoft-tests-edge-scareware-blocker-to-block-tech-support-scams/) (introduced at the [November 2024 Ignite conference](http://blogs.windows.com/msedgedev/2024/11/19/microsoft-edge-for-business-transform-your-workday-ignite-2024#detect-scams) and [enabled by default since February](https://www.bleepingcomputer.com/news/microsoft/microsoft-edge-update-adds-ai-powered-scareware-blocker/) on most PCs) adds extra protection by detecting signs of such scams in real-time using a local machine learning model.

After detecting a tech support scam page in real-time, the AI/ML-based scareware blocker warns users and allows them to continue loading the website if they trust it's safe. The blocker will exit full-screen mode, display a warning, stop loud audio, and show a page thumbnail.

Users can also report scam sites to protect others by sharing diagnostic information and screenshots with Microsoft, which helps the SmartScreen service detect scareware outbreaks.

With the new sensor enabled, SmartScreen will be notified to index scam pages more quickly, ensuring that Edge users worldwide are alerted to scams faster.

![Edge scareware blocker SmartScreen setting](https://www.bleepstatic.com/images/news/u/1109292/2025/edge-scareware-blocker-smartscreen-setting.jpg)

_Edge scareware blocker SmartScreen setting (Microsoft)_

​"Starting in November, if Scareware blocker detects a suspicious full-screen page, the new scareware sensor in Edge 142 can notify SmartScreen about the potential scam immediately, without sharing screenshots or any extra data beyond what SmartScreen already receives," [said Principal PM Manager Rob Franco](https://blogs.windows.com/msedgedev/2025/10/31/protecting-more-edge-users-with-expanded-scareware-blocker-availability-and-real-time-protection/), who is working on the Microsoft Edge Enterprise and Security team.

"This real-time report gives SmartScreen an immediate heads-up to help confirm scams faster and block them worldwide. Later, we'll add more anonymous detection signals to help Edge recognize recurring scam patterns."

This new scareware sensor is rolling out in Microsoft Edge 142, disabled by default, but Microsoft plans to enable it for all users who have enabled SmartScreen to help detect more scams.

Microsoft says Edge users have reported scareware beyond run-of-the-mill "Virus Alert!" popups, including scams using fake control panels and blue screens.

"Recently, users reported scams posing as law enforcement, accusing them of crimes, and demanding payment to unlock their PCs," Franco added. "When Scareware blocker caught that scam, it had not yet been blocked by Defender SmartScreen or other services like Google Safe Browsing."