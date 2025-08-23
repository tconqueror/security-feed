# Brave blocks Windows Recall from screenshotting your browsing activity

![Brave Browser](https://www.bleepstatic.com/content/hl-images/2022/06/22/Brave.jpg)

Brave Software says its privacy-focused browser will block Microsoft's Windows Recall from capturing screenshots of Brave windows by default to protect users' privacy.

Windows Recall is an opt-in Windows feature that takes screenshots of active windows every few seconds, analyzes them, and enables Windows 11 users to search for text within the snapshots using natural language. The goal is to make it easy for users to quickly find information about past activities in Windows.

However, the feature has [sparked widespread criticism](https://www.bleepingcomputer.com/news/microsoft/microsofts-new-windows-11-recall-is-a-privacy-nightmare/) for potentially exposing sensitive data of Windows users, including passwords, emails, health records, and financial information.

Microsoft later increased security by providing methods for software providers to opt out of Windows Recall and by securing data with Windows Hello Enhanced Sign-in Security (ESS).

Brave has now decided to proactively enable a technical feature that prevents Recall from capturing the contents of its windows.

"Given Brave's focus on privacy-maximizing defaults and what is at stake here (your entire browsing history), we have proactively disabled Recall for all Brave tabs," reads a new [Brave announcement](https://brave.com/privacy-updates/35-block-recall/).

"We think it's vital that your browsing activity on Brave does not accidentally end up in a persistent database, which is especially ripe for abuse in highly-privacy-sensitive cases such as intimate partner violence."

A [Brave GitHub issue](https://github.com/brave/brave-browser/issues/46284) explains that developers have utilized Microsoft's [SetInputScope API](https://learn.microsoft.com/en-us/windows/ai/recall/recall-web-browsers) and set the input scope to IS_PRIVATE for all browser windows. This tells Windows that the content should not be captured or indexed by Recall.

"Microsoft says that a Web browser can use SetInputScope to set the scope to be IS_PRIVATE to make sure that Recall doesn't save the user's browsing history," reads the Brave GitHub issue.

"We can force that to be true for all windows in renderer_widget_host_view."

The change is already live in Brave Nightly builds and will roll out to stable releases in the coming weeks. For those who wish to use Recall, you can enable it through Brave's settings.

In May, encrypted messenger [Signal also blocked Windows Recall](https://www.bleepingcomputer.com/news/security/signal-now-blocks-microsoft-recall-screenshots-on-windows-11/) by enabling the DRM management flag in the program, which prevents Microsoft's software from taking screenshots of the program.

However, this method could cause issues with accessibility software, such as screen readers, so Signal also provides a way to turn off this setting.