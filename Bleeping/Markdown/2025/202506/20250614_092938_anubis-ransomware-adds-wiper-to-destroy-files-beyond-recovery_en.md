# Anubis ransomware adds wiper to destroy files beyond recovery

![Anubis ransomware](https://www.bleepstatic.com/content/hl-images/2025/06/13/Anubis.jpg)

The Anubis ransomware-as-a-service (RaaS) operation has added to its file-encrypting malware a wiper module that destroys targeted files, making recovery impossible even if the ransom is paid.

Anubis (not to be confused with the [same-name Android malware](https://www.bleepingcomputer.com/news/security/anubis-android-malware-returns-to-target-394-financial-apps/) with a [ransomware module](https://www.bleepingcomputer.com/news/security/anubis-android-trojan-spotted-with-almost-functional-ransomware-module/)) is a relatively new RaaS first observed in December 2024 but became more active at the beginning of the year.

On February 23, the operators announced an affiliate program on the RAMP forum.

A [report from KELA](https://www.kelacyber.com/blog/anubis-a-new-ransomware-threat/) at the time explained that Anubis offered ransomware affiliates an 80% share of their proceeds. Data extortion affiliates were offered a 60%, and initial access brokers a 50% cut.

Currently, Anubis’ extortion page on the dark web lists only eight victims, indicating that it could increase the attack volume once confidence in the technical aspect is strengthened.

On that front, a Trend Micro report published yesterday contains evidence that the operators of Anubis are actively working on adding new features, an unusual one being a file-wiping function.

The researchers found the wiper in the latest Anubis samples they dissected, and believe the feature was introduced to increase the pressure on the victim to pay quicker instead of stalling negotiations or ignoring them altogether.

“What further sets Anubis apart from other RaaS and lends an edge to its operations is its use of a file wiping feature, designed to sabotage recovery efforts even after encryption,” [explains Trend Micro](https://www.trendmicro.com/en%5Fus/research/25/f/anubis-a-closer-look-at-an-emerging-ransomware.html).

“This destructive tendency adds pressure on victims and raises the stakes of an already damaging attack.”

The destructive behavior is activated using the command-line parameter ‘/WIPEMODE,’ which requires key-based authentication to issue.

![Anubis' wipe mode](https://www.bleepstatic.com/images/news/u/1220909/2025/June/wipemode.jpg)

**Anubis' wipe mode**  
_Source: Trend Micro_

When activated, the wiper erases all file contents, reducing their sizes to 0 KB while keeping the filenames and structure intact.

The victim will still see all files in the expected directories, but their contents will be irreversibly destroyed, making recovery impossible.

![Files before encryption (top) and after (bottom)](https://www.bleepstatic.com/images/news/u/1220909/2025/June/before.jpg)

**Files before encryption (top) and after (bottom)**  
_Source: Trend Micro_

Trend Micro’s analysis reveals that Anubis supports several commands at launch, including for privilege elevation, directory exclusion, and target paths for encryption.

Important system and program directories are excluded by default to avoid rendering the system completely unusable.

The ransomware removes Volume Shadow Copies and terminates processes and services that could interfere with the encryption process.

The encryption system uses ECIES (Elliptic Curve Integrated Encryption Scheme), and the researchers noted implementation similarities to EvilByte and Prince ransomware.

The encrypted files are appended the ‘.anubis’ extension, an HTML ransom note is dropped on impacted directories, and the malware also performs an attempt (failed) to change the desktop wallpaper.

**The Anubis ransom note**  
_Source: Trend Micro_

Trend Micro observed that Anubis attacks begin with phishing emails that carry malicious links or attachments.

The complete list of the indicators of compromise (IoCs) associated with Anubis attacks is [available here](https://www.trendmicro.com/content/dam/trendmicro/global/en/research/25/f/anubis--a-closer-look-at-an-emerging-ransomware-with-built-in-wiper/Anubis%5FA%5FCloser%5FLook%5Fat%5Fa%5FEmerging%5FRansomware%5Fwith%5FBuilt-in%5FWiper%5FIOCs.txt).