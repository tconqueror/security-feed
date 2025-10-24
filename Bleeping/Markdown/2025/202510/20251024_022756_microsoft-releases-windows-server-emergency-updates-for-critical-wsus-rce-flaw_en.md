# Windows Server emergency patches fix WSUS bug with PoC exploit

![Windows](https://www.bleepstatic.com/content/hl-images/2025/08/22/Windows.jpg)

Microsoft has released out-of-band (OOB) security updates to patch a critical-severity Windows Server Update Service (WSUS) vulnerability with publicly available proof-of-concept exploit code.

WSUS is a Microsoft product that enables IT administrators to manage and deliver Windows updates to computers within their network.

Tracked as [CVE-2025-59287](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59287) and patched during [this month's Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-october-2025-patch-tuesday-fixes-6-zero-days-172-flaws/), this remote code execution (RCE) security flaw affects only Windows servers with the WSUS Server Role enabled, a feature that isn't enabled by default.

The vulnerability can be exploited remotely in low-complexity attacks that do not require user interaction, allowing threat actors without privileges to target vulnerable systems and run malicious code with SYSTEM privileges. This makes it potentially wormable between WSUS servers.

"Windows servers that do not have the WSUS server role enabled are not vulnerable to this vulnerability. If the WSUS server role is enabled, the server will become vulnerable if the fix is not installed before the WSUS server role is enabled," [Microsoft explained](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59287).

"A remote, unauthenticated attacker could send a crafted event that triggers unsafe object deserialization in a legacy serialization mechanism, resulting in remote code execution."

Microsoft has released security updates for all impacted Windows Server versions and advised customers to install them as soon as possible:

* Windows Server 2025 ([KB5070881](https://support.microsoft.com/help/5070881))
* Windows Server, version 23H2 ([KB5070879](https://support.microsoft.com/help/5070879))
* Windows Server 2022 ([KB5070884](https://support.microsoft.com/help/5070884))
* Windows Server 2019 ([KB5070883](https://support.microsoft.com/help/5070883))
* Windows Server 2016 ([KB5070882](https://support.microsoft.com/help/5070882))
* Windows Server 2012 R2 ([KB5070886](https://support.microsoft.com/help/5070886))
* Windows Server 2012 ([KB5070887](https://support.microsoft.com/help/5070887))

As Microsoft revealed in a Thursday update to the original security advisory, a proof-of-concept exploit for CVE-2025-59287 is now also available online, making it even more critical to patch vulnerable servers immediately.

Microsoft also shared workarounds for admins who can't immediately install these emergency patches, including disabling the WSUS Server Role to remove the attack vector or blocking all inbound traffic to Ports 8530 and 8531 on the host firewall to render WSUS non-operational.

However, it's important to note that Windows endpoints will stop receiving updates from the local server after WSUS is disabled or the traffic is blocked.

"This is a cumulative update, so you do not need to apply any previous updates before installing this update, as it supersedes all previous updates for affected versions," Microsoft added.

"If you haven't installed the October 2025 Windows security update yet, we recommend you apply this OOB update instead. After you install the update you will need to reboot your system."