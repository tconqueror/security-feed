# Fake Mac fixes trick users into installing new Shamos infostealer

![Apple](https://www.bleepstatic.com/content/hl-images/2023/09/11/apple_triangle.jpg)

A new infostealer malware targeting Mac devices, called 'Shamos,' is targeting Mac devices in ClickFix attacks that impersonate troubleshooting guides and fixes.

The new malware, which is a variant of the Atomic macOS Stealer (AMOS), was developed by the cybercriminal group "COOKIE SPIDER," and is used to steal data and credentials stored in web browsers, Keychain items, Apple Notes, and cryptocurrency wallets.

CrowdStrike, which detected Shamos, [reports](https://www.crowdstrike.com/en-us/blog/falcon-prevents-cookie-spider-shamos-delivery-macos/) that the malware has attempted infections against over three hundred environments worldwide that they monitor since June 2025.

## Promoted through ClickFix attacks

Victims are lured via malvertising or fake GitHub repositories that utilize ClickFix attacks that prompt users into executing shell commands in the macOS Terminal.

The threat actors prompt users to run these commands to install software or fix fake errors, but when executed, they actually download and execute the malware on the device.

![Malicious GitHub repository](https://www.bleepstatic.com/images/news/u/1220909/2025/August/github.jpeg)

**Malicious GitHub repository**  
_Source: CrowdStrike_

The ads or spoofed pages (mac-safer\[.\]com, rescue-mac\[.\]com) claim to provide help with macOS problems people are likely to search for, containing instructions directing them to copy and paste the command to fix the issue.

![Malicious sponsored results on Google Search](https://www.bleepstatic.com/images/news/u/1220909/2025/August/sponsored.jpg)

**Malicious sponsored results on Google Search**  
_Source: CrowdStrike_

Instead of fixing anything, the command decodes a Base64-encoded URL and fetches a malicious Bash script from a remote server.

**False instructions for fixing printer issues on macOS**  
_Source: CrowdStrike_

The script captures the user's password, downloads the Shamos mach-O executable, and prepares and executes the malware using 'xattr' (removes quarantine flag) and 'chmod' (makes binary executable) to bypass Gatekeeper.

## Shamos data theft

Once executed on the device, Shamos executes anti-VM commands to verify it's not running on a sandbox, followed by AppleScript commands for host reconnaissance and data collection.

Shamos searches for sensitive data on the device, including cryptocurrency wallet files, keychain data, Apple Notes data, and information stored on the victim's browser.

After collecting everything, it packages them into an archive named 'out.zip' and transmits them to the attacker using curl.

In the cases where the malware runs with sudo privileges, it also creates a Plist file (com.finder.helper.plist) and stores it in the user's LaunchDaemons directory, ensuring persistence via automatic execution on system startup.

CrowdStrike also notes that Shamos can download additional payloads into the victim's home directory, and has observed cases where threat actors dropped a spoofed Ledger Live wallet app and a botnet module.

MacOS users are advised never to execute commands on their system that they found online if they don't fully understand what they do.

The same applies to GitHub repositories, as the platform is unfortunately a host to numerous malicious projects aimed at infecting unsuspecting users.

When facing issues with macOS, it is better that you avoid sponsored search results and instead seek help in the Apple Community forums, which are moderated by Apple, or the system's built-in Help (Cmd + Space → "Help").

ClickFix attacks have become a widespread tactic in distributing malware, with threat actors using them in [TikTok videos](https://www.bleepingcomputer.com/news/security/tiktok-videos-now-push-infostealer-malware-in-clickfix-attacks/), [disguising them as captchas](https://www.bleepingcomputer.com/news/security/iclicker-hack-targeted-students-with-malware-via-fake-captcha/), or as fixes for fake [Google Meet errors](https://www.bleepingcomputer.com/news/security/fake-google-meet-conference-errors-push-infostealing-malware/). 

This tactic has proven to be so effective in deploying malware that it has been used in [ransomware attacks](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/) and even by [state-sponsored threat actors](https://www.bleepingcomputer.com/news/security/state-sponsored-hackers-embrace-clickfix-social-engineering-tactic/).