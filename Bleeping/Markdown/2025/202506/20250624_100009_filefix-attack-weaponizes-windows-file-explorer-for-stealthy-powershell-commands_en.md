# FileFix attack weaponizes Windows File Explorer for stealthy commands

![FileFix attacks weaponizes Windows File Explorer for stealthy PowerShell commands](https://www.bleepstatic.com/content/hl-images/2021/12/28/hacker.jpg)

A cybersecurity researcher has developed FileFix, a variant of the ClickFix social engineering attack that tricks users into executing malicious commands via the File Explorer address bar in Windows.

FileFix, a variation of the social-engineering attack called ClickFix, allows threat actors to execute commands on the victim system through the File Explorer address bar in Windows.

Cybersecurity researcher [mr.d0x](https://twitter.com/mrd0x) discovered the new method and demonstrated that it could be used in attacks targeting company employees using simple social engineering techniques.

[ClickFix](https://www.bleepingcomputer.com/tag/clickfix/) attacks are browser-based and rely on tricking users into clicking on a button on a website that copies a command to Windows clipboard. Users are then instructed to paste the command into PowerShell or another command prompt to fix an issue.

These types of attacks commonly masquerade as captchas or errors that prevent the user from using a site without first "fixing" the issue.

![Fake CAPTCHA in a ClickFix attack](https://www.bleepstatic.com/images/news/security/attacks/i/iclicker/example-captcha-clickfix.jpg)

Example of a fake CAPTCHA in a ClickFix attack  
[Source: SilentPush](https://x.com/silentpush/status/1902557832014393767)

### The FileFix divergence

In a ClickFix attack, when users click a website button, a malicious PowerShell command is automatically copied into the Windows clipboard followed by instructions to paste it into the command prompt through the Run Dialog (Win+R).

mr.d0x found a way to achieve the same goal but by having the target paste the command in the more familiar user interface of Windows File Explorer.

Since File Explorer can execute operating system commands, the researcher combined the functionality with the browser’s file upload feature and came up with a highly plausible scenario.

FileFix attacks also rely on a phishing page, but the ruse is no longer presented as an error or issue. Instead, it may appear as a notification indicating that a file has been shared with the user and includes a request to paste the path into File Explorer to locate it.

“The phishing page includes an “Open File Explorer” button that, when clicked, launches File Explorer through the file upload functionality and copies the PowerShell command to the clipboard” - [mr.d0x](https://mrd0x.com/filefix-clickfix-alternative/)

However, to keep the deceit intact, an attacker can hide the malicious PowerShell command by concatenating a dummy file path within a PowerShell comment.

This causes only the fake path to be initially seen in the File Explorer address bar, hiding the malicious PowerShell command that precedes it.

A video demonstrating the new ClickFix variation shows that by placing the dummy file path as a comment after the PowerShell command, the malicious string is no longer visible to the user, and File Explorer executes it.

Since the attack requires a file upload button, the researcher carefully considered the FileFix method so that it avoids users accidentally selecting a file from the computer.

In the proof-of-concept code for the phishing page, mr.d0x added a few lines that block file upload action “by intercepting the file selection event and immediately clearing the input.”

If this happens, an attacker could display an alert informing users that they failed to follow the instructions and try again.

### ClickFix campaigns

ClickFix attacks have proven to be a method so efficient to deploy malware on user systems that it has been used in [ransomware attacks](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/) and even [state-sponsored groups used it](https://www.bleepingcomputer.com/news/security/state-sponsored-hackers-embrace-clickfix-social-engineering-tactic/).

North Korean [state hacker group ‘Kimsuky’](https://www.bleepingcomputer.com/news/security/dprk-hackers-dupe-targets-into-typing-powershell-commands-as-admin/) included ClickFix elements in one of their campaigns where they used a PDF file to direct targets to a fake device registration link showing instructions to run PowerShell as administrator and paste code provided by the attacker.

In a ClickFix campaign observed by Microsoft, cybercriminals [impersonated Booking.com](https://www.bleepingcomputer.com/news/security/clickfix-attack-delivers-infostealers-rats-in-fake-bookingcom-emails/) to deliver infostealers and remote access trojans to hospitality workers.

The attack method has also been [adapted to Linux](https://www.bleepingcomputer.com/news/security/hackers-now-testing-clickfix-attacks-against-linux-targets/), where a shell command is automatically copied to the clipboard after visiting a malicious website. The potential victim is then guided to open a Run dialog and execute the command.

FileFix, although a variation, shows that such phishing attacks can be improved by switching command execution to an environment that is friendlier and more familiar to users.

mr.d0x told BleepingComputer that he believes his FileFix attack will soon be adopted by threat actors due to its simplicity and use of a well-known Windows utility.

In the past, cybercriminals quickly started using the researcher's [browser-in-the-browser phishing technique](https://www.bleepingcomputer.com/news/security/browser-in-the-browser-attacks-target-cs2-players-steam-accounts/), showing that bad actors are constantly interested in learning about new attack methods.