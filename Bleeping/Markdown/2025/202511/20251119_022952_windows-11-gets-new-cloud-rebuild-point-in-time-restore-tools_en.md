# Windows 11 gets new Cloud Rebuild, Point-in-Time Restore tools

![Windows 11](https://www.bleepstatic.com/content/hl-images/2024/07/18/Windows--11.jpg)

Microsoft announced two new Windows 11 recovery features today at the Ignite developer conference, called Cloud Rebuild and Point-in-Time Restore (PITR), that aim to reduce downtime and make it easier to recover from system failures or faulty updates.

The new recovery features are part of Microsoft's [Windows Resiliency Initiative](https://blogs.windows.com/windowsexperience/2025/06/26/the-windows-resiliency-initiative-building-resilience-for-a-future-ready-enterprise/) and are designed to help organizations quickly restore devices when a device is no longer able to start or function properly.

The first feature, Point-in-Time Restore (PITR), allows users and IT administrators to roll back a Windows 11 system to an earlier, healthy snapshot within minutes.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Like System Restore, PITR restores an operating system, its settings, and system files to a previously stored state. However, Point-in-Time Restore builds on the System Restore feature by taking a complete snapshot of the system at different points in time, so it can also restore local files and applications.

Microsoft says this feature will enter preview this week in an upcoming Windows 11 Insider preview build.

Microsoft is also introducing Cloud Rebuild, a tool that can remotely trigger a complete reinstall of Windows 11 from the cloud for devices experiencing persistent problems or becoming inoperable.

"Through the Intune portal, admins will be able to select the desired Windows release and language, triggering the PC to download installation media and rebuild itself," [explains Microsoft](https://blogs.windows.com/windowsexperience/2025/11/18/preparing-for-whats-next-windows-security-and-resiliency-innovations-help-organizations-mitigate-risks-recover-faster-and-prepare-for-the-era-of-ai/).

"The process leverages Autopilot for zero-touch provisioning, ensuring MDM enrollment and policy compliance post-rebuild. User data and settings restoration is streamlined via OneDrive and Windows Backup for Organizations. This approach will reduce downtime from hours—or days—to a fraction of that time."

Microsoft says that both of these features will be integrated directly within Microsoft Intune in the first half of 2026, allowing Windows admins to trigger recovery actions remotely, coordinate enterprise-wide remediation, and control Windows Recovery Environment (WinRE) functionality directly from Intune. 

Earlier this month, Microsoft began testing an [updated version of Quick Machine Recovery (QMR)](https://www.bleepingcomputer.com/news/microsoft/microsoft-testing-faster-quick-machine-recovery-in-windows-11/), a tool designed to help administrators resolve Windows boot failures without requiring physical access to a device.

![Quick Machine Recovery in the Advanced Startup menu](https://www.bleepstatic.com/images/news/Microsoft/windows-11/q/quick-machine-recovery/quick-machine-recovery.jpg)

**Windows 11 Quick Machine Recovery settings**  
_Source: Microsoft_

When Windows 11 encounters a boot failure caused by a configuration change, problematic drive, or update, it will automatically launch the Windows Recovery Environment, load QMR, and send crash information to Microsoft.

Based on the analysis of this data, Microsoft can remotely apply fixes such as removing problematic drivers or updates and changing configuration settings.

Microsoft says the latest release improves on the QMR boot-repair process by performing a single scan to detect and resolve issues, rather than repeatedly searching for a solution in a loop.