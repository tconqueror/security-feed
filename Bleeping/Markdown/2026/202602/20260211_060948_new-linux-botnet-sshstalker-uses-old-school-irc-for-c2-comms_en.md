# New Linux botnet SSHStalker uses old-school IRC for C2 comms

![New Linux botnet SSHStalker uses old-school IRC for C2 comms](https://www.bleepstatic.com/content/hl-images/2024/05/14/Linux-botnet.jpg)

A newly documented Linux botnet named SSHStalker is using the IRC (Internet Relay Chat) communication protocol for command-and-control (C2) operations.

The protocol was invented in 1988, and its adoption peaked during the 1990s, becoming the main text-based instant messaging solution for group and private communication.

Technical communities still appreciate it for its implementation simplicity, interoperability, low bandwidth requirements, and no need for a GUI.

[![Wiz](https://www.bleepstatic.com/c/w/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=AI-Agents-101) 

The SSHStalker botnet relies on classic IRC mechanics such as multiple C-based bots and multi-server/channel redundancy instead of modern C2 frameworks, prioritizing resilience, scale, and low cost over stealth and technical novelty.

According to researchers at threat intelligence company Flare, this approach extends to other characteristics of SSHStalker’s operation, like using noisy SSH scans, one-minute cron jobs, and a large back-catalog of 15-year old CVEs.

“What we actually found was a loud, stitched-together botnet kit that mixes old-school IRC control, compiling binaries on hosts, mass SSH compromise, and cron-based persistence. In other words scale-first operation that favors reliability over stealth,” Flare says.

![The 'infected machines' IRC channel](https://www.bleepstatic.com/images/news/u/1220909/2026/February/infectedmachines.jpg)

**The 'infected machines' IRC channel**  
_Source: Flare_

SSHStalker achieves initial access through automated SSH scanning and brute forcing, using a Go binary that masquerades as the popular open-source network discovery utility _nmap_.

Compromised hosts are then used to scan for additional SSH targets, which resembles a worm-like propagation mechanism for the botnet.

Flare [found](https://flare.io/learn/resources/blog/old-school-irc-new-victims-inside-the-newly-discovered-sshstalker-linux-botnet) a file with results from nearly 7,000 bot scans, all from January, and focused mostly on cloud hosting providers in Oracle Cloud infrastructure.

Once SSHStalker infects a host, it downloads the GCC tool for compiling payloads on the victim device for better portability and evasion.

The first payloads are C-based IRC bots with hard-coded C2 servers and channels, which enroll the new victim in the botnet’s IRC infrastructure.

Next, the malware fetches archives named GS and _bootbou_, which contain bot variants for orchestration and execution sequencing.

Persistence is achieved via cron jobs that run every 60 seconds, invoking a watchdog-style update mechanism that checks whether the main bot process is running and relaunches it if it is terminated.

The botnet also contains exploits for 16 CVEs targeting Linux kernel versions from the 2009-2010 era. This is used to escalate privileges after the earlier brute-forcing step grants access to a low-privileged user.

**Attack chain overview**  
_Source: Flare_

Regarding monetization, Flare noticed that the botnet performs AWS key harvesting and website scanning. It also includes cryptomining kits such as the high-performance Ethereum miner PhoenixMiner.

Distributed denial-of-service (DDoS) capabilities are also present, though the researchers noted they have not yet observed any such attacks. In fact, SSHStalker’s bots currently just connect to the C2 and then enter an idle state, suggesting testing or access hoarding for now.

Flare has not attributed SSHStalker to a particular threat group, though it noted similarities with the [Outlaw/Maxlas](https://www.bleepingcomputer.com/news/security/rubycarp-hackers-linked-to-10-year-old-cryptomining-botnet/) botnet ecosystem and various Romanian indicators.

The threat intelligence company suggests placing monitoring solutions for compiler installation and execution on production servers, and alerts for IRC-style outbound connections. Cron jobs with short execution cycles from unusual paths are also big red flags.

Mitigation recommendations include disabling SSH password authentication, removing compilers from production images, enforcing egress filtering, and restricting execution from ‘/dev/shm.’