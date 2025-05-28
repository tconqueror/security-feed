# Dark Partners cybercrime gang fuels large-scale crypto heists

![Dark Partners cybercrime gang fuels large-scale crypto heists](https://www.bleepstatic.com/content/hl-images/2023/12/01/Hackers_crypto.jpg)

A sprawling network of fake AI, VPN, and crypto software download sites is being used by the "Dark Partner" threat actors to conduct a crypto theft attacks worldwide.

Masquerading as popular apps, these cloned sites deliver the Poseiden (macOS) and Lumma (Windows) infostealers and malware loaders like Payday. This malware is used to steal cryptocurrency and sensitive data such as host information, credentials, private keys, or cookies, which are likely sold on the cybercriminal market.

On Windows, the threat actor used certificates from multiple companies to digitally sign malware builds, one of them was the PayDay Loader.

One infostealer delivered to these machines was Lumma Stealer, a malware operation that [law enforcement disrupted](https://www.bleepingcomputer.com/news/security/lumma-infostealer-malware-operation-disrupted-2-300-domains-seized/) earlier this month by seizing thousands of domains and part of its infrastructure.

On macOS, the threat actor delivered the Poseidon Stealer, which uses a custom DMG launcher, and targets Firefox and Chromium-based web browsers.

### Targeting wallet folders

The threat actors behind this campaign were dubbed "Dark Partners" by cybersecurity researcher [g0njxa](https://x.com/g0njxa), who describes the infection steps and analyzes the malware used.

Dark Partners delivers the infostealers through simple websites that impersonate at least 37 apps and tools, some of them using generative AI technology to create illustrations, videos, and artistic images (e.g. Sora, DeepSeek, Haiper, Runway, Leonardo, Creatify).

The list also includes seven crypto apps and platforms like TradingView, MetaTrader 5, Ledger, Exodus, Koinly, AAVE, and Unusual Whales.

These fake sites also include VPN services like Windscribe, payment processing platform Stripe, 3D modeling app Blender, creator-focused platform TikTok Studio, remote desktop solution UltraViewer, and Mac Clean - a system cleaning tool for macOS.

According to g0njxa, the landing pages provide nothing more than a download button and they all share a custom "Waiting for the file to download" frame, making it easy to discover them.

![Fake Haiper download page](https://www.bleepstatic.com/images/news/u/1100723/fake_haiper.webp)

**Fake download page for AI-powered video generator**  
_source: [g0njxa](https://g0njxa.medium.com/dark-partners-the-crypto-heist-adventure-of-poseidon-stealer-and-payday-loader-c91382fac5c8)_

Before providing the malware, the website checks for bot downloads and sends user information to an endpoint via a POST request.

In the end, the download action is triggered based on the operating system requesting it.

The researcher says that the host for the PayDay Loader panel (inspired by the [eponymous game](https://www.paydaythegame.com/payday3/)) also had a Poseidon Stealer panel in August 2024.

![PayDay loader panel](https://www.bleepstatic.com/images/news/u/1100723/PayDayLoader_panel.webp)

**PayDay loader panel**  
_source: [g0njxa](https://g0njxa.medium.com/dark-partners-the-crypto-heist-adventure-of-poseidon-stealer-and-payday-loader-c91382fac5c8)_

Notably, the infamous Poseidon Stealer was put on sale in July 2024 and sold to an unknown source. The malware hasn't seen major payload changes since its sale.

The AppleScript code for Poseidon shows that it can collect browser data, which including specific extension data from Chromium-based browsers like Chrome, Brave, Edge, Vivaldi, Opera, and Firefox, and wallets like MetaMask.

It also specifically targets wallet folders for desktop applications like Electrum, Coinomi, Exodus, Atomic, Wasabi, Ledger Live, and others.

The PayDay Loader is the Windows-specific malicious application, built as an electron-based application to deliver infostealers.

It has an anti-sandbox module that checks for common process names related to security analysis tools and terminates itself if any are detected.

g0njxa analyzed the malware and discovered that it used an obfuscated function to retrieve the command and control (C2) server address from a Google Calendar link.

Establishing persistence is a rather complex process that involves running a PowerShell script at every logon, its role being to access a virtual hard disk (VHD) hidden inside an NTFS alternate data stream (setting.json:disk.vhd), mounting it, and executing a file from the newly mounted volume.

“After a short delay to ensure execution, the script unmounts the VHD, removing traces of the payload” - [g0njxa](https://g0njxa.medium.com/dark-partners-the-crypto-heist-adventure-of-poseidon-stealer-and-payday-loader-c91382fac5c8)

PayDay Loader includes a NodeJS stealer module that can exfiltrate cryptocurrency wallet data to a C2, the researcher says. In total, it can steal data from 76 wallets and desktop applications.

Another highlight in g0njxa’s report is the use of code signing certificates for Windows malware builds. The researcher says that the Dark Partners threat actor likely purchased the certificates.

At the moment, none of the discovered certificates are valid, putting a temporary stop to the malicious campaign.

The researcher included in their report an extensive list of indicators of compromise for the analyzed samples (PayDay Loader and Poseidon Stealer) and nearly 250 domains for the landing pages.

g0njxa is well-known among cybercriminal gangs as the researcher is tracking threat actors that drain cryptocurrency wallets. One gang in particular is [Crazy Evil](https://www.bleepingcomputer.com/news/security/grasscall-malware-campaign-drains-crypto-wallets-via-fake-job-interviews/), who is responsible for multiple campaigns that involve complex social engineering over social media platforms to attract victims.