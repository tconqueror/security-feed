# North Korean Lazarus hackers targeted European defense companies

![North Korean Lazarus hackers targeted European defense companies](https://www.bleepstatic.com/content/hl-images/2024/11/13/Lazarus.jpg)

North Korean Lazarus hackers compromised three European companies in the defense sector through a coordinated Operation DreamJob campaign leveraging fake recruitment lures.

The threat group's activity was detected in late March and targeted organizations involved in the development of unmanned aerial vehicle (UAV) technology.

‘Operation DreamJob’ is a long-running Lazarus campaign where the adversary, posing as a recruiter at a big company (either real or fake), approaches employees at an organization of interest with job offers for a high-profile role.

The targets are tricked into downloading malicious files that give hackers access to the systems of the target company.

The tactic has been used in the past against cryptocurrency and [DeFi firms](https://www.bleepingcomputer.com/news/security/dprk-hackers-go-after-crypto-assets-using-trojanized-defi-wallet-app/), [software developers](https://www.bleepingcomputer.com/news/security/lazarus-hackers-now-push-linux-malware-via-fake-job-offers/), [journalists](https://www.bleepingcomputer.com/news/security/hackers-trojanize-putty-ssh-client-to-backdoor-media-company/), [security researchers](https://www.bleepingcomputer.com/news/security/security-researchers-targeted-with-new-malware-via-job-offers-on-linkedin/), and also organizations in the [defense sector](https://www.bleepingcomputer.com/news/security/north-korean-hackers-linked-to-defense-sector-supply-chain-attack/), including the [aerospace industry](https://www.bleepingcomputer.com/news/security/lazarus-hackers-breach-aerospace-firm-with-new-lightlesscan-malware/).

Researchers at cybersecurity company ESET say that in the most recent Operation DreamJob they analyzed, Lazarus focused on UAV-related technology, which aligns with current geo-political developments and coincides with North Korea’s increased effort to build a drone arsenal "inspired" by Western designs.

### Targeting makers of drone components

ESET observed in late March that "in-the-wild \[DreamJob\] attacks successively targeted" a metal engineering firm in Southeastern Europe, an aircraft parts maker, and a defense company, both in Central Europe.

However, the cybersecurity company did not provide any details on the success the hackers had with targeting the three companies.

All three companies make military equipment that is currently deployed in Ukraine as part of their countries' military assistance.

Two of them, though, "are clearly involved in the development of UAV technology, with one manufacturing critical drone components and the other reportedly engaged in the design of UAV-related software."

Analyzing the infection chain, the researchers found that it started with the victim launching a trojanized open-source application or plugin, such as the MuPDF viewer, Notepad++, WinMerge plugins, TightVNC Viewer, libpcre, and DirectX wrappers.

Loading the trojanized DLL or malware dropper was achieved through DLL sideloading, an evasion technique that uses a legitimate but vulnerable software to load the malicious payload.

In the next stage, the payload is decrypted and loaded directly into memory using MemoryModule-style routines.

The final stage malware is the ScoringMathTea RAT (Remote Access Trojan), which establishes communication with the command-and-control (C2) infrastructure and awaits instructions.

In one alternative infection chain, a malware loader named BinMergeLoader (MISTPEN) is used instead of the RAT, which abuses the Microsoft Graph API and tokens to retrieve additional payloads.

![Two attack chains used in the campaign](https://www.bleepstatic.com/images/news/u/1220909/2025/October/infection-chain(1).jpg)

**Two attack chains used in the campaign**  
_Source: ESET_

The ScoringMathTea RAT, first documented in 2023, supports 40 commands in its latest version, which give the attackers a broad range of operational versatility, from command execution to dropping new malware.

“The implemented functionality is the usual required by Lazarus: manipulation of files and processes, exchanging the configuration, collecting the victim’s system info, opening a TCP connection, and executing local commands or new payloads downloaded from the C&C server,” [explains ESET](https://www.welivesecurity.com/en/eset-research/gotta-fly-lazarus-targets-uav-sector/).

ESET comments that despite the repeated exposure of Operation DreamJob tactics and social engineering lures via reports, it continues to remain an effective modus operandi for North Korean threat actors.

The cybersecurity company provides an extensive set of [indicators of compromise](https://github.com/eset/malware-ioc/tree/master/nukesped%5Flazarus#gotta-fly-lazarus-targets-the-uav-sector) (IoCs) for the domains and malicious tools Lazarus hackers used in the DreamJob campaign against European organizations in the defense sector.