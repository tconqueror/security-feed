# Kraken ransomware benchmarks systems for optimal encryption choice

![Kraken ransomware benchmarks systems for optimal encryption choice](https://www.bleepstatic.com/content/hl-images/2025/02/12/ransomware-3.jpg)

The Kraken ransomware, which targets Windows, Linux/VMware ESXi systems, is testing machines to check how fast it can encrypt data without overloading them.

According to Cisco Talos researchers, Kraken's feature is a rare capability that uses temporary files to choose between full and partial data encryption.

The Kraken ransomware emerged at the begining of the year as a continuation of the HelloKitty operation, and engages in big-game hunting attacks with data theft for double extortion.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

On the gang's data leak sites there are listed victims from the United States, the UK, Canada, Panama, Kuwait, and Denmark.

Cisco researchers note that various mentions on Kraken’s site, as well as similarities in the ransom note, indicate connections with the now defunct HelloKitty ransomware that [gained prominence](https://www.bleepingcomputer.com/news/security/hellokitty-ransomware-behind-cd-projekt-red-cyberattack-data-theft/) in 2021 and [attempted a rebranding](https://www.bleepingcomputer.com/news/security/hellokitty-ransomware-rebrands-releases-cd-projekt-and-cisco-data/) after the [leak of its source code](https://www.bleepingcomputer.com/news/security/hellokitty-ransomware-source-code-leaked-on-hacking-forum/).

Apart from the ransomware operation, Kraken has also launched a new cybercrime forum named “The Last Haven Board” to facilitate supposedly secure communications and exchanges.

![Kraken's extortion portal on the dark web](https://www.bleepstatic.com/images/news/u/1220909/2025/November/krakenblog(1).jpg)

**Kraken's extortion portal on the dark web**  
_Source: BleepingComputer_

## Kraken attack chain

According to Cisco’s observations, Kraken ransomware attacks typically begin with the exploitation of SMB vulnerabilities on internet-facing assets, providing the threat actors with an initial foothold.

Next, the intruder extracts admin account credentials and uses them to re-enter the environment via Remote Desktop Protocol (RDP) and deploy the Cloudflared and SSHFS tools.

Cloudflared is used for creating a reverse tunnel from the victim host back to the attacker’s infrastructure, and SSHFS allows exfiltrating data through mounted remote filesystems.

Using persistent Cloudflared tunnels and RDP, Kraken operators navigate compromised networks and move laterally to all reachable machines to steal valuable data and lay the ground for the deployment of the ransomware binaries.

**Kraken infection chain**  
_Source: Cisco_

## Setting the encryption mode

When the encryption command is issued, Kraken will perform a performance benchmark on each machine, the researchers [say](https://blog.talosintelligence.com/kraken-ransomware-group/).

The process includes the creation of a temporary file with random data, encrypting it in a timed operation, calculating the result, and then deleting the file.

Based on the result, the encryption decides if the data will be encrypted completely or partially.

**Speed calculation function**  
_Source: Cisco_

Cisco Talos notes that assessing the machine's capabilities is likely to move quickly with the final stage of the attack and deal maximum damage without triggering alerts due to intensive resource usage.

Before triggering the actual encryption, Kraken deletes shadow volumes and the Recycle Bin and stops backup services running on the system.

Cisco explains that the Windows version of Kraken features four encryption modules: 

1. **SQL database** – Identifies Microsoft SQL Server instances through registry keys, locates their database file directories, verifies the paths, and encrypts the SQL data files.
2. **Network share** – Enumerates accessible network shares via WNet APIs, ignores ADMIN$ and IPC$, and encrypts files on all other reachable shares.
3. **Local drive** – Scans available drive letters, targets removable, fixed, and remote drives, and encrypts their contents using separate worker threads.
4. **Hyper-V** – Uses embedded PowerShell commands to list VMs, obtain their virtual disk paths, forcibly stop running VMs, and encrypt the associated VM disk files.

The Linux/ESXi version enumerates and forcibly terminates running virtual machines to unlock their disk files, and then performs multi-threaded full or partial encryption using the same benchmarking logic as the Windows version.

After finishing the encryption, an auto-generated ‘_bye\_bye.sh_’ script executes to remove all logs, shell history, the Kraken binary, and finally the script itself.

Encrypted files are appended with the ‘.zpsc’ file extension, and a ransom note (‘readme\_you\_ws\_hacked.txt’) is dropped on impacted directories.

**Kraken ransom note**  
_Source: Cisco_

Cisco notes that in one case, it has observed a ransom demand of $1 million to be paid in Bitcoin.

The complete indicators of compromise (IoCs) associated with Kraken ransomware attacks are available on this [GitHub repository](https://github.com/Cisco-Talos/IOCs/blob/main/2025/11/kraken-ransomware-group.txt).