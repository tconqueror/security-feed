# 'Stargazers' use fake Minecraft mods to steal player passwords

![Minecraft stargazers](https://www.bleepstatic.com/content/hl-images/2025/06/18/minecraft-stargazers.jpg)

A large-scale malware campaign specifically targets Minecraft players with malicious mods and cheats that infect Windows devices with infostealers that steal credentials, authentication tokens, and cryptocurrency wallets.

The campaign, [discovered by Check Point Research](https://research.checkpoint.com/2025/minecraft-mod-malware-stargazers/), is conducted by the Stargazers Ghost Network and leverages the Minecraft massive modding ecosystem and legitimate services like GitHub to reach a large audience of potential targets.

Check Point has seen thousands of views, or hits, on Pastebin links used by the threat actors to deliver payloads to targets' devices, indicating the broad reach of this campaign.

## Stealthy Minecraft malware

The Stargazers Ghost Network is a distribution-as-a-service (DaaS) operation active on GitHub since last year, first documented by Check Point in a campaign involving [3,000 accounts](https://www.bleepingcomputer.com/news/security/over-3-000-github-accounts-used-by-malware-distribution-service/) spreading infostealers.

The same operation, which is boosted by [fake GitHub stars](https://www.bleepingcomputer.com/news/security/over-31-million-fake-stars-on-github-projects-used-to-boost-rankings/), was observed [infecting over 17,000 systems](https://www.bleepingcomputer.com/news/security/new-godloader-malware-infects-thousands-of-gamers-using-godot-scripts/) in late 2024 with a novel Godot-based malware.

The latest campaign described by Check Point researchers Jaromír Hořejší and Antonis Terefos targets Minecraft with Java malware that evades detection by all anti-virus engines.

The researchers found multiple GitHub repositories run by Stargazers, disguised as Minecraft mods and cheats like Skyblock Extras, Polar Client, FunnyMap, Oringo, and Taunahi.

"We have identified approximately 500 GitHub repositories, including those that are forked or copied, which were part of this operation aimed at Minecraft players," Antonis Terefos told BleepingComputer.

"We've also seen 700 stars produced by approximately 70 accounts."

![Four repositories participating in this operation](https://www.bleepstatic.com/images/news/security/m/minecraft/stargazers-fake-mods-malware/fake-minecraft-mods.jpg)

**Four repositories participating in this operation**  
_Source: Check Point_

Once executed within Minecraft, the first-stage JAR loader downloads the next stage from Pastebin using a base64 encoded URL, fetching a Java-based stealer.

This stealer targets Minecraft account tokens and user data from the Minecraft launcher and popular third-party launchers like Feather, Lunar, and Essential.

It also attempts to steal Discord and Telegram account tokens, sending the stolen data via HTTP POST requests to the attacker's server.

The Java stealer also serves as a loader for the next stage, a .NET-based stealer called '44 CALIBER,' which is a more "traditional" info stealer, attempting to snatch information stored in web browsers, VPN account data, cryptocurrency wallets, Steam, Discord, and other apps.

![Infection chain](https://www.bleepstatic.com/images/news/u/1220909/2025/June/chain.jpg)

**Overview of the infection chain**  
_Source: Check Point_

44 CALIBER also collects system information and clipboard data and can grab screenshots of the victim's computer.

"After deobfuscation we can observe that it steals various credentials from browsers (Chromium, Edge, Firefox), files (Desktop, Documents, %USERPROFILE%/Source), Cryptocurrency wallets (Armory, AtomicWallet, BitcoinCore, Bytecoin, DashCore, Electrum, Ethereum, LitecoinCore, Monero, Exodus, Zcash, Jaxx), VPNs (ProtonVPN, OpenVPN, NordVPN), Steam, Discord, FileZilla, Telegram," warns the researchers.

The stolen data is exfiltrated via Discord webhooks, accompanied by Russian comments. This clue, combined with UTC+3 commit timestamps, suggests that the operators of this campaign are Russian.

Check Point has shared the full indicators of compromise (IoCs) at the bottom of its report to help detect and block the threat.

To stay safe against this and similar campaigns, Minecraft players should only download mods from reputable platforms and verified community portals and stick to trusted publishers.

If prompted to download from GitHub, check the number of stars, forks, and contributors, scrutinize commits for signs of fake activity, and check recent actions on the repository.

Ultimately, it is prudent to use a separate "burner" Minecraft account when testing mods and avoid logging into your main account.