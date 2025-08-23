# Interlock ransomware gang pushes fake IT tools in ClickFix attacks

![Hacker](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

The Interlock ransomware gang now uses ClickFix attacks that impersonate IT tools to breach corporate networks and deploy file-encrypting malware on devices.

ClickFix is a social engineering tactic where victims are tricked into executing dangerous PowerShell commands on their systems to supposedly fix an error or verify themselves, resulting in the installation of malware.

Though this [isn't the first time](https://www.bleepingcomputer.com/news/security/fake-google-chrome-errors-trick-you-into-running-malicious-powershell-scripts/) ClickFix has been linked to ransomware infections, confirmation about Interlock shows an increasing trend in these types of threat actors utilizing the tactic.

Interlock is a ransomware operation launched in late September 2024, [targeting FreeBSD servers](https://www.bleepingcomputer.com/news/security/meet-interlock-the-new-ransomware-targeting-freebsd-servers/) and Windows systems.

Interlock is not believed to operate as a ransomware-as-a-service model. Still, it maintains a data leak portal on the dark web to increase pressure on victims, demanding payments ranging from hundreds of thousands of dollars to millions.

## From ClickFix to ransomware

In the past, Interlock utilized fake browser and VPN client updates to install malware and breach networks.

According to [Sekoia researchers](https://blog.sekoia.io/interlock-ransomware-evolving-under-the-radar/), the Interlock ransomware gang began utilizing ClickFix attacks in January 2025.

Interlock used at least four URLs to host fake CAPTCHA prompts that tell visitors to execute a command on their computer to verify themselves and download a promoted tool.

The researchers say they detected the malicious captcha on four different sites, mimicking Microsoft or Advanced IP Scanner portals:

* microsoft-msteams\[.\]com/additional-check.html
* microstteams\[.\]com/additional-check.html
* ecologilives\[.\]com/additional-check.html
* advanceipscaner\[.\]com/additional-check.html

However, only the site impersonating Advanced IP Scanner, a popular IP scanning tool commonly used by IT staff, led to downloading a malicious installer.

![Page hosting Interlock's ClickFix bait](https://www.bleepstatic.com/images/news/u/1220909/2025/April/clickfix-page.jpg)

**Page hosting Interlock's ClickFix bait**  
_Source: Sekoia_

Clicking the 'Fix it' button copies the malicious PowerShell command to the victim's clipboard. If executed in a command prompt or Windows Run dialog, it will download a 36MB PyInstaller payload.

At the same time, the legitimate AdvanceIPScanner website opens in a browser window to reduce suspicion.

The malicious payload installs a legitimate copy of the software it pretends to be and simultaneously executes an embedded PowerShell script that runs in a hidden window.

This script registers a Run key in Windows Registry for persistence and then collects and exfiltrates system info including OS version, user privilege level, running processes, and available drives.

Sekoia has observed the command and control (C2) responding with various payloads, including LummaStealer, BerserkStealer, keyloggers, and the Interlock RAT.

The latter is a simple trojan that can be dynamically configured, supporting file exfiltration, shell command execution, and running malicious DLLs.

![Commands Interlock RAT supports](https://www.bleepstatic.com/images/news/u/1220909/2025/April/rat-commands.jpg)

**Commands Interlock RAT supports**  
_Source: Sekoia_

After the initial compromise and RAT deployment, Interlock operators used stolen credentials to move laterally via RDP, while Sekoia also saw PuTTY, AnyDesk, and LogMeIn used in some attacks.

The last step before the ransomware execution is data exfiltration, with the stolen files uploaded to attacker-controlled Azure Blobs.

The Windows variant of Interlock is set (via a scheduled task) to run daily at 08:00 PM, but thanks to file extension-based filtering, this doesn't cause multiple layers of encryption but serves as a redundancy measure.

Sekoia also reports that the ransom note has evolved, too, with the latest versions focusing more on the legal aspect of the data breach and the regulatory consequences if stolen data is made public.

**Interlock's latest ransom note**  
_Source: BleepingComputer_

ClickFix attacks have now been adopted by a wide range of threat actors, including other ransomware gangs and North Korean hackers.

Last month, Sekoia discovered that the infamous Lazarus North Korean hacking group was using [ClickFix attacks targeting job seekers](https://www.bleepingcomputer.com/news/security/north-korean-hackers-adopt-clickfix-attacks-to-target-crypto-firms/) in the cryptocurrency industry.