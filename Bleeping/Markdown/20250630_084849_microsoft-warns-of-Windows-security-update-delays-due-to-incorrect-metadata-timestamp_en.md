# Microsoft warns of Windows update delays due to wrong timestamp

![Windows](https://www.bleepstatic.com/content/hl-images/2024/12/16/Windows.jpg)

Microsoft has confirmed a new known issue causing delivery delays for June 2025 Windows security updates due to an incorrect metadata timestamp.

As Redmond explains in recent advisory updates, this bug affects Windows 10 and Windows 11 systems in environments with quality update deferral policies that enable admins to delay update installation on managed devices.

While update deployment delays are an expected result when using such policies, the wrong timestamp for the June security updates will postpone them beyond the period specified by administrators, potentially exposing unpatched systems to attacks.

"Some devices in environments where IT admins use quality update (QU) deferral policies might experience delays in receiving the June 2025 Windows security update," Microsoft [explains](https://support.microsoft.com/en-us/topic/june-10-2025-kb5060842-os-build-26100-4349-47ff300b-2a04-440c-9476-2860d04fce8d#ID0EFF). "Although the update was released on June 10, 2025, its update metadata timestamp reflects a date of June 20, 2025. This discrepancy might cause devices with configured deferral periods to receive the update later than expected."

While still investigating this known issue, Microsoft has provided Windows admins with several temporary workarounds to accelerate deployment for the June 2025 updates until a fix is available.

To achieve this, Redmond recommends creating an expedited deployment policy to bypass deferral settings and ensure that the updates are delivered immediately in organizations using Windows Autopatch. As an alternative, admins can modify deferral configurations or deployment rings to minimize the delay for impacted devices.

As detailed in a [new Microsoft 365 Message Center advisory](https://admin.microsoft.com/#/MessageCenter/:/messages/AH1104938), this can be done by going through the following steps:

1. Go to Intune \\ Devices \\ Windows Updates.
2. Click on the Quality Updates Tab.
3. Click "Create Expedite Policy".
4. Select the 6B release, fill out other relevant details, and assign desired Entra groups.
5. Validate your update as normal and assign additional groups to the policy to finish rolling out the latest updates to your devices.

"This delay issue affects only the timing of update availability for organizations using QU deferral policies and doesn't impact the quality or applicability of the update," Microsoft added. "We will not change the metadata value from the current June 20, 2025, value. This workaround is the final resolution we will provide for this issue."

Earlier this month, Microsoft [rolled out a configuration update](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-known-issue-that-breaks-windows-11-updates/) (KB5062324) to address a known issue that caused update failures after the scan for Windows updates stopped responding on some Windows 11 systems.

In May, Redmond [fixed another bug](https://www.bleepingcomputer.com/news/microsoft/microsoft-pushes-fix-for-windows-11-update-0x80240069-errors/) blocking Windows 11 24H2 feature updates from being delivered via Windows Server Update Services (WSUS) after installing the April 2025 security updates.

One month earlier, it addressed what it described as a "latent code issue" that was [causing some PCs to be upgraded to Windows 11](https://www.bleepingcomputer.com/news/microsoft/microsoft-some-devices-offered-windows-11-upgrades-despite-intune-blocks/) overnight despite Intune policies designed to block Windows 11 upgrades.

In May, the company also revealed that it aims [to update all software on your PC](https://www.bleepingcomputer.com/news/microsoft/microsoft-wants-windows-to-update-all-software-on-your-pc/) via a new update orchestration platform built on top of the existing Windows Update infrastructure, a platform that aims to unify the updating system for all apps, drivers, and system components across all Windows systems.