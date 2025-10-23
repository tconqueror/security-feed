# Microsoft disables File Explorer preview for downloads to block attacks

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/04/24/Microsoft.jpg)

Microsoft says that the File Explorer (formerly Windows Explorer) now automatically blocks previews for files downloaded from the Internet to block credential theft attacks via malicious documents.

The change is already live for users who have installed this month's Patch Tuesday security updates on Windows 11 and Windows Server systems.

As Redmond [explains in a support document](https://support.microsoft.com/en-us/topic/file-explorer-automatically-disables-the-preview-feature-for-files-downloaded-from-the-internet-56d55920-6187-4aae-a4f6-102454ef61fb) published this Wednesday, the preview functionality will be disabled by default only for files viewed on an Internet Zone file share and those marked with the Mark of the Web (MotW), which shows that they've been downloaded using a web browser, received as email attachments, and obtained from other internet sources.

When attempting to preview such files, the File Explorer preview pane will display a warning message saying "The file you are attempting to preview could harm your computer. If you trust the file and the source you received it from, open it to view its contents."

After installing Windows security updates released after October 2025, this change will block threat actors from exploiting vulnerabilities that allow them to obtain NTLM hashes when users preview files containing HTML tags (such as <link>, <src>, and so on) that reference external paths on attacker-controlled servers.

This attack vector is particularly concerning because it requires no user interaction beyond selecting a file to preview and removes the need to trick a target into actually opening or executing it on their system.

![File Explorer preview disabled for downloaded file](https://www.bleepstatic.com/images/news/u/1109292/2025/File_Explorer_blocking_preview.jpg)

_File Explorer preview disabled for file with MotW (BleepinComputer)_

"Starting with Windows security updates released on and after October 14, 2025, File Explorer automatically disables the preview feature for files downloaded from the internet," Microsoft [says in a support document](https://support.microsoft.com/en-us/topic/file-explorer-automatically-disables-the-preview-feature-for-files-downloaded-from-the-internet-56d55920-6187-4aae-a4f6-102454ef61fb) published this Wednesday.

"This change is designed to enhance security by preventing a vulnerability that could leak NTLM hashes when users preview potentially unsafe files."

For most users, no action is required since the protection is enabled automatically with the October 2025 security update, and existing workflows remain unaffected unless you regularly preview downloaded files.

If you need to preview a trusted file from a known source, you can manually remove the Internet security block. To do that, right-click the file in File Explorer, select Properties, and click the "Unblock" button at the bottom of the General tab.

However, it's important to note that this may not take effect immediately and could require signing out and signing back in.

The preview block can also be removed for all files on an Internet Zone file share by using the Internet Options control panel's Security tab to add the file share’s address to the Trusted sites or the Local intranet security zone.