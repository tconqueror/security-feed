# Microsoft: June Windows Server security updates cause DHCP issues

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/05/16/Windows-Server.jpg)

Microsoft acknowledged a new issue caused by the June 2025 security updates, causing the DHCP service to freeze on some Windows Server systems.

On Windows Server systems, the Dynamic Host Configuration Protocol (DHCP) Server service automates assigning IP addresses and other network configurations, reducing network administration and ensuring reliable IP address configuration in Windows networks.

In affected environments, the new DHCP known issue confirmed by Microsoft over the weekend prevents renewals of unicast IP addresses from applying correctly across network devices.

"The DHCP Server service might intermittently stop responding after installing this security update. This issue affects IP renewal for clients," the company says in updates added to security advisories issued during this month's Patch Tuesday.

The list of affected Windows versions and the updates causing this issue includes:

* Windows Server 2016 ([KB5061010](https://support.microsoft.com/en-us/topic/june-10-2025-kb5061010-os-build-14393-8148-6766ca26-dc1e-4592-b959-d0c92d6deb6f))
* Windows Server 2019 ([KB5060531](https://support.microsoft.com/en-gb/topic/june-10-2025-kb5060531-os-build-17763-7434-32fce7e7-305d-4d32-913f-3fdc0709a763))
* Windows Server 2022 ([KB5060526](https://support.microsoft.com/en-us/topic/june-10-2025-kb5060526-os-build-20348-3807-4e9453c4-6602-48ea-b349-689cd66dfdb9))
* Windows Server 2025 ([KB5060842](https://support.microsoft.com/en-us/topic/june-10-2025-kb5060842-os-build-26100-4349-47ff300b-2a04-440c-9476-2860d04fce8d))

"We are working on releasing a resolution in the coming days and will provide more information when it is available," Microsoft added.

During this month's Patch Tuesday, Redmond addressed another known Windows Server issue that [triggered app or service failures](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-unreachable-windows-server-domain-controllers/) after causing some Windows Server 2025 domain controllers to become unreachable after restarts.

The June 2025 cumulative updates also [fixed authentication problems](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-windows-server-auth-issues-caused-by-april-updates/) on Windows Server domain controllers triggered after deploying the April 2025 security updates.

In May, Microsoft also [issued out-of-band updates](https://www.bleepingcomputer.com/news/microsoft/windows-server-emergency-update-fixes-hyper-v-vm-freezes-restart-issues/) to address a bug causing some Hyper-V virtual machines with Windows 10, Windows 11, and Windows Server to restart or freeze unexpectedly.

One month earlier, the company [released another set of emergency updates](https://www.bleepingcomputer.com/news/microsoft/new-windows-server-emergency-updates-fix-container-launch-issue/) that resolved a known issue preventing Windows containers from launching on Windows Server 2019, Windows Server 2022, and Windows Server 2025 systems.

These launch problems affected only containers under Hyper-V isolation mode, allowing multiple containers to run simultaneously on a single Windows host inside separate virtual machines.