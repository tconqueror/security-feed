# Windows 11 KB5067036 update rolls out Administrator Protection feature

![Windows 11](https://www.bleepstatic.com/content/hl-images/2024/07/18/Windows-11.jpg)

​​Microsoft has released the KB5067036 preview cumulative update for Windows 11 24H2 and 25H2, which begins the rollout of the Administrator Protection cybersecurity feature and an updated Start Menu.

The [KB5067036](https://support.microsoft.com/en-us/topic/october-28-2025-kb5067036-os-builds-26200-7019-and-26100-7019-preview-ec3da7dc-63ba-4b1d-ac41-cf2494d2123a#id0ebdj=gradual%5Frollout) update is part of the company's optional non-security preview update schedule, which releases updates at the end of each month to test new fixes and features coming to the next month's Patch Tuesday.

Unlike regular Patch Tuesday cumulative updates, monthly non-security preview updates do not include security updates and are optional.

You can install the KB5067036 update by opening **Settings**, clicking on **Windows Update,** and then **"Check for Updates**."

Because this is an optional update, you will be asked if you want to install it by clicking the "Download and install" link unless you have the "Get the latest updates as soon as they're they're available" option enabled, which will cause the update to automatically install.

![KB5067036 preview update](https://www.bleepstatic.com/images/news/Microsoft/windows-11/KB5064081.jpg)

_KB5067036 preview update_ 
_Source: BleepingComputer_

You can also manually download and install the KB5067036 preview update from the [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5064081).

## Windows 11 KB5067036 highlights

Once installed, this optional cumulative release will update Windows 11 24H2 systems to build 26100.5074 and Windows 11 25H2 to 26100.7019.

The October 2025 preview update features numerous new additions, including fixes for bugs that [broke the Media Creation Tool](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-11-media-creation-tool-broken-on-windows-10-pcs/) and caused [problems making HTTP/2 connections](https://www.bleepingcomputer.com/news/microsoft/windows-11-updates-break-localhost-127001-http-2-connections/) to web services running on the localhost.

One of the features gradually rolling out to users is a redesigned Start Menu, including new categories and grid views, a responsive layout, and a scrollable "All" section, so it's easier to find the apps you are looking for.

Another highly anticipated feature is the rollout of the new [Administrator Protection feature](https://www.bleepingcomputer.com/news/microsoft/microsoft-shares-more-details-on-windows-11-admin-protection/), which reduces the risk of malicious programs running commands or performing actions that require administrative privileges.

"Administrator protection requires that a user verify their identity with Windows Hello integrated authentication before allowing any action that requires administrator privileges," [explains Microsoft](https://techcommunity.microsoft.com/blog/windows-itpro-blog/administrator-protection-on-windows-11/4303482).

"These actions include installing software, changing system settings like the time or the registry, and accessing sensitive data. Administrator protection minimizes the risk of the user making a system-level change by mistake, and, more importantly, helps prevent malware from making silent changes to the system without the user knowing."

![Administrator Protection feature](https://www.bleepstatic.com/images/news/Microsoft/a/administrator-protection/administrator-protection.png)

**Administrator Protection feature**  
_Source: Microsoft_

The following features are rolling out immediately to all Windows 11 users:

* **\[Authentication\]**  
   * Fixed: An issue that caused an ACCESS\_DENIED error when users attempted to change passwords remotely on member servers or workgroup devices, even when they had the required permissions.  
   * Fixed: This update addresses an issue that affects the Kerberos Key Distribution Center (KDC) service on server domain controllers. When the KDC service is manually stopped, the server cannot retrieve Kerberos tickets.  
   * After installing the September 2025 security update for Windows Server 2022 ([KB5065432](https://support.microsoft.com/en-us/topic/september-9-2025-kb5065432-os-build-20348-4171-78d6c76c-f2cc-40d5-bb3a-290abf4a0321)), you might experience repeated reauthentication issues with Active Directory Federation Services (AD FS).
* **\[Display\]** Fixed: After the latest updates, text may not render correctly when editing content within a multiline text box in certain apps.
* **\[Installation (known issue)\]** Fixed: The Media Creation tool l (version 26100.6584), released on September 29, 2025, might not work as expected on devices with Arm64\. Users may encounter an error message such as: _“We’re not sure what happened, but we're unable to run this tool on your PC."_ This is a known issue for Windows 11, version 25H2.
* **\[Media (known issue)\]** Fixed: This update addresses an issue where protected content playback fails on some machines after installing [KB5064081](https://support.microsoft.com/en-us/topic/august-29-2025-kb5064081-os-build-26100-5074-preview-3f9eb9e1-72ca-4b42-af97-39aace788d93).
* **\[Networking (known issue)**\] Fixed: An issue occurred where web servers using HTTP.sys (such as Internet Information Services \[IIS\]) rejected incoming HTTP requests with a “NOT\_SUPPORTED” error.
* **\[Screen readers\]** Fixed: After the latest updates, screen readers may unexpectedly say "legacy window" without reading out the window contents when interacting with certain apps.

Microsoft is also gradually rolling out the following features to users after installing the update:

* **\[Start menu\]** _**New!**_ The redesigned **Start menu**, built to help you access your apps more quickly and smoothly. Its redesigned layout makes it easier than ever to find what you need.  
   * **Scrollable ‘All’ section:** The main page now includes a scrollable “All” section, making it easier to find apps.  
   * **Category and grid views**: Switch between two new views—category view, which groups apps by type and highlights frequently used ones, and grid view, which lists apps alphabetically with more horizontal space for easier scanning. The menu remembers your last selected view.  
   * **Responsive layout:** The Start menu adapts to your screen size. Larger displays show more pinned apps, recommendations, and categories by default. Sections like Pinned and Recommended expand or collapse based on content. You can customize these views under **Settings** \> **Personalization** \> **Start.**  
   * **Phone Link integration:** A new mobile device button next to Search lets you expand or collapse content from your connected phone. This feature supports Android and iOS devices in most markets and will roll out to the European Economic Area (EEA) in 2025.
* **\[File Explorer\]**  
   * _**New!**_ 3 Recommended files in **File Explorer Home** are now available for personal Microsoft accounts and local accounts. These files include content you frequently use, have recently downloaded, or added to your **File Explorer Gallery**. If you prefer not to see the recommended section in File Explorer Home, you can turn it off in **File Explorer Folder Options**. When this feature is turned off, folders pinned to **Quick Access** will appear instead.  
   * _**New!**_ StorageProvider APIs are now available for cloud providers to integrate with File Explorer Home. Developers can learn to [enable the system to query for suggested files](https://learn.microsoft.com/uwp/api/windows.storage.provider.istorageprovidersuggestionshandler?view=winrt-26100).  
   * Fixed: The **File Explorer context menu** might unexpectedly switch back and forth between the normal view and **Show More Options** on each right click.  
   * Fixed: When opening a folder from another app (for example, opening the **Downloads folder** from a browser), your custom view — including sorting files by name, changing the icon size, or removing grouping — unexpectedly resets back to default.  
   * Fixed: The body of the **File explorer** window might no longer respond to mouse clicks after invoking the **context menu**.  
   * Fixed: Extracting very large archive folders (1.5gb+) might fail with a “Catastrophic Error” (**error code 0x8000FFFF**).  
   * Fixed: **File Explorer** might become unresponsive when opening **Home**.
* **\[Lock screen\] _New!_** The new battery icons, which include color indicators and battery percentage, now appear in the lower-right corner of the lock screen. This feature makes it easier to check your device’s charging status and battery level at a glance. To learn more about the battery icon feature, see **Taskbar**.
* **\[Microsoft 365 Copilot\]** _**New!**_ A new **Microsoft 365 Copilot page** has been added to the **Get Started** experience for commercial devices with an active Microsoft 365 subscription. This page helps you learn about Microsoft 365 Copilot features and begin using them more easily.
* **\[Settings\]** _**New!**_ The “Email & accounts” section is now called “Your accounts.” You manage all your accounts under **Settings** \> **Accounts**.
* **\[Taskbar\]**  
   * _**New!**_ The battery icons have been updated to make it easier to check your PC’s status at a glance. Color indicators show charging and battery levels: green indicates the PC is charging and in good condition, yellow shows that battery saver mode is on at 20% or below, and red signals a critically low battery. Simplified overlays keep the progress bar visible, and the icons appear in the system tray, Quick Settings, and Settings, with Lock screen support coming soon. To show the battery percentage next to the icon, go to **Settings** \> **System** \> **Power & battery**, then turn on Battery Percentage. You can still view detailed battery information by hovering over the battery icon or opening the **Power & battery** settings.​​​​  
   * **\[Administrator Protection Preview\] _New!_** [Administrator protection](https://techcommunity.microsoft.com/blog/windows-itpro-blog/administrator-protection-on-windows-11/4303482) aims to protect free floating admin rights for administrators. It enables users to perform administrative tasks using just-in-time privileges. This feature is turned off by default and can be enabled using OMA-URI in Microsoft Intune or through Group Policy.  
   * **\[Display and Graphics\]**  
         * Fixed: Apps and browsers might display partially unresponsive onscreen content when other maximized or full-screen apps are updating in the background. This issue is especially noticeable when scrolling, as only parts of the window content might update.  
         * Fixed: After you install [KB5064081](https://support.microsoft.com/en-us/topic/august-29-2025-kb5064081-os-build-26100-5074-preview-3f9eb9e1-72ca-4b42-af97-39aace788d93), some videos and games might be unexpectedly red.  
         * Fixed: If the **Connected Devices Platform Service** is disabled, Settings might stop responding or close unexpectedly when you try to open **Settings** \> **System** \> **Display**, including when launched from the **desktop context menu**.  
   * **\[Input\]** Fixed: An issue with microsoft.ink.dll and related APIs might cause pen and handwriting input to stop responding in apps or lead to apps closing unexpectedly due to thrown exceptions.  
   * **\[Narrator**\] Fixed: Narrator fails when trying to launch it while setting up Windows using an ISO.  
   * **\[Open and Save Dialog\]** Fixed: Certain apps might become unresponsive when launching the **Open or Save Dialog**.  
   * **\[Remote Credential Guard\]** Fixed: Remote Credential Guard scenarios between the latest Windows 11 builds and Windows Server 2022 or earlier might unexpectedly fail.  
   * **\[Sign in to your PC\]:** Improved: Made underlying changes to improve the performance of loading the taskbar after unlocking your PC from sleep. This also helps in cases where the password field and other sign-in screen contents didn’t render when transitioning from the lock screen to the sign-in screen after sleep.  
   * **\[Task Manager\]** Fixed: Some apps might unexpectedly not be grouped with their processes.  
   * **\[Windows Update\]**  
         * Improved: Addressed underlying issue which can cause **“Update and shutdown”** to not actually shut down your PC after updating.  
         * Improved: Addressed underlying issue which can cause Windows Update to fail to install with **error 0x800f0983**.

Microsoft says that there are currently no known issues with this update.

The full release notes for KB5067036 can be found in this [support bulletin](https://support.microsoft.com/en-us/topic/october-28-2025-kb5067036-os-builds-26200-7019-and-26100-7019-preview-ec3da7dc-63ba-4b1d-ac41-cf2494d2123a#id0ebdj=gradual%5Frollout).