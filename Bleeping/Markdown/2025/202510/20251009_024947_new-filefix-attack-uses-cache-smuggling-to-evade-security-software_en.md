# New FileFix attack uses cache smuggling to evade security software

![Hacker holding his arms up](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

A new variant of the FileFix social engineering attack uses cache smuggling to secretly download a malicious ZIP archive onto a victim’s system and bypassing security software.

The new phishing and social engineering attack impersonates a "Fortinet VPN Compliance Checker" and was first spotted by cybersecurity researcher [P4nd3m1cb0y](https://x.com/P4nd3m1cb0y/status/1970796711816605782), who shared information about it on X.

In a new report by cybersecurity firm [Expel](https://expel.com/blog/cache-smuggling-when-a-picture-isnt-a-thousand-words/), cybersecurity researcher Marcus Hutchins shares more details on how this attack works.

For those not familiar with [FileFix attacks](https://www.bleepingcomputer.com/news/security/filefix-attack-weaponizes-windows-file-explorer-for-stealthy-powershell-commands/), they are a variant of the [ClickFix social engineering attack](https://www.bleepingcomputer.com/news/security/fake-google-chrome-errors-trick-you-into-running-malicious-powershell-scripts/) developed by Mr.d0x. Instead of tricking users into pasting malicious commands into operating system dialogs, it uses the Windows File Explorer address bar to execute PowerShell scripts stealthily.

## FileFix attack evolves with cache smuggling

In the new phishing attack, a website displays a dialog that poses as a Fortinet VPN "Compliance Checker, directing users to paste what looks like a legitimate network path to a Fortinet program on a network share.

![Fortinet VPN Compliance Check FileFix lure](https://www.bleepstatic.com/images/news/security/f/filefix/fortinet-filefix/fortinet-filefix-lure.png)

**Fortinet VPN Compliance Check FileFix lure**  
_Source: Expel_

While the lure displays the path " \\\\Public\\Support\\VPN\\ForticlientCompliance.exe," when copied to the clipboard, it is actually much longer, as it is padded with 139 spaces to hide a malicious PowerShell command.

Due to this padding, when the visitor follows the instructions to open File Explorer and paste the command into the address bar, only the path is displayed, as seen below.

![How a copied command appears in File Explorer address bar](https://www.bleepstatic.com/images/news/security/f/filefix/fortinet-filefix/filefix-fileexplorer.jpg)

**How a copied command appears in File Explorer address bar**  
_Source: Expel_

However, when a person presses Enter on the keyboard, Windows runs the following hidden PowerShell command through conhost.exe in headless mode, so it's not visible to the user.

**Malicious PowerShell command**  
_Source: Expel_

The PowerShell command first creates the %LOCALAPPDATA%\\FortiClient\\compliance folder, then copies Chrome's cache files from %LOCALAPPDATA%\\Google\\Chrome\\User Data\\Default\\Cache\\Cache\_Data\\ into that folder.

The script then scans each cache file using regular expressions to find content between the "bTgQcBpv" and "mX6o0lBw". This content is actually a zip file stored in the fake image file, which is extracted to ComplianceChecker.zip and unzipped.

The script then launches the FortiClientComplianceChecker.exe executable from the extracted archive to execute malicious code.

You may be wondering how the malicious file was stored in Chrome's cache files in the first place, and this is where the cache smuggling attack comes into play.

When the visitor accessed the phishing page containing the FileFix lure, the website executed JavaScript that instructed the browser to retrieve an image file.

As the HTTP response states that the fetched image is of type "image/jpeg", the browser automatically caches it on the file system, treating it as a legitimate image file, even though it is not.

As this was done before the PowerShell command was executed through File Explorer, the file already existed in the cache, and the zip file could be extracted from it.

"This technique, known as [cache smuggling](https://sensepost.com/blog/2023/browsers-cache-smuggling/), enables the malware to bypass many different types of security products," explains Hutchins.

"Neither the webpage nor the PowerShell script explicitly download any files. By simply letting the browser cache the fake "image," the malware is able to get an entire zip file onto the local system without the PowerShell command needing to make any web requests."

"As a result, any tools scanning downloaded files or looking for PowerShell scripts performing web requests wouldn't detect this behavior."

Threat actors have become quick to adopt the new FileFix technique soon after it was disclosed, with [ransomware gangs](https://www.bleepingcomputer.com/news/security/interlock-ransomware-adopts-filefix-method-to-deliver-malware/) and [other threat actors](https://www.bleepingcomputer.com/news/security/new-filefix-attack-uses-steganography-to-drop-stealc-malware/) utilizing it in [their campaigns](https://www.bleepingcomputer.com/news/security/new-filefix-attack-runs-jscript-while-bypassing-windows-motw-alerts/).

## ClickFix generator expands the ecosystem

In addition to the new cache-smuggling FileFix variant, researchers at [Palo Alto Unit 42](https://unit42.paloaltonetworks.com/clickfix-generator-first-of-its-kind/) discovered a new ClickFix kit called the "IUAM ClickFix Generator," which automates the creation of ClickFix-style lures.

The ClickFix Generator's interface allows attackers to design spoofed verification pages, customize page titles and text, select color schemes, and configure clipboard payloads.

**IUAM ClickFix Generator interface**  
_Source: Unit 42_

The kit also supports OS detection, tailoring PowerShell commands for Windows or Base64-encoded shell commands for macOS, while sometimes serving harmless decoys to other operating systems.

The lures all appear to involve some type of fake Cloudflare captcha, with the researchers seeing multiple websites created that utilize the generated lures.

These websites claim to be affiliated with Cloudflare, Speedtest, Microsoft Teams, Claude, TradingView, Microsoft, and Microsoft 365, among others.

**Microsoft ClickFix lure**  
_Source: BleepingComputer_

While each lure is customized according to the attacker's campaign, the behavior remains the same, displaying a fake Cloudflare CAPTCHA that prompts users to run a hidden command in the Command Prompt, Run dialog, or Terminal.

In the campaign observed by Unit 42, the social engineering attacks were used to infect devices with the DeerStealer (Windows) and Odyssey (Mac) infostealer malware, as well as another unknown payload for Windows.

As these types of social engineering attacks have become increasingly popular among threat actors, it is essential to educate employees on the importance of never copying text from a website and running it in an operating system dialog box.