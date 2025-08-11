# MuddyWater’s DarkBit ransomware cracked for free data recovery

![Hand holding a cyber key](https://www.bleepstatic.com/content/hl-images/2022/10/09/cyber-key.jpg)

Cybersecurity firm Profero cracked the encryption of the DarkBit ransomware gang's encryptors, allowing them to recover a victim's files for free without paying a ransom.

This occurred in 2023 during an incident response handled by Profero experts, who were brought in to investigate a ransomware attack on one of their clients, which had encrypted multiple VMware ESXi servers.

The timing of the cyberattack suggests that it was in retaliation for the 2023 drone strikes in Iran that targeted an ammunition factory belonging to the Iranian Defence Ministry.

In the ransomware attack, the threat actors claimed to be from DarkBit, who previously posed as pro-Iranian hacktivists, targeting [educational institutes in Israel](https://www.bleepingcomputer.com/news/security/ransomware-hits-technion-university-to-protest-tech-layoffs-and-israel/). The attackers included anti-Israel statements in their ransom notes, demanding ransom payments of 80 Bitcoin.

Israel's National Cyber Command [linked DarkBit attacks](https://www.gov.il/he/pages/%5Fmuddywater) to the Iranian state-sponsored APT hacking group known as [MuddyWater](https://www.microsoft.com/en-us/security/blog/2023/04/07/mercury-and-dev-1084-destructive-attack-on-hybrid-environment/), who have a history of conducting cyberespionage attacks.

In the case investigated by Profero, the attackers did not engage in ransom payment negotiations, but instead appeared to be more interested in causing operational disruption.

Instead, the attackers launched an influence campaign to maximize reputational damage to the victim, which is a [tactic associated](https://www.bleepingcomputer.com/news/security/russian-sandworm-hackers-pose-as-hacktivists-in-water-utility-breaches/) with nation-state actors posing as hacktivists.

## Decrypting DarkBit

At the time of the attack, no decryptor existed for DarkBit ransomware, so Profero researchers decided to analyze the malware for potential weaknesses.

DarkBit uses a unique AES-128-CBC key and Initialization Vector (IV) generated at runtime for each file, encrypted with RSA-2048, and appended to the locked file.

![Final encrypted file structure](https://www.bleepstatic.com/images/news/u/1220909/2025/August/structure.png)

**Final encrypted file structure**  
_Source: Profero_

Profero found that the key generation method used by DarkBit is low entropy. When combined with the encryption timestamp, which can be inferred from file modification times, the total keyspace is reduced to a few billion possibilities.

Moreover, they found that Virtual Machine Disk (VMDK) files on ESXi servers have known header bytes, so they only had to brute force the first 16 bytes to see if the header matched, instead of the entire file.

Profero built a tool to try all possible seeds, generate candidate key/IV pairs, and check against VMDK headers, which they ran in a high-performance computing environment, recovering valid decryption keys.

In parallel, the researchers discovered that much of the VMDK file content hadn't been impacted by DarkBit's intermittent encryption, as those files are sparse and many encrypted chunks fall onto empty space.

This allowed them to retrieve significant amounts of valuable data without having to decrypt it by brute-forcing keys.

"As we began to work on speeding up our brute force, one of our engineers/team members? had an interesting idea," explained Profero.

"VMDK files are sparse, which means they are mostly empty, and therefore, the chunks encrypted by the ransomware in each file are also mostly empty. Statistically, most files contained within the VMDK filesystems won't be encrypted, and most files inside these file systems were anyways not relevant to us/our task/our investigation."

"So, we realized we could walk the file system to extract what was left of the internal VMDK filesystems... and it worked! Most of the files we needed could simply be recovered without decryption."

Profero noted that DarkBit's objectives would have been better served with a data wiper rather than ransomware, and that the attackers' refusal to negotiate left them no choice but to dissect the malware's encryption in search of a recovery method.

While Profero is not publicly releasing the DarkBit decryptor, they told BleepingComputer that future victims can contact them for assistance.