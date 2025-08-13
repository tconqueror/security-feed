# Microsoft removes PowerShell 2.0 from Windows 11, Windows Server

![PowerShell](https://www.bleepstatic.com/content/hl-images/2025/08/13/PowerShell.jpg)

Microsoft will remove PowerShell 2.0 from Windows starting in August, eight years after [announcing its deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/) and keeping it around as an optional feature.

The 14-year-old command processor introduced with Windows 7 was already removed for Windows Insiders as of [July 2025](https://blogs.windows.com/windows-insider/2025/07/03/announcing-windows-11-insider-preview-build-27891-canary-channel/), with the release of Windows 11 Insider Preview Build 27891 to the Canary Channel.

As detailed in a [support document](https://support.microsoft.com/en-us/topic/powershell-2-0-removal-from-windows-fe6d1edc-2ed2-4c33-b297-afe82a64200a) published on Monday, Microsoft will permanently remove PowerShell 2.0 from Windows 11 version 24H2, starting in August, and from Windows Server 2025 in September.

"For most users and organizations, this change will be uneventful – newer versions of PowerShell such as PowerShell 5.1 and PowerShell 7.x continue to be available and supported. However, if you have legacy scripts or software that explicitly depends on PowerShell 2.0, you will need to take action and update them or use a workaround to prevent any disruptions," [Microsoft said.](https://support.microsoft.com/en-us/topic/powershell-2-0-removal-from-windows-fe6d1edc-2ed2-4c33-b297-afe82a64200a)

"PowerShell 2.0 will be removed in a later release starting in August 2025 for Windows 11, version 24H2 and a September 2025 release for Windows Server 2025. All later releases for Windows 11 and Windows Server 2025 will not include PowerShell 2.0."

This move is part of a broader effort to remove legacy code, reducing system complexity, and improving Windows security, according to Microsoft.

## Removal affects customers using legacy scripts and software

Microsoft customers who use legacy applications, including older Microsoft server products such as Exchange, SharePoint, and SQL Server, that rely on PowerShell 2.0 scripting, will be directly impacted by this change.

Although legacy scripts attempting to launch PowerShell 2.0 will automatically default to PowerShell 5.1, which is backward-compatible for most commands and modules, those using such tools are advised to update their systems to prevent disruptions.

The company added that customers should migrate their scripts and tools to PowerShell 5.1 or PowerShell 7 and replace outdated software that cannot function without PowerShell 2.0 support, since some older third-party installers may fail on newer Windows versions when attempting to enable PowerShell 2.0 during setup.

"By using the newer and supported PowerShell 7 or PowerShell 5.1, you can help ensure that scripts run safer," [Microsoft added](https://learn.microsoft.com/en-us/windows/release-health/windows-message-center#3628) in a new message center post.

"If you have legacy scripts or software that explicitly depend on PowerShell 2.0, you'll need to either update them or use a workaround to prevent disruptions."