# Microsoft: Windows Server hotpatching to require subscription

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/11/12/Windows-Server.jpg)

Microsoft has announced that it will soon introduce paid subscriptions for Windows Server 2025 hotpatching, a service that enables admins to install security updates without restarting.

The company urged admins to try hotpatching free of charge before it becomes generally available in July, when they'll have to pay for a subscription to test it.

However, Redmond also warned those currently testing Windows Server 2025 hotpatching in preview to disenroll on or before June 30 so that they're not automatically subscribed in July.

"Hotpatching for Windows Server 2025, made available in preview in 2024, will become generally available as a subscription service on July 1st, 2025. With hotpatching, we are taking what was previously an Azure-only capability and now making it available to Windows Server machines outside of Azure through Azure Arc," [Microsoft said](https://www.microsoft.com/en-us/windows-server/blog/2025/04/24/tired-of-all-the-restarts-get-hotpatching-for-windows-server/).

"Hotpatching is available at no charge to preview now, but starting in July with the subscription launch, hotpatching for Windows Server 2025 will be offered at a subscription of $1.50 USD per CPU core per month."

To use hotpatching in multi-cloud environments or on-premises, you will need a Hotpatch service subscription and an Azure Arc-connected server that runs Windows Server 2025 Standard or Datacenter.

To enable hotpatching on your server, connect it to Azure Arc using [these steps](https://learn.microsoft.com/en-us/azure/azure-arc/servers/onboard-windows-server?toc=%2Fwindows-server%2Fget-started%2Ftoc.json&bc=%2Fwindows-server%2Fbreadcrumbs%2Ftoc.json), then go to Azure Update Manager in the Azure Portal, select your Azure Arc-enabled server, and check the hotpatching option [as detailed here](http://learn.microsoft.com/en-us/azure/update-manager/manage-hot-patching-arc-machines?tabs=manage-single%2Chotpatch-scale).

Hotpatching has been available since February 2022 for [Windows Server 2022 Datacenter: Azure Edition](https://www.bleepingcomputer.com/news/microsoft/microsoft-announces-hotpatching-for-windows-server-azure-vms/), when Microsoft announced its general availability for Windows Server Azure Edition core virtual machines.

On devices where hotpatching is toggled on, Windows deploys security updates by patching the in-memory code of running processes without restarting them after each installation and without rebooting the device.

However, servers still require reboots after installing updates delivered through the regular (non-Hotpatch) Windows update channel, which aren't included in the Hotpatch program. Two examples of updates that can't be installed without a restart are non-Windows updates (such as .NET patches) and Windows non-security updates.

Microsoft also started testing hotpatching in public preview for Windows Server 2025 [in September 2024](https://www.bleepingcomputer.com/news/microsoft/windows-server-2025-hotpatching-in-public-preview-installs-security-updates-without-restarts/) and on Windows 11 24H2 and Windows 365 two months later, [in November 2024](https://www.bleepingcomputer.com/news/microsoft/microsoft-now-testing-hotpatch-on-windows-11-24h2-and-windows-365/).

Starting April 2025, hotpatch updates are [generally available for business customers](https://www.bleepingcomputer.com/news/microsoft/microsoft-adds-hotpatching-support-to-windows-11-enterprise/) using Windows 11 Enterprise 24H2 on x64 (AMD/Intel) systems.