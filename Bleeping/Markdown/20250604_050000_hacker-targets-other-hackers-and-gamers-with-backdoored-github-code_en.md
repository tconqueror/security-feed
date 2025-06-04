# Hacker targets other hackers and gamers with backdoored GitHub code

![Hacker smiley face](https://www.bleepstatic.com/content/hl-images/2022/09/15/cyber-smiley-lower.jpg)

A hacker targets other hackers, gamers, and researchers with exploits, bots, and game cheats in source code hosted on GitHub that contain hidden backdoors to give the threat actor remote access to infected devices.

This campaign was discovered by Sophos researchers, whom a client contacted to estimate the danger of a remote access trojan called Sakura RAT, which is freely available on GitHub.

The researchers found that the Sakura RAT code was essentially nonfunctional but had a _PreBuildEvent_ in the Visual Studio project that downloads and installs malware on the devices of those who attempt to compile it.

The publisher, "ischhfd83," was discovered to be directly or indirectly linked to another 141 GitHub repositories, 133 of which dropped hidden backdoors, marking this as a concerted campaign to distribute malware.

![One of the malicious repositories promoting a fake exploit builder](https://www.bleepstatic.com/images/news/u/1220909/2025/June/repo.jpg)

**One of the malicious repositories promoting a fake exploit builder**  
_Source: Sophos_

The backdoors selection includes Python scripts with obfuscated payloads, malicious screensaver (.scr) files using Unicode tricks, JavaScript files with encoded payloads, and Visual Studio PreBuild events.

A few repositories appear to have been abandoned since late 2023, but many are active with regular commits, some submitted mere minutes before Sophos' analysis.

These commits are fully automated, so their sole purpose is to create a false image of activity that gives the malicious projects an illusion of legitimacy.

![Commits history](https://www.bleepstatic.com/images/news/security/g/github/backdoored-cheats-code/anydesk-github.jpg)

**Commits history**  
_Source: Sophos_

"Because of the automated workflow runs, many projects had large numbers of commits (one had almost 60,000, despite having only been created in March 2025)," explains Sophos.

"Across all repositories, the average number of commits was 4,446 at the time of our initial collection."

The number of contributors is fixed to three specific users for each repository, and different publisher accounts are used for each, never surpassing nine repositories assigned to a single account.

These repositories receive traffic from YouTube videos, Discord, and posts on cybercrime forums. Sakura RAT itself received some media attention that sparked interest among curious "script kiddies" who went out looking for it on GitHub.

However, when victims download the files, running or building the code triggers a multi-step infection stage.

**The initial backdoor triggering the infection process**  
_Source: Sophos_

This process involves VBS scripts getting executed on the disk, PowerShell downloading an encoded payload from hardcoded URLs, fetching a 7zip archive from GitHub, and running an Electron app (SearchFilter.exe).

The app loads a bundled archive containing heavily obfuscated 'main.js' and related files, including code for system profiling, command execution, Windows Defender deactivation, and payload retrieval.

**Excerpt from main.js**  
_Source: Sophos_

The additional payloads downloaded by the backdoor include info-stealers and remote access trojans such as Lumma Stealer, AsyncRAT, and Remcos, all featuring extensive data theft capabilities.

Although many trojanized repositories are created to target other hackers, a wide variety of lures, such as game cheats, mod tools, and fake exploits, are used to target gamers, students, and even cybersecurity researchers.

As anyone can upload source code to GitHub, examining source code and verifying any projects' pre and post-build events is vital before attempting to compile software downloaded from open-source repositories.