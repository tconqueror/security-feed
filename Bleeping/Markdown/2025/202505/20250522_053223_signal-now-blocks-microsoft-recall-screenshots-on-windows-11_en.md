# Signal now blocks Microsoft Recall screenshots on Windows 11

![Signal](https://www.bleepstatic.com/content/hl-images/2024/08/09/Signal-red.jpg)

​Signal has updated its Windows app to protect users' privacy by blocking Microsoft's AI-powered Recall feature from taking screenshots of their conversations.

This new privacy feature, dubbed "screen security," is now enabled by default on all Windows 11 devices, where Recall continuously takes screenshots of all active windows every few seconds and analyzes them to build a database that can be searched using natural language.

When enabled, screen security will set a Digital Rights Management (DRM) flag on Signal's app windows, blocking their content from being captured by Recall or other Windows apps and features.

Microsoft introduced Recall [in May 2024](https://www.bleepingcomputer.com/news/microsoft/windows-11-recall-ai-feature-will-record-everything-you-do-on-your-pc/) when security experts described it as a [privacy nightmare](https://www.bleepingcomputer.com/news/microsoft/microsofts-new-windows-11-recall-is-a-privacy-nightmare/) and a significant security risk because attackers could easily weaponize it to steal user data.

To address these concerns, Microsoft made Recall a removable [opt-in](https://www.bleepingcomputer.com/news/microsoft/microsoft-makes-windows-recall-opt-in-secures-data-with-windows-hello/) feature that requires users to sign in [using Windows Hello](https://www.bleepingcomputer.com/news/microsoft/microsoft-makes-windows-recall-opt-in-secures-data-with-windows-hello/) and upgraded it to [filter out sensitive information](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-recall-now-can-be-removed-is-more-secure/) (like credentials and credit card numbers) and to exclude some apps, websites, or private browsing sessions from being captured.

David Weston, Microsoft's VP for Enterprise and OS Security, also said in September that Microsoft added rate-limiting and anti-hammering [protection against malware](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-recall-now-can-be-removed-is-more-secure/) attacks to Recall, as well as the ability to adjust storage settings, delete snapshots, and turn off saving snapshots completely.

"Although Microsoft made several adjustments over the past twelve months in response to critical feedback, the revamped version of Recall still places any content that's displayed within privacy-preserving apps like Signal at risk," Signal developer Joshua Lund [said in a Wednesday blog post](https://signal.org/blog/signal-doesnt-recall/).

"As a result, we are enabling an extra layer of protection by default on Windows 11 in order to help maintain the security of Signal Desktop on that platform even though it introduces some usability trade-offs. Microsoft has simply given us no other option."

Signal's screen security might cause issues with screen readers, so those who want to turn it off can do so from Signal Settings > Privacy > Screen security.

Signal will also show an alert before turning off screen security, warning that Windows can take screenshots of their Signal chats once the feature is disabled.

![Signal screen security warning](https://www.bleepstatic.com/images/news/u/1109292/2025/Disable_Signal_screen_security.jpg)

_Signal screen security warning (Signal)_

"Apps like Signal have essentially no control over what content Recall is able to capture, and implementing 'DRM' that works for you (not against you) is the best choice that we had," Lund added.

​"We hope that the AI teams building systems like Recall will think through these implications more carefully in the future. Apps like Signal shouldn't have to implement 'one weird trick' in order to maintain the privacy and integrity of their services without proper developer tools. People who care about privacy shouldn't be forced to sacrifice accessibility upon the altar of AI aspirations either."

However, as Lund added, enabling Signal's screen security on your device will not protect against screenshots or recordings by others using screen readers on macOS or Linux devices.

In April, almost one year after its introduction, Microsoft [started rolling out](https://www.bleepingcomputer.com/news/microsoft/windows-11s-recall-ai-is-now-rolling-out-on-copilot-plus-pcs/) Windows Recall to all customers who installed the Windows 11 KB5055627 update on Copilot+ PCs.

One month later, the company made it generally available to everyone who installed the May 2025 Patch Tuesday updates.