# BreachForums hacking forum database leaked, exposing 324,000 accounts

![Hacker holding hands up](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

The latest incarnation of the notorious BreachForums hacking forum has suffered a data breach, with its user database table leaked online.

BreachForums is the name of a series of hacking forums used to trade, sell, and leak stolen data, as well as sell access to corporate networks and other illegal cybercrime services.

The site was launched after the first of these forums, RaidForums, [was seized by law enforcement](https://www.bleepingcomputer.com/news/security/raidforums-hacking-forum-seized-by-police-owner-arrested/), with the owner, "Omnipotent", arrested.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

While BreachForums has [suffered data breaches](https://www.bleepingcomputer.com/news/security/breachforums-v1-hacking-forum-data-leak-exposes-members-info/) and [police actions](https://www.bleepingcomputer.com/news/security/fbi-seizes-breachforums-after-arresting-its-owner-pompompurin-in-march/) in [the past](https://www.bleepingcomputer.com/news/security/fbi-seize-breachforums-hacking-forum-used-to-leak-stolen-data/), it has been repeatedly relaunched under new domains, with some accusing it of now being a honeypot for law enforcement.

Yesterday, a website named after the ShinyHunters extortion gang released a 7Zip archive named breachedforum.7z.

This archive contains three files named:

* shinyhunte.rs-the-story-of-james.txt
* databoose.sql
* breachedforum-pgp-key.txt.asc

A representative of the ShinyHunters extortion gang told BleepingComputer they are not affiliated with the site that distributed this archive.

The archive's 'breachedforum-pgp-key.txt.asc' file is the PGP private key created on July 25, 2023, and used by BreachForums to sign official messages from the administrators. While the key has been leaked, it is passphrase-protected, and without the password, it can't be abused to sign messages.

![Passphrase-protected BreachForums PGP private key](https://www.bleepstatic.com/images/news/security/d/data-breaches/b/breachforums-2025/pgp-passphrase.jpg)

**Passphrase-protected BreachForums PGP private key**  
_Source: BleepingComputer_

The "databoose.sql" file is a MyBB users database table (mybb\_users) containing 323,988 member records that include member display names, registration dates, IP addresses, and other internal information.

BleepingComputer's analysis of the table shows that most of the IP addresses map back to a local loopback IP address (0x7F000009/127.0.0.9), so they are not of much use.

However, 70,296 records do not contain the 127.0.0.9 IP address, and the records we tested map to a public IP address. These public IP addresses could be an OPSEC concern for those people and valuable to law enforcement and cybersecurity researchers.

The last registration date in the newly leaked user database is from August 11, 2025, which is the same day that the previous BreachForums at breachforums\[.\]hn was closed. This shutdown followed the arrest of some of its [alleged operators](https://www.bleepingcomputer.com/news/security/breachforums-hacking-forum-operators-reportedly-arrested-in-france/).

That same day, a member of the ShinyHunters extortion gang [posted a message](https://web.archive.org/web/20250811213740/https://pastebin.com/raw/EDUtVYq2) on the "Scattered Lapsus$ Hunters" Telegram channel, claiming the forum was a law-enforcement honeypot. The BreachForums administrators subsequently denied these allegations.

The breachforums\[.\]hn domain was later [seized by law enforcement](https://www.bleepingcomputer.com/news/security/fbi-takes-down-breachforums-portal-used-for-salesforce-extortion/) in October 2025 after it was [repurposed to extort companies](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) impacted by the [widespread Salesforce data theft attacks](https://www.bleepingcomputer.com/tag/salesforce/) conducted by the ShinyHunters extortion group.

The current BreachForums administrator, known as "N/A," has acknowledged the new breach, stating that a backup of the MyBB user database table was temporarily exposed in an unsecured folder and downloaded only once.

"We want to address recent discussions regarding an alleged database leak and clearly explain what happened," N/A wrote on BreachForums.

"First of all, this is not a recent incident. The data in question originates from an old users-table leak dating back to August 2025, during the period when BreachForums was being restored/recovered from the .hn domain."

"During the restoration process, the users table and the forum PGP key were temporarily stored in an unsecured folder for a very short period of time. Our investigation shows that the folder was downloaded only once during that window," continued the administrator.

While the administrator said that BreachForums members should use disposable email addresses to reduce risk and that most IP addresses mapped to local IPs, the database still contains information that could be of interest to law enforcement.