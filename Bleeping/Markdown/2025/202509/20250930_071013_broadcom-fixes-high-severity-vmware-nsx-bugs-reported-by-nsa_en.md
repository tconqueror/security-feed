# Broadcom fixes high-severity VMware NSX bugs reported by NSA

![VMware](https://www.bleepstatic.com/content/hl-images/2024/11/18/VMware.jpg)

Broadcom has released security updates to patch two high-severity VMware NSX vulnerabilities reported by the U.S. National Security Agency (NSA).

VMware NSX is a networking virtualization solution within VMware Cloud Foundation that enables administrators to deploy traditional and modern applications in private/hybrid clouds.

The first security flaw reported by the NSA, tracked as [CVE-2025-41251](https://nvd.nist.gov/vuln/detail/CVE-2025-41251), is due to a weakness in the password recovery mechanism that can let unauthenticated attackers enumerate valid usernames, which could later be used in brute-force attacks.

The second one ([CVE-2025-41252](https://nvd.nist.gov/vuln/detail/CVE-2025-41252)) is a username enumeration vulnerability that unauthenticated threat actors can also exploit to enumerate valid usernames, which could potentially lead to unauthorized access attempts.

"Broadcom would like to thank the National Security Agency for reporting this issue to us," the company [said](https://support.broadcom.com/web/ecx/support-content-notification/-/external/content/SecurityAdvisories/0/36150) in a Monday security advisory.

Yesterday, the company patched a high-severity SMTP header injection vulnerability ([CVE-2025-41250](https://nvd.nist.gov/vuln/detail/CVE-2025-41250)) in VMware vCenter that can let attackers with non-administrative privileges and permission to create scheduled tasks to manipulate the notification emails sent for scheduled tasks.

As part of a second security advisory, Broadcom disclosed three more security flaws in VMware Aria Operations and VMware Tools (CVE-2025-41244, CVE-2025-41245, CVE-2025-41246) that can be exploited to escalate privileges to root, steal other users' credentials, and access other guest VMs.

Earlier this year, [Broadcom also patched four vulnerabilities](https://www.bleepingcomputer.com/news/security/vmware-fixes-four-esxi-zero-day-bugs-exploited-at-pwn2own-berlin/) in VMware ESXi, Workstation, Fusion, and Tools that were disclosed and exploited as zero-days during the Pwn2Own Berlin 2025 hacking contest in May 2025, after [fixing three actively exploited VMware zero days](https://www.bleepingcomputer.com/news/security/broadcom-fixes-three-vmware-zero-days-exploited-in-attacks/) (CVE-2025-22224, CVE-2025-22225, and CVE-2025-22226) reported by the Microsoft Threat Intelligence Center.

State-sponsored hackers and cybercrime gangs, including ransomware operations, frequently target VMware vulnerabilities, given that enterprises widely use VMware products to transfer and store sensitive corporate data.

For instance, in November, [attackers began exploiting](https://www.bleepingcomputer.com/news/security/critical-rce-bug-in-vmware-vcenter-server-now-exploited-in-attacks/) two VMware vCenter Server flaws, a privilege escalation to root (CVE-2024-38813) and a critical remote code execution flaw (CVE-2024-38812), which were disclosed during China's 2024 Matrix Cup hacking contest.

In January 2024, Chinese state hackers were [linked to attacks exploiting a critical vCenter Server zero-day](https://www.bleepingcomputer.com/news/security/chinese-hackers-exploit-vmware-bug-as-zero-day-for-two-years/) (CVE-2023-34048) since late 2021, which led to the [deployment of VirtualPita and VirtualPie backdoors](https://www.bleepingcomputer.com/news/security/new-malware-backdoors-vmware-esxi-servers-to-hijack-virtual-machines/) on compromised ESXi systems.