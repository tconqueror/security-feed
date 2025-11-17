# Microsoft: Windows 10 KB5068781 ESU update may fail with 0x800f0922 errors

![Windows 10](https://www.bleepstatic.com/content/hl-images/2021/04/17/windows-10-sapphire.jpg)

Microsoft has confirmed it is investigating a bug causing the Windows 10 KB5068781 extended security update to fail to install with 0x800f0922 errors on devices with corporate licensing.

KB5068781 is the [first Windows 10 extended security update](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-kb5068781-the-first-windows-10-extended-security-update/) and was released on November 11 as part of [Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-november-2025-patch-tuesday-fixes-1-zero-day-63-flaws/).

Since then, some business Windows 10 users have reported that the KB5068781 update is failing to install on certain devices.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"We are currently experiencing the same issue with this KB5068781 across our managed Win10 devices, despite purchasing and applying the ESU license (MAK key) to all our devices," wrote a BleepingComputer reader.

"The update appears to install successfully, but after a restart, it fails to apply and rolls back with the common error 0x800f0922."

Microsoft has now confirmed that they are aware of and investigating the issue, stating it only impacts Windows subscription activation through the Microsoft 365 Admin Center.

"Some Windows 10 devices enrolled in Extended Security Updates (ESU) might fail to install the November 2025 security update (the Originating KBs listed above) with error 0x800f0922 (CBS\_E\_INSTALLERS\_FAILED)," explains Microsoft.

"This issue is isolated to devices activated via [Windows subscription activation](https://learn.microsoft.com/windows/deployment/windows-subscription-activation?pivots=windows-10) through the Microsoft 365 Admin Center."

Unfortunately, there is no ETA for when a fix will be available and Microsoft has not provided any workarounds to resolve these errors.

In addition to the install errors, Windows admins in corporate environments have reported \[[1](https://www.reddit.com/r/SCCM/comments/1ovetfu/kb5068781%5Fsupersedes%5Flast%5Fpatch%5Fof%5Fw10/), [2](https://www.reddit.com/r/sysadmin/comments/1owu7t9/purchased%5Fand%5Finstalled%5Fesu%5Fproduct%5Fkey%5Ffor%5F1/)\] that not all of their Windows 10 devices are showing as needing the new KB5068781 ESU update, even when they are appropriately licensed to receive it.

To help organizations improve their patching workflows and reduce the risk of issues like this, BleepingComputer will be hosting a [December 2 webinar with Action1](http://onlinexperiences.com/scripts/Server.nxp?LASCmd=AI:4;F:QS!10100&ShowUUID=84B6E94D-9C81-4F9B-841F-7D435B7FF576&utm%5Fsource=bleepingcomputer&utm%5Fmedium=esufail%5Fart&utm%5Fcampaign=sc-cybercast-bc-2025-dec-a1) on modern patch management.