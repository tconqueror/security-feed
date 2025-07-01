# New FileFix attack runs JScript while bypassing Windows MoTW alerts

![New FileFix attack runs JScript while bypassing Windows MoTW alerts](https://www.bleepstatic.com/content/hl-images/2024/12/15/hacker-card.jpg)

A new FileFix attack allows executing malicious scripts while bypassing the Mark of the Web (MoTW) protection in Windows by exploiting how browsers handle saved HTML webpages.

The technique was devised by security researcher mr.d0x. Last week, the researcher showed how the [first FileFix method](https://www.bleepingcomputer.com/news/security/filefix-attack-weaponizes-windows-file-explorer-for-stealthy-powershell-commands/) worked as an alternative to 'ClickFix' attacks by tricking users into pasting a disguised PowerShell command into the File Explorer address bar.

The attack involves a phishing page to trick the victim into copying a malicious PowerShell command. Once they paste it into File Explorer, Windows executes the PowerShell, making it a very subtle attack.

With the [new FileFix attack](http://mrd0x.com/filefix-part-2/), an attacker would use social engineering to trick the user into saving an HTML page (using Ctrl+S) and renaming it to .HTA, which auto-executes embedded JScript via mshta.exe.

HTML Applications (.HTA) are considered legacy technology. This Windows file type can be used to execute HTML and scripting content using the legitimate mshta.exe in the context of the current user.

The researcher found that when HTML files are saved as "Webpage, Complete" (with MIME type text/html), they do not receive the MoTW tag, allowing script execution without warnings for the user.

When the victim opens the .HTA file, the embedded malicious script runs immediately without any warning.

The highest-friction part of the attack is the social engineering step, where victims need to be tricked into saving a webpage and renaming it.

One way around this is by designing a more effective bait, such as a malicious website prompting users to save multi-factor authentication (MFA) codes to maintain future access to a service.

The page would instruct the user to press Ctrl+S (Save As), choose "Webpage, Complete," and save the file as 'MfaBackupCodes2025.hta.'

![Example of the malicious page](https://www.bleepstatic.com/images/news/u/1220909/2025/June/page.png)

**Example of the malicious page**  
_Source: mr.d0x_

Although this requires more interaction, if the malicious webpage looks genuine and the user doesn't have a deep understanding of file extensions and security warnings, they could still fall for it.

An effective defense strategy against this variant of the FileFix attack is to disable or remove the 'mshta.exe' binary from your environment (found in C:\\Windows\\System32 and C:\\Windows\\SysWOW64).

Additionally, consider enabling file extension visibility on Windows and blocking HTML attachments on email.