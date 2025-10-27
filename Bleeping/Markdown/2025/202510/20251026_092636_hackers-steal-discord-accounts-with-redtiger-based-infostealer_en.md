# Hackers steal Discord accounts with RedTiger-based infostealer

![Discord](https://www.bleepstatic.com/content/hl-images/2023/11/03/Discord.jpg)

Attackers are using the open-source red-team tool RedTiger to build an infostealer that collects Discord account data and payment information.

The malware can also steal credentials stored in the browser, cryptocurrency wallet data, and game accounts.

RedTiger is a Python-based penetration testing suite for Windows and Linux that bundles options for scanning networks and cracking passwords, OSINT-related utilities, Discord-focused tools, and a malware builder.

![Discord-related tools in RedTiger](https://www.bleepstatic.com/images/news/u/1100723/RedTigerDiscord.png)

**Discord-related tools in RedTiger**  
_Source: GitHub_

RedTiger's info-stealer component offers the standard capabilities of snatching system info, browser cookies and passwords, crypto wallet files, game files, and Roblox and Discord data. It can also capture webcam snapshots and screenshots of the victim's screen.

Although the project marks its dangerous functions as "legal use only" [on GitHub](https://github.com/loxy0dev/RedTiger-Tools), its free and unconditional distribution and the lack of any safeguards allow easy abuse.

![RedTiger's malware builder](https://www.bleepstatic.com/images/news/u/1220909/2025/October/Builder.jpg)

**RedTiger's malware builder**  
_Source: GitHub_

According to [a report from Netskope](https://www.netskope.com/blog/redtiger-new-red-teaming-tool-in-the-wild-targeting-gamers-and-discord-accounts), threat actors are now abusing RedTiger's info-stealer component, primarily for targeting French Discord account holders.

The attackers compiled RedTiger's code using PyInstaller to form standalone binaries and gave those gaming or Discord-related names.

Once the info-stealer is installed on the victim's machine, it scans for Discord and browser database files. It then extracts plain and encrypted tokens via regex, validates the tokens, and pulls the profile, email, multi-factor authentication, and subscription information.

Next, it injects custom JavaScript into Discord's index.js to intercept API calls and capture events such as login attempts, purchases, or even password changes. It also extracts payment information (PayPal, credit cards) stored on Discord.

**Discord data targeted by the malware**  
_Source: Netskope_

From the victim's web browsers, RedTiger harvests saved passwords, cookies, history, credit cards, and browser extensions. The malware also captures desktop screenshots and scans for .TXT, .SQL, and .ZIP files on the filesystem.

After collecting the data, the malware archives the files and uploads them to GoFile, a cloud storage service that allows anonymous uploads. The download link is then sent to the attacker via a Discord webhook, along with the victim metadata.

Regarding evasion, RedTiger is well-equipped, featuring anti-sandbox mechanisms and terminating when debuggers are detected. The malware also spawns 400 processes and creates 100 random files to overload forensic analysis.

**Spamming deceptive files and processes on the host**  
_Source: Netskope_

While Netskope has not shared explicit distribution vectors for the weaponized RedTiger binaries, some common methods include Discord channels, malicious software download sites, forum posts, malvertising, and YouTube videos.

Users should avoid downloading executables or game tools like mods, "trainers," or "boosters" from unverified sources.

If you suspect compromise, revoke Discord tokens, change passwords, and reinstall your Discord desktop client from the official site. Also, clear saved data from browsers and enable MFA everywhere.