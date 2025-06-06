# Microsoft shares script to restore inetpub folder you shouldn’t delete

![Windows](https://www.bleepstatic.com/content/hl-images/2021/05/17/0_Windows-headpic.jpg)

Microsoft has released a PowerShell script to help restore an empty 'inetpub' folder created by the April 2025 Windows security updates if deleted. As Microsoft previously warned, this folder helps mitigate a high-severity Windows Process Activation privilege escalation vulnerability.

In April, after installing the new security updates, Windows users [suddenly found](https://www.bleepingcomputer.com/news/microsoft/windows-11-april-update-unexpectedly-creates-new-inetpub-folder/) that an empty C:\\Inetpub folder was created. As this folder is associated with Microsoft's Internet Information Server, users found it confusing that it was created when the web server was not installed.

This caused some people to remove the folder, making them vulnerable again to the patched vulnerability. Microsoft said that users who removed it [can manually recreate it](https://www.bleepingcomputer.com/news/security/microsoft-windows-inetpub-folder-created-by-security-fix-dont-delete/) by installing Internet Information Services from the Windows "Turn Windows Features on or off" control panel.

Once IIS is installed, a new inetpub folder will be added to the root of the C:\\ drive, with files and the same SYSTEM ownership as the directory created by the April Windows security updates. Also, if you don't use IIS, you can uninstall it using the same Windows Features control panel to remove it, leaving the C:\\inetpub folder behind.

On Wednesday, in a new update to the CVE-2025-21204 advisory, the company also shared a [remediation script](https://www.powershellgallery.com/packages/Set-InetpubFolderAcl/1.0) that helps admins re-create this folder from a PowerShell shell using the following commands:

```
Install-Script -Name Set-InetpubFolderAcl

C:\Program` Files\WindowsPowerShell\Scripts\Set-InetpubFolderAcl.ps1
```

As Redmond explains, the script will set the correct IIS permissions to prevent unauthorized access and potential vulnerabilities related to CVE-2025-21204.

It will also update access control list (ACL) entries for the DeviceHealthAttestation directory on Windows Server systems to ensure it is secure if created by the February 2025 security updates.

![Running Set-InetpubFolderAcl](https://www.bleepstatic.com/images/news/u/1109292/2025/Using-Set-InetpubFolderAcl.png)

_Executing the script in Windows PowerShell (BleepingComputer)_

## ​Microsoft: "Don't delete it."

The security flaw ([CVE-2025-21204](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-21204)) mitigated by this inetpub folder (automatically created by April's security updates even on systems where the IIS web server platform was not previously installed) is caused by an improper link resolution issue in the Windows Update Stack.

This likely means that Windows Update may follow symbolic links on unpatched devices in a way that can let local attackers trick the OS into accessing or modifying unintended files or folders.

Microsoft says successful exploitation allows attackers with low privileges to escalate permissions and manipulate or perform file management operations in the context of the NT AUTHORITY\\SYSTEM account.

While removing the folder did not cause issues using Windows in our tests, Microsoft [told BleepingComputer](https://www.bleepingcomputer.com/news/security/microsoft-windows-inetpub-folder-created-by-security-fix-dont-delete/) it was intentionally created and should not be deleted. Redmond issued the same warning in an updated advisory for the CVE-2025-21204 security flaw to warn users not to delete the empty %systemdrive%\\inetpub folder.

"This folder should not be deleted regardless of whether Internet Information Services (IIS) is active on the target device. This behavior is part of changes that increase protection and does not require any action from IT admins and end users," the company cautioned.

Cybersecurity expert Kevin Beaumont also demonstrated that non-admin users can abuse this folder [to block Windows updates](https://www.bleepingcomputer.com/news/microsoft/windows-inetpub-security-fix-can-be-abused-to-block-future-updates/) from being installed by creating a junction between C:\\inetpub and any Windows file.