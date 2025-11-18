# Microsoft: Windows 10 KB5072653 OOB update fixes ESU install errors

![Windows 10](https://www.bleepstatic.com/content/hl-images/2021/09/20/Windows.jpg)

Microsoft has released an emergency Windows 10 KB5072653 out-of-band update to resolve ongoing issues with installing the November extended security updates.

Windows 10 reached the end of support on October 14, 2025, and Microsoft no longer introduces new features or releases free security updates.

For individuals and business customers who wish to continue using Windows 10, Microsoft offers extended security updates (ESU).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Consumers can receive extended security updates for one additional year by either paying $30, backing up their Windows settings to their Microsoft account, or redeeming 1,000 Microsoft reward points.

Enterprise customers can purchase an ESU license for 3 years, bringing the total cost per device to $427.

As part of the November Patch Tuesday, Microsoft released the [first Windows 10 extended security update](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-kb5068781-the-first-windows-10-extended-security-update/). However, some consumer and business customers found that the update was not correctly offered to devices, or they [failed with 0x800f0922 (CBS\_E\_INSTALLERS\_FAILED) errors](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-10-kb5068781-esu-update-may-fail-with-0x800f0922-errors/).

## Microsoft releases emergency fix

Today, Microsoft has released the "KB5072653 Extended Security Updates (ESU) Licensing Preparation Package," which fixes the 0x800f0922 errors people have been encountering when attempting to install the ESU update.

"The organizations affected by this issue can resolve it by installing [KB5072653: Extended Security Updates (ESU) Licensing Preparation Package for Windows 10](https://support.microsoft.com/help/5072653), which was released on November 17, 2025." reads a Microsoft support bulletin.

"Once you install this preparation package ([KB5072653](https://support.microsoft.com/help/5072653)), you will be able to deploy the November 2025 security update ([KB5068781](https://support.microsoft.com/help/5068781))."

To install the update, a Windows device must be running Windows 10 22H2 and have the October 2025 [KB5066791](https://www.bleepingcomputer.com/news/microsoft/final-windows-10-patch-tuesday-update-rolls-out-as-support-ends/) cumulative update installed.

They can then check for new updates using Windows Update, and the KB5072653 will be automatically installed.

Microsoft says that once the KB5072653 update is installed and Windows has been restarted, users should rerun Windows Update to install the November extended security update successfully.

However, some corporate Windows admins have reported \[[1](https://www.reddit.com/r/SCCM/comments/1ovetfu/kb5068781%5Fsupersedes%5Flast%5Fpatch%5Fof%5Fw10/), [2](https://www.reddit.com/r/sysadmin/comments/1owu7t9/purchased%5Fand%5Finstalled%5Fesu%5Fproduct%5Fkey%5Ffor%5F1/)\] that WSUS and SCCM are not correctly indicating that a Windows 10 device needs the extended security update, even when it is correctly enrolled in the program.

Microsoft says it will release a new Scan Cab with updated metadata for this update to properly perform compliance update checks.

"A new Scan Cab including metadata for [KB5072653](https://support.microsoft.com/help/5072653) will be available in the near future for organizations that utilize cab files for compliance update checks. We will update this announcement once the new Scan Cab is available," explained Microsoft.

BleepingComputer contacted Microsoft to determine if this would resolve the issue reported by some Windows admins.

For more insights on modern patch management strategies and how organizations can streamline and strengthen their update workflows, BleepingComputer is hosting a **[December 2 webinar with Action1](https://onlinexperiences.com/scripts/Server.nxp?LASCmd=AI:4;F:QS!10100&ShowUUID=84B6E94D-9C81-4F9B-841F-7D435B7FF576&AffiliateData=bleepingcomputer%5Fesuoob%5Fart%5Fsc-cybercast-bc-2025-dec-a1)**.