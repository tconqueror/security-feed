# CISA warns of Akira ransomware Linux encryptor targeting Nutanix VMs

![Hacker](https://www.bleepstatic.com/content/hl-images/2024/12/10/hacker-box.jpg)

US government agencies are warning that the Akira ransomware operation has been spotted encrypting Nutanix AHV virtual machines in attacks. 

An updated joint advisory from CISA, the FBI, the Department of Defense Cyber Crime Center (DC3), the Department of Health and Human Services (HHS), and several international partners alerts that Akira ransomware has expanded its encryption capabilities Nutanix AHV VM disk files.

The advisory includes new indicators of compromise and tactics observed through FBI investigations and third-party reporting as recent as November 2025.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

## Encrypting Nutanix VMs in attacks

The advisory warns that in June 2025 Akira actors started to encrypt disk files for Nutanix AHV virtual machines.

"In a June 2025 incident, Akira threat actors encrypted Nutanix AHV VM disk files for the first time, expanding their capabilities beyond VMware ESXi and Hyper-V by abusing Common Vulnerabilities and Exposures (CVE)-2024-40766 \[Common Weakness Enumeration (CWE)-284: Improper Access Control\], a SonicWall vulnerability," reads the [updated advisory](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-109a).

Nutanix's AHV platform is a Linux-based virtualization solution that runs and manages virtual machines on Nutanix's infrastructure.

As it is widely deployed, it is no surprise that ransomware gangs would begin to target virtual machines on this platform, as they do with VMware ESXi and Hyper-V.

While CISA has not shared how Akira is targeting Nutanix AHV environments, Akira Linux encryptors analyzed by BleepingComputer attempt to encrypt files with the **.qcow2** extension, which is the virtual disk format used by Nutanix AHV.

However, the .qcow2 file extension has been targeted by Akira Linux encryptors since at least the end of 2024.

Furthermore, Akira's focus on Nutanix VMs is also not as developed as its targeting of VMware ESXi

The Linux encryptor uses _esxcli_ and _vim-cmd_ to gracefully shut down ESXi virtual machines before encrypting their disks, but for Nutanix AHV, it simply encrypts the .qcow2 files directly and does not use the platform's _acli_ or _ncli_ commands to power down AHV VMs.

## Other updates

The updated advisory also includes new information on Akira's intrusion methods and post-compromise tactics.

To breach corporate networks, Akira affiliates commonly use stolen or brute-forced VPN and SSH credentials on exposed routers and [exploit SonicWall vulnerabilities](https://www.bleepingcomputer.com/news/security/akira-ransomware-breaching-mfa-protected-sonicwall-vpn-accounts/) (CVE-2024-40766) on exposed firewalls.

Once they gain access, they exploit the CVE-2023-27532 or CVE-2024-40711 vulnerabilities on unpatched Veeam Backup & Replication servers to gain access to and delete backups.

Within a network, Akira members have been observed using utilities such as nltest, AnyDesk, LogMeIn, Impacket's wmiexec.py, and VB scripts to perform reconnaissance, spread laterally to other systems, and establish persistence. The threat actors also commonly remove endpoint detection tools and create new administrative accounts for persistence.

In one incident, the attackers powered down a domain controller VM, copied its VMDK files, attached them to a new VM, and extracted the NTDS.dit file and SYSTEM hive to obtain a domain administrator account.

The advisory notes that the "Megazord" tool previously linked to Akira operations appears to have been abandoned since 2024.

Akira has exfiltrated data in as little as two hours during some attacks, and for command-and-control has relied on tunneling tools such as Ngrok to establish encrypted channels that bypass perimeter monitoring.

The advisory urges organizations to review the updated guidance and implement the recommended mitigations.

CISA and the FBI also continue to recommend regular offline backups, enforced multifactor authentication, and quick patching of known exploited vulnerabilities.