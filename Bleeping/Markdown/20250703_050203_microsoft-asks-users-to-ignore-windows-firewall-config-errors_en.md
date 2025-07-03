# Microsoft asks users to ignore Windows Firewall config errors

![Windows](https://www.bleepstatic.com/content/hl-images/2025/04/02/Windows-11.jpg)

Microsoft asked customers this week to disregard incorrect Windows Firewall errors that appear after rebooting their systems following the installation of the June 2025 preview update.

These warnings are logged in the Event Viewer as 'Event 2042' for Windows Firewall with Advanced Security, with a 'Config Read Failed' warning and a 'More data is available' message.

Microsoft added that this known issue is caused by a new feature that's still under development and hasn't yet been fully integrated with the operating system.

"Following installation of the June 2025 Windows non-security preview update ([KB5060829](https://www.bleepingcomputer.com/news/microsoft/windows-11-kb5060829-update-released-with-38-new-changes-fixes/)), security event logs might include an error event related to Windows Firewall With Advanced Security, which can be safely ignored," the company [said](https://learn.microsoft.com/en-us/windows/release-health/status-windows-11-24h2#3355msgdesc) on the Windows release health dashboard.

"Please note Windows Firewall is expected to function normally, and no action is required to prevent or resolve this error event. This event is related to a feature that is currently under development and not fully implemented."

These incorrect firewall errors will only appear on Windows 11 24H2 systems, but they shouldn't impact any Windows processes associated with this event.

Microsoft is currently working on a fix for this known issue and will provide an update when more details are available.

In recent months, Redmond has dealt with similar issues affecting other Windows features, resulting in more erroneous warnings with no actual impact.

In April, the company resolved a bug that [caused incorrect BitLocker drive encryption errors](https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-incorrect-bitlocker-encryption-errors/) on Windows 10 and Windows 11 devices due to a reporting issue. Redmond acknowledged this bug [in October](https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-incorrect-bitlocker-encryption-errors/) and stated that it only impacted managed Windows environments where drive encryption was enforced for the operating system and fixed drives.

The same month, Microsoft [confirmed](https://www.bleepingcomputer.com/news/microsoft/microsoft-tells-windows-users-to-ignore-winre-install-errors/) and fixed another known issue that [triggered invalid 0x80070643 failure errors](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-bug-causing-incorrect-windows-recovery-errors/) after installing the April 2025 Windows Recovery Environment (WinRE) updates.