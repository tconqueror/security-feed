# Hackers now testing ClickFix attacks against Linux targets

![Linux](https://www.bleepstatic.com/content/hl-images/2024/05/31/Linux.jpg)

A new campaign employing ClickFix attacks has been spotted targeting both Windows and Linux systems using instructions that make infections on either operating system possible.

ClickFix is a [social engineering tactic](https://www.bleepingcomputer.com/news/security/iclicker-hack-targeted-students-with-malware-via-fake-captcha/) where fake verification systems or application errors are used to trick website visitors into running console commands that install malware.

These attacks have traditionally targeted Windows systems, prompting targets to execute PowerShell scripts from the Windows Run command, resulting in [info-stealer malware](https://www.bleepingcomputer.com/news/security/over-6-000-wordpress-sites-hacked-to-install-plugins-pushing-infostealers/) infections and [even ransomware](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/).

However, a 2024 campaign using bogus Google Meet errors also [targeted macOS users](https://www.bleepingcomputer.com/news/security/fake-google-meet-conference-errors-push-infostealing-malware/).

## ClickFix targeting Linux users

A more recent campaign spotted by [Hunt.io researchers](https://hunt.io/blog/apt36-clickfix-campaign-indian-ministry-of-defence) last week is among the first to adapt this social engineering technique for Linux systems.

The attack, which is attributed to the Pakistan-linked threat group APT36 (aka "Transparent Tribe"), utilizes a website that impersonates India's Ministry of Defence with a link to an allegedly official press release.

![Malicious website mimicking India's Ministry of Defence](https://www.bleepstatic.com/images/news/u/1220909/2025/May/website.jpg)

**Malicious website mimicking India's Ministry of Defence**  
_Source: Hunt.io_

When visitors click on this website link, they are profiled by the platform to determine their operating system, and then redirected to the correct attack flow.

On Windows, victims are served a full-screen page warning them of limited content usage rights. Clicking on 'Continue' triggers JavaScript that copies a malicious MSHTA command to the victim's clipboard, who is instructed to paste and execute it on the Windows terminal.

This launches a .NET-based loader which connects to the attacker's address, while the user sees a decoy PDF file to make everything appear legitimate and as expected.

On Linux, victims are redirected to a CAPTCHA page that copies a shell command to their clipboard when clicking the "I'm not a robot button."

The victim is then guided to press ALT+F2 to open a Linux run dialog, paste the command into it, and then press **Enter** to execute it.

![Instructions for Linux users](https://www.bleepstatic.com/images/news/u/1220909/2025/May/linux-instructions.jpg)

**Instructions for Linux users**  
_Source: Hunt.io_

The command drops the 'mapeal.sh' payload on the target's system, which, according to Hunt.io, does not perform any malicious actions in its current version, limited to fetching a JPEG image from the attacker's server.

**Linux ClickFix script**  
_Source: BleepingComputer_

"The script downloads a JPEG image from the same trade4wealth\[.\]in directory and opens it in the background," explains Hunt.io.

"No additional activity, such as persistence mechanisms, lateral movement, or outbound communication, was observed during execution."

However, it is possible that APT36 is currently experimenting to determine the effectiveness of the Linux infection chain, as they would just need to swap out the image for a shell script to install malware or perform other malicious activity.

The adaptation of ClickFix to carry out attacks on Linux is another testament to its effectiveness, as the attack type has now been used against all three major desktop OS platforms.

As a general policy, users should not copy and paste any commands into Run dialogs without knowing exactly what the command does. Doing so only increases the risk of a malware infection and theft of sensitive data.