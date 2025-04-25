# Windows "inetpub" security fix can be abused to block future updates

![Microsoft](https://www.bleepstatic.com/content/hl-images/2024/01/26/microsoft-red-header.jpg)

A recent Windows security update that creates an ‘inetpub’ folder has introduced a new weakness allowing attackers to prevent the installation of future updates.

After people installed this month's [Microsoft Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-april-2025-patch-tuesday-fixes-exploited-zero-day-134-flaws/) security updates, Windows users [suddenly found an "inetpub" folder](https://www.bleepingcomputer.com/news/microsoft/windows-11-april-update-unexpectedly-creates-new-inetpub-folder/) owned by the SYSTEM account created in the root of the system drive, normally the C: drive.

It was strange to see this folder created as it is normally used to hold files associated with Microsoft's Internet Information Service web server, which was not installed on these devices.

In an update to a [security advisory](http://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-21204), Microsoft later confirmed that the C:\\inetpub folder was part of a fix for a Windows Process Activation elevation of privilege vulnerability tracked as CVE-2025-21204, with the company [warning not to delete the folder](https://www.bleepingcomputer.com/news/security/microsoft-windows-inetpub-folder-created-by-security-fix-dont-delete/).

"After installing the updates listed in the Security Updates table for your operating system, a new %systemdrive%\\inetpub folder will be created on your device," [confirmed Microsoft](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-21204#exploitability).

"This folder should not be deleted regardless of whether Internet Information Services (IIS) is active on the target device. This behavior is part of changes that increase protection and does not require any action from IT admins and end users."

However, cybersecurity expert Kevin Beaumont has demonstrated that this folder can be abused to prevent further Windows updates from being installed if it is created a certain way.

"I've discovered this fix introduces a denial of service vulnerability in the Windows servicing stack that allows non-admin users to stop all future Windows security updates," Kevin Beaumont.

In a new report, [Beaumont says](https://doublepulsar.com/microsofts-patch-for-cve-2025-21204-symlink-vulnerability-introduces-another-symlink-vulnerability-9ea085537741) that Windows users, even those without administrative privileges, can create a junction between C:\\inetpub and a Windows file, like C:\\windows\\system32\\notepad.exe using the following command.

```
mklink /j c:\inetpub c:\windows\system32\notepad.exe
```

A Windows junction is a special type of folder that redirects access to another folder on the same or another drive, making it appear as though the content exists in both locations.

When asked why this junction is preventing the update from being installed, Beaumont says he believes it's because the update expects a folder rather than a file.

"It works with basically any file, I think it's because the servicing stack expects c:\\inetpub to be a directory - but mklink allows you to make a junction to a file," Beaumont told BleepingComputer.

According to [Microsoft's documentation](http://learn.microsoft.com/en-us/windows/win32/fileio/hard-links-and-junctions), junctions are meant to be links between folders rather than between files. However, as you can see from the image earlier in the article, it is still possible to create one as shown in the image below.

![C:\inetpub junction pointing to C:\Windows\system32\notepad.exe](https://www.bleepstatic.com/images/news/Microsoft/w/inetpub/inetpub-junction.jpg)

**C:\\inetpub junction pointing to C:\\Windows\\system32\\notepad.exe**  
_Source: BleepingComputer_

With this junction created, if you attempt to install the April security update, it will not install correctly, giving a [0x800F081F error code](https://learn.microsoft.com/en-us/troubleshoot/windows-server/installing-updates-features-roles/fix-windows-update-errors). This code is related to the error "CBS\_E\_SOURCE\_MISSING," which means a package or file was not found.

![Windows 0x800F081F error after creating junction](https://www.bleepstatic.com/images/news/Microsoft/w/inetpub/windows-update-error.jpg)

**Windows 0x800F081F error after creating junction**  
_Source: BleepingComputer:_

Beaumont says he reported the bug to Microsoft, who has assigned it a "Medium" severity classification and closed his case, stating they will consider fixing it in the future.

"After careful investigation, this case is currently rated as a Moderate severity issue," [Microsoft emailed Beaumont](https://cyberplace.social/@GossiTheDog/114398293866746480).

"It does not meet MSRCs current bar for immediate servicing as the update fails to apply only if the 'inetpub' folder is a junction to a file and succeeds upon deleting the inetpub symlink and retrying."

BleepingComputer also contacted Microsoft about this bug on Wednesday but has not received a response yet.