# Meet ShinySp1d3r: New Ransomware-as-a-Service created by ShinyHunters

![Hacker with a smiley face](https://www.bleepstatic.com/content/hl-images/2024/06/15/emoji-hacker.jpg)

An in-development build of the upcoming ShinySp1d3r ransomware-as-a-service platform has surfaced, offering a preview of the upcoming extortion operation.

ShinySp1d3r is the name of an emerging RaaS created by threat actors associated with the ShinyHunters and Scattered Spider extortion groups.

These threat actors have traditionally used other ransomware gangs' encryptors in attacks, including [ALPHV/BlackCat](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), and [DragonForce](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/), but are now creating their own operation to deploy attacks themselves and their affiliates.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

News of the upcoming RaaS first came to light on a Telegram channel, where threat actors calling themselves "Scattered Lapsus$ Hunters," from the names of the three gangs forming the collective (Scattered Spider, Lapsus$, and ShinyHunters), were attempting to [extort victims of data theft at Salesforce](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) and [Jaguar Land Rover (JLR)](https://www.bleepingcomputer.com/news/security/jaguar-land-rover-extends-shutdown-after-cyberattack-by-another-week/).

## The ShinySp1d3r encryptor

BleepingComputer discovered a sample of the ShinySp1d3r after it was uploaded to [VirusTotal](https://www.virustotal.com/gui/file/3bf53cddf7eb98d9cb94f9aa9f36c211a464e2c1b278f091d6026003050281de). Since then, additional samples have been uploaded, allowing researchers to analyze the upcoming ransomware encryptor.

**Note:** While some of our images show the name as 'Sh1nySp1d3r,' BleepingComputer has been told that the RaaS is operating under ShinySp1d3r and the name will be changed in future builds.

The encryptor is developed by the ShinyHunters extortion group, which is building it from scratch, rather than utilizing a previously leaked codebase like LockBit or Babuk.

![The ShinySp1d3r ransomware encryptor](https://www.bleepstatic.com/images/news/ransomware/s/ShinySp1d3r/windows-encryptor.jpg)

**The ShinySp1d3r ransomware encryptor**  
_Source: BleepingComputer_

As a result, the ShinySp1d3r Windows encryptor offers many features, some common to other encryptors and others not seen before.

According to analysis shared with BleepingComputer by analysts at ransomware recovery firm [Coveware](https://www.coveware.com/), these features include:

* Hooking the EtwEventWrite function to prevent data from being logged to the Windows Event Viewer.
* Kills processes that keep a file open and prevent it from being encrypted by iterating over processes with a handle to the file, then killing them. The encryptor also has a 'forceKillUsingRestartManager' function that uses the [Restart Manager API](https://learn.microsoft.com/en-us/windows/win32/rstmgr/restart-manager-portal), but it is not implemented yet.
* Fills free space on a drive by writing random data into files called 'wipe-\[random\].tmp'. This is done to overwrite any deleted files, making them more challenging, if not impossible, to recover.
* Kills a hard-coded list of processes and services.
* Checks available memory to calculate the optimal amount of data to read at a time.
* Contains the ability to propagate to other devices on the local network through one of these methods:  
   * **deployViaSCM** \- Creates a service to run the malware  
   * **deployViaWMI**\- Runs the malware via WMI with Win32\_Process.Create  
   * **attemptGPODeployment** \- Creates a GPO startup script in scripts.ini to run the malware
* Contains anti-analysis features and overwrites the contents of a memory buffer to prevent forensic analysis.
* Deletes Shadow Volume Copies to prevent them from being used to restore encrypted files.
* Searches for hosts with open network shares and attempts to encrypt them.
* Encrypts files with different chunk sizes and offsets. It is unclear why it does that, or whether this information is stored in an encrypted file header (more about that later).

When encrypting files, the ransomware uses the ChaCha20 encryption algorithm with the private key protected using RSA-2048\. Each file will have its own unique extension as shown in the folder below, which ShinyHunters claimed to BleepingComputer was based on a mathematical formula.

**Folder encrypted by ShinySp1d3r ransomware**  
_Source: BleepingComputer_

Each encrypted file contains a file header that begins with **SPDR** and ends with **ENDS**, as shown in the image below. This header contains information about the encrypted file, including the filename, the encrypted private key, and other metadata.

**Files encrypted by ShinySp1d3r ransomware**  
_Source: BleepingComputer_

Every folder on the encrypted device will contain a ransom note, currently hardcoded to **R3ADME\_1Vks5fYe.txt**, that includes information on what happened to a victim's files, how to negotiate the ransom, and a TOX address for communications.

The ransom note also includes a link to the Tor data leak site, but currently has a placeholder onion URL that is not valid.

"This communication has been issued on behalf of the ShinySp1d3r group. It is intended exclusively for internal incident response personnel, technical leadership, or designated external advisors," begins the ransom note.

"A critical encryption event has taken place within your infrastructure. Certain digital assets have become inaccessible, and selected data was securely mirrored. The goal of this message is not disruption, but to provide your team with a confidential opportunity to resolve the situation efficiently and permanently."

**ShinySp1d3r ransom note**  
_Source: BleepingComputer_

The ransom note goes on to say that victims have three days to begin negotiations before the attack is made public on the data leak site.

In addition to the ransom notes, the encryptor will also set a Windows wallpaper that warns the victim of what happened and urges them to read the ransom note.

**ShinySp1d3r wallpaper**  
_Source: BleepingComputer_

While BleepingComputer only obtained the Windows encryptor, ShinyHunters says they have completed a CLI build with runtime configuration and are close to finishing versions for Linux and ESXi. They also said that a separate "lightning version" is in development, optimized for speed.

"We're also working on a "lightning version" pure ASM, its like lockbit green - another windows locker variant but in pure assembly and its pretty simple,” ShinyHunters told BleepingComputer.

As this is a debug build of an in-development ransomware, we will likely see additional features added in the future.

As for the RaaS operation itself, ShinyHunters says it will be run by their group under the Scattered LAPSUS$ Hunters name.

"Yes, it will be lead by me/us 'ShinyHunters' but operated under the Scattered LAPSUS$ Hunters (SLH) brand, hence the name ShinySp1d3r, to demonstrate the 'alliance' or 'cooperation' between these groups," ShinyHunters told BleepingComputer.

The threat actor also claims that any company in the healthcare sector, including pharmaceutical companies, hospitals, clinics, and insurance firms, cannot be targeted with their encryptor. However, BleepingComputer has been told this by other ransomware gangs in the past, many of whom later allowed those policies to be violated.

Similar to other ransomware operations, ShinyHunters says attacks against Russia and other CIS countries are prohibited, as many affiliates will come from those regions and could become targets of law enforcement.