# Microsoft: Some Windows PCs fail to shut down after January update

![Windows 11](https://www.bleepstatic.com/content/hl-images/2025/11/11/Windows_11.jpg)

Microsoft has confirmed a new issue that prevents Windows 11 23H2 devices with System Guard Secure Launch enabled from shutting down.

System Guard Secure Launch is a Windows security feature designed to protect the boot process from firmware-level attacks and malware such as rootkits.

According to a release health dashboard update on Thursday, this known issue affects only systems running Enterprise and IoT Windows editions with the [KB5073455](https://support.microsoft.com/help/5073455) cumulative update installed.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"After installing the January 13, 2026, Windows security update (KB5073455) for Windows 11, version 23H2, some PCs with Secure Launch are unable to shut down or enter hibernation. Instead, the device restarts," [Microsoft explained](https://learn.microsoft.com/en-us/windows/release-health/status-windows-11-23h2#devices-with-secure-launch-might-fail-to-shut-down-or-hibernate) in a Windows release health dashboard update on Thursday.

"Secure Launch uses virtualization-based security to protect the system from firmware-level threats during startup. KB5073455 is only offered for Enterprise and IoT editions of Windows 11, versions 23H2."

Until a permanent fix is available for this bug, Microsoft has shared a temporary workaround that requires affected users to shut down their device from the command prompt by running the following command:

```
shutdown /s /t 0
```

However, at the moment, there is no workaround for systems configured to enter hibernation.

"Until this issue is resolved, please ensure you save all your work, and shut down when you are done working on your device to avoid the device running out of power instead of hibernating," Microsoft added.

Microsoft is also working to [address a bug](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-update-blocks-access-to-cloud-pc-sessions/) triggered by the January 2026 [KB5074109](https://support.microsoft.com/help/5074109) Windows security update that causes connection failures and authentication errors during Remote Desktop connections to Cloud PC sessions.

On Tuesday, Microsoft [fixed another known issue](https://www.bleepingcomputer.com/news/microsoft/microsoft-updates-windows-dll-that-triggered-security-alerts/) causing security applications to flag a core Windows component on client (Windows 10 and Windows 11) and server (Windows Server 2012 through Windows Server 2025) platforms.