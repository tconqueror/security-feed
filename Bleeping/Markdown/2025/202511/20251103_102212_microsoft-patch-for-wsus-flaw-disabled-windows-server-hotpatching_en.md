# Microsoft: Patch for WSUS flaw disabled Windows Server hotpatching

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/05/16/Windows-Server.jpg)

An out-of-band (OOB) security update that patches an actively exploited Windows Server Update Service (WSUS) vulnerability has broken hotpatching on some Windows Server 2025 devices.

[KB5070881](https://support.microsoft.com/en-us/topic/october-23-2025-kb5070881-os-build-26100-6905-out-of-band-8e7ac742-6785-4677-87e4-b73dd8ac0122), the emergency update causing this issue, was released on the same day that several cybersecurity companies confirmed the critical-severity [CVE-2025-59287](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59287) remote code execution (RCE) flaw [was being exploited in the wild](https://www.bleepingcomputer.com/news/security/hackers-now-exploiting-critical-windows-server-wsus-flaw-in-attacks/). The Netherlands National Cyber Security Centre (NCSC-NL) confirmed the companies' findings, warning IT admins of the increased risk given that [a PoC exploit is already available](http://hawktrace.com/blog/CVE-2025-59287).

Days later, the Cybersecurity and Infrastructure Security Agency (CISA) ordered U.S. government agencies to secure their systems after adding it to its catalog of security flaws that have been abused in attacks. The Shadowserver Internet watchdog group [is now tracking](https://dashboard.shadowserver.org/statistics/iot-devices/time-series/?date%5Frange=7&vendor=microsoft&model=windows+server+update+services+%28open%29&dataset=count&limit=100&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) over 2,600 WSUS instances with the default ports (8530/8531) exposed online, although it didn't share how many have already been patched.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

However, in an update to the original KB5070881 support document, Microsoft says that some of the Hotpatch-enrolled Windows Server 2025 systems have now lost their hotpatch enrollment status after receiving the OOB update that addresses the CVE-2025-59287 vulnerability.

"A very limited number of Hotpatch-enrolled machines received the update before the issue was corrected. The update is now offered only to machines that are not enrolled to receive Hotpatch updates," [Microsoft says](https://support.microsoft.com/en-us/topic/october-23-2025-kb5070881-os-build-26100-6905-out-of-band-8e7ac742-6785-4677-87e4-b73dd8ac0122). "This issue only impacts Windows Server 2025 devices and virtual machines (VMs) enrolled to receive Hotpatch updates."

Microsoft has stopped offering the KB5070881 update to Hotpatch-enrolled Windows Server 2025 devices, and states that those who have already installed it will no longer receive Hotpatch updates in November and December.

They will instead be offered the regular monthly security updates, which will require a restart, and will join the hotpatching rollout after installing the planned baseline for January 2026.

## New security update doesn't break hotpatching

Luckily, admins who have only downloaded the buggy update and have yet to deploy it can install [the KB5070893 security update](https://support.microsoft.com/en-us/topic/october-24-2025-kb5070893-os-build-26100-6905-security-update-for-windows-server-update-services-78f3720c-9511-4deb-b0d7-7bed2016fefd) (released one day after KB5070881 and specifically designed to patch the CVE-2025-59287 flaw without breaking hotpatching) by going into Settings > Windows Update and selecting Pause updates. Next, they have to unpause and scan for updates to receive the correct update.

"Hotpatch-enrolled machines that have not installed this update will be offered the October 24, 2025, Security Update for Windows Server Update Services (KB5070893) on top of the planned baseline update for October 2025 ([KB5066835](https://support.microsoft.com/topic/october-14-2025-baseline-58e80013-ba94-46ad-a56c-b6691d2405ad))," Microsoft added.

"Machines installing KB5070893 will remain 'on the Hotpatch train' and will continue to receive Hotpatch updates in November and December. Only those machines that have WSUS enabled will be prompted to restart after installing the Security Update, KB5070893."

To address the CVE-2025-59287 RCE vulnerability, Microsoft has also turned off the display of synchronization error details within its WSUS error reporting.

Last week, Microsoft acknowledged a bug that [prevented users from quitting the Windows 11 Task Manager](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-task-manager-wont-quit-after-kb5067036-update/) after installing the October 2025 optional update. Additionally, it [fixed the Windows 11 Media Creation Tool (MCT)](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-media-creation-tool-broken-on-some-windows-pcs/) and resolved [0x800F081F update errors](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-0x800f081f-errors-causing-windows-update-failures/) affecting Windows 11 24H2 systems since January.