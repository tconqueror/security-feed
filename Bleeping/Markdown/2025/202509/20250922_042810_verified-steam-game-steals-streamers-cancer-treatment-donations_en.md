# Verified Steam game steals streamer's cancer treatment donations

![Verified Steam game steals streamer's cancer treatment donations](https://www.bleepstatic.com/content/hl-images/2025/09/19/Steam.jpg)

A gamer seeking financial support for cancer treatment lost $32,000 after downloading from Steam a verified game named Block Blasters that drained his cryptocurrency wallet.

Block Blasters is a 2D platformer that was available on Steam for almost two months, between July 30 and September 21\. The game was safe until August 30, when a [cryptodrainer component was added](http://steamdb.info/depot/3872351/history/).

Published by developer Genesis Interactive and [no longer on Steam](http://web.archive.org/web/20250921181738/https://store.steampowered.com/app/3872350/BlockBlasters/), the retro-styled game was a free-to-play title promising fast-paced action on responsive controls, and had a few hundred ‘Very Positive’ reviews on the gaming platform.

The malicious component in the game was revealed during a live fundraising from video game streamer [RastalandTV](https://x.com/rastalandTV/status/1969629808788181258), who was trying to raise funds for life saving treatment against stage 4 high-grade sarcoma.

The gamer also started a [GoFundMe crowdsourcing campaign](https://www.gofundme.com/f/57p5a-help-me-beat-stage-4-cancer) to receive donations. At the time of writing, completion of the goal is at 58%.

As the Latvian gamer [explains](https://x.com/rastalandTV/status/1969629808788181258), he lost more than $32,000 after downloading a verified game on Steam.

![The malicious game on Steam](https://www.bleepstatic.com/images/news/u/1220909/2025/September/steam.jpg)

**The malicious game on Steam**  
_Source: Internet Archive_

Crypto investigator ZachXBT told BleepingComputer that the attackers appear to have stolen [a total of $150,000](https://x.com/zachxbt/status/1969793042531107300) from 261 Steam accounts.

VXUnderground security group, who has also been [following the attack](https://x.com/vxunderground/status/1969786282831130872), reports a higher victim count of 478, and [published a list](https://pastebin.com/g3JSYHQi) of usernames, urging their owners to immediately reset their passwords.

Reportedly, these people were explicitly targeted after being identified over Twitter for managing significant cryptocurrency amounts, and were presumably sent invitations to try out the game.

A [group](https://x.com/John5725424446/status/1969896301119819791) of researchers [published a brief report](https://s3.us-east-005.backblazeb2.com/vx-underground-main/Malware%20Analysis/2025/2025-09-21%20-%20Block%20Blasters%20-%20Forensic%20Report/Paper/2025-09-21%20-%20Block%20Blasters%20-%20Forensic%20Report.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=005e2c099359ccf0000000004%2F20250922%2Fus-east-1%2Fs3%2Faws4%5Frequest&X-Amz-Date=20250922T052246Z&X-Amz-Expires=3600&X-Amz-SignedHeaders=host&X-Amz-Signature=239334631df4839d8e26e7aeae88fb3c1c5b03dacf1039cae49b109b68f783f1) detailing the dropper batch script that performs environment checks before it collects Steam login information along with the victim’s IP address, and uploads the data to a command and control (C2) system.

GDATA researcher [Karsten Hahn](https://x.com/struppigel/status/1969974814459736397) also documented a Python backdoor, and a [StealC](https://www.bleepingcomputer.com/news/security/stealc-malware-enhanced-with-stealth-upgrades-and-data-theft-tools/) payload, used alongside the batch stealer.

![Data theft routine](https://www.bleepstatic.com/images/news/u/1220909/2025/September/data-theft.jpeg)

**Data theft routine**  
_Source: @struppigel | X_

Investigators also highlighted an operational security failure where the attackers left their Telegram bot code and tokens exposed.

There are unconfirmed reports that OSINT experts participating in the hunt [identified the threat actor](https://x.com/vxunderground/status/1969912677914103847) as an Argentinian immigrant living in Miami, Florida.

BleepingComputer has contacted Valve for a comment on Block Blasters and the alleged inaction following multiple reports, but we have not received a response by publication time.

The Block Blasters incident is not an isolated one on Steam. Similar cases earlier this year include the [Chemia](https://www.bleepingcomputer.com/news/security/hacker-sneaks-infostealer-malware-into-early-access-steam-game/) survival crafting game, [Sniper: Phantom’s Resolution](https://www.bleepingcomputer.com/news/security/steam-pulls-game-demo-infecting-windows-with-info-stealing-malware/), and [PirateFi](https://www.bleepingcomputer.com/news/security/piratefi-game-on-steam-caught-installing-password-stealing-malware/), all of which infected unsuspecting victims with information-stealing malware.

If you have installed Block Blasters on your computer, it is recommended to reset your Steam passwords immediately and move your digital assets to new wallets.

In general, it is advisable to be cautious with Steam games that have a small number of downloads and reviews, and also titles in ‘beta’ development stage, as those can hide malware payloads.