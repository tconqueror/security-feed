# The Hidden Risk in Virtualization: Why Hypervisors are a Ransomware Magnet

![Hacker looking at a computer screen](https://www.bleepstatic.com/content/posts/2025/12/14/huntress-header-image.jpg)

_Author: Dray Agha, Senior Manager, Hunt & Response, at Huntress Labs_

Hypervisors are the backbone of modern virtualized environments, but when compromised, they can become a force multiplier for attackers. A single breach at this layer can put dozens or even hundreds of virtual machines at risk simultaneously. Unlike traditional endpoints, hypervisors often operate with limited visibility and protections, meaning conventional security tools may be blind to an attack until it is too late.

From our vantage point in the SOC and threat-hunting space at Huntress, we are seeing adversaries increasingly target hypervisors to deploy ransomware at scale. Specifically, in 2025, Huntress case data revealed a stunning surge in hypervisor ransomware: its role in malicious encryption rocketed from just 3% in the first half of the year to 25% so far in the second half.

The primary actor driving this trend is the Akira ransomware group.This shift underscores the importance of hardening the hypervisor layer with the same rigor applied to endpoints and servers.

In this article, we outline the threats we’ve observed in the wild and provide practical guidance for securing your hypervisor infrastructure, from patching and access control to runtime hardening and robust recovery strategies.

## Hypervisors: A New Battleground in Ransomware Operations

In the last few months of 2025, Huntress has observed adversaries target hypervisors in an attempt to circumvent endpoint and network security controls.

And this makes sense: as defenders continue to harden endpoints and servers, adversaries are increasingly shifting their focus to the hypervisor layer, the foundation of virtualized infrastructure - a Type 1 ("bare metal") hypervisor is the foundation, installed directly on server hardware, a Type 2 ("hosted") hypervisor is an app that sits on top of your regular computer's OS.The shift is following a familiar playbook.

We've seen it with attacks on VPN appliances: threat actors realize that the host operating system is often proprietary or restricted, meaning defenders cannot install critical security controls like EDR. This creates a significant blind spot.

The same principle applies to Type 1 hypervisors; they are the ultimate "land-and-expand" target where traditional endpoint security often cannot reach.

We’ve also observed multiple cases where ransomware operators deploy **ransomware payloads directly through hypervisors**, bypassing traditional endpoint protections entirely.

In some instances, attackers leverage built-in tools such as openssl to perform encryption of the virtual machine volumes, avoiding the need to upload custom ransomware binaries.

* Once inside a network, attackers often pivot towards hypervisors using compromised internal authentication credentials in environments where network segmentation has failed to deny lateral movement to the hypervisor management page. This move grants them elevated control over multiple guest systems from a single management interface.
* We’ve seen misuse of Hyper-V management utilities, to modify VM settings and undermine security features. This includes disabling endpoint defenses, tampering with virtual switches, and preparing VMs for ransomware deployment at scale.

![Fig 1: Extract from Huntress Platform detecting adversary manipulating Hyper-V](https://www.bleepstatic.com/images/news/security/h/huntress-labs/virtualization-ransomware/huntress-detection-timeline.jpg)

**Fig 1: Extract from Huntress Platform detecting adversary manipulating Hyper-V**

This shift underscores a growing and uncomfortable trend: Attackers are targeting the infrastructure that controls all hosts, and with access to the hypervisor, adversaries dramatically amplify the impact of their intrusion.

## [Share the Gift of Security](https://www.huntress.com/cybersecurity-education/cybersecurity-awareness/secure-the-holiday-spirit-from-cyber-attacks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-11-camp-sat-global-prospect-all-x-gift%5Fof%5Fsat&utm%5Fcontent=december&hnt=f2jcfqx6qjxf)

Hackers love the holidays too! Share FREE Security Awareness Training with family & friends to keep them safe.

Quick, fun lessons to sharpen their cyber-smarts! Access extended through 1/31/26.

[Sign Up For Free](https://www.huntress.com/cybersecurity-education/cybersecurity-awareness/secure-the-holiday-spirit-from-cyber-attacks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-11-camp-sat-global-prospect-all-x-gift%5Fof%5Fsat&utm%5Fcontent=december&hnt=f2jcfqx6qjxf)

## Secure access, enforce least privilege, and separate the management plane

If an attacker can obtain administrative credentials for the hypervisor, they can deploy ransomware payloads that affect every VM on the host. Also, using domain-joined accounts (e.g., Active Directory (AD) accounts) for ESXi increases lateral movement risk. 

What to do:

* **Use local ESXi accounts.** Avoid using general-purpose domain admin accounts for management. Instead, create dedicated, local ESXi accounts or strictly limited, audited domain accounts with only the necessary permissions. If a domain admin account is compromised, this separation prevents immediate, unauthorized access to the hypervisor and its virtual machines.
* **Enforce Multi-factor Authentication (MFA).** This is non-negotiable for all critical infrastructure. Enforce MFA for host management interfaces and vCenter access to protect against credential theft. An attacker with a stolen username and password will be blocked, significantly raising the effort required for a successful breach. This control provides a robust defense against common phishing and brute-force attacks.**Use strong passwords stored in a secure password vault.** ESXi credentials should be extremely strong and stored only in a dedicated password vault, never in shared documents or less secure locations. This prevents credential exposure through common attack vectors like compromised file shares or insecure password management practices.
* **Segregate the host management network.** Segregate the hypervisor’s management network from production and general user networks. Create a dedicated VLAN or network segment that is logically and/or physically separate. By limiting the number of endpoints that can even attempt to connect to the hypervisor management interface, you drastically reduce the potential attack surface.
* **Deploy a jump box or bastion server.** To ensure all administrative access is audited and controlled, deploy a jump box or bastion server that IT admins must access first, before pivoting to the hypervisor. This setup eliminates direct connections from potentially less-secure administrator workstations. The jump box acts as a monitored checkpoint, allowing for session recording, logging of all commands, and enforcement of security policies before granting access to critical infrastructure.
* **Apply the principle of least privilege(PoLP).** Strictly limit access to the control plane (vCenter and individual hosts). Grant only the minimum required roles for necessary administrative functions, such as resource management or patching, to both human administrators and service accounts. Enforcing PoLP ensures that a potential compromise of a single account cannot be leveraged for wholesale changes across the entire virtualized environment.
* **Restrict management access to dedicated admin devices.** Limit ESXi management interface access to specific administrative devices with static IP addresses. This creates an additional barrier by ensuring that only known, authorized endpoints can attempt to connect to the hypervisor, further reducing the attack surface.

## Lock down the hypervisor runtime environment and enforce code-/execution controls

One of the unique risks with hypervisor-level ransomware is that once the attacker is on the host, they can run code at the hypervisor level, bypassing guest-OS controls. You need to harden the host so it only runs expected, signed code and trusted modules.

What to do:

* Enable the advanced host setting **VMkernel.Boot.execInstalledOnly = TRUE** so that only binaries installed via signed VIBs can execute, which prevents custom, malicious binaries from running on the host.
* Disable/close unnecessary services such as SSH or ESXi Shell when not in use; enable lockdown mode.

## Keep the hypervisor patched, up to date, and exposed surfaces minimised

Attackers are actively targeting ESXi hosts via known vulnerabilities for mass encryption operations. 0days and CVEs are not going to likely be the most common / real reason for compromise, and likely to be lapses in security segmentation. However, maintaining patching is critical.

For example, [CVE-2024-37085](https://nvd.nist.gov/vuln/detail/cve-2024-37085) highlights this hypervisor risk perfectly. This vulnerability allows attackers with adequate AD permissions to bypass authentication and instantly seize full administrative control of an ESXi host, leading to [mass encryption of all VMs in seconds](https://www.microsoft.com/en-us/security/blog/2024/07/29/ransomware-operators-exploit-esxi-hypervisor-vulnerability-for-mass-encryption/).

The exploit works because vulnerable ESXi hosts automatically grant full admin privileges to the 'ESX Admins' AD group. Threat actors simply recreate that group to immediately seize the keys to the kingdom.

These initial compromises often start with unpatched management interfaces or exposed protocols, like Service Location Protocol (SLP), which provide a low-effort entry point.

 What to do:

* Maintain an inventory of all ESXi hosts (and associated management components like vCenter) and their patch level.
* Prioritize security patches and updates from the vendor, especially for hypervisor-related CVEs.
* Disable or restrict services you don't need or ensure they are not exposed externally. Service Location Protocol (SLP/port 427) has been exploited by ransomware groups like ESXArgs and should be disabled. Follow [VMware's official remediation guidance](https://knowledge.broadcom.com/external/article?legacyId=76372).
* Ensure that ESXi hosts are not directly exposed to the internet for management. Use VPNs, bastion hosts, or isolated management networks.

## Backup strategy, immutable snapshots and rapid recovery capability

Even with strong prevention, risk remains. The hypervisor layer is high-impact; fallback is mandatory. Many guides emphasise that recovery is the last line of defense. Ransomware targeting ESXi typically seeks to encrypt VMDKs and host files; without good backups you may be forced to pay.

What to do:

* Adopt the “3-2-1” backup rule: have at least three copies of data, on two different media, and one copy offsite/off the hypervisor network.
* Use immutable backup repositories or snapshots so that once written they cannot be modified or deleted by ransomware.
* Do not connect your backup repository to Active Directory or any centralized identity management system. Instead, use separate, non-domain-joined, and dedicated local accounts to prevent a compromised AD credential from enabling ransomware to spread directly to your critical backup location.
* Ensure backups include full VM images and associated hypervisor state, so you can rebuild quickly.
* Test your backups regularly. Don’t just confirm that you can mount a backup and access files, but ensure that your OS fully starts and that you can login with known credentials.
* Practice full recovery drills on an annual basis at a minimum. Assumptions lead to longer periods of downtime. Here are some additional considerations:  
   * Have you tested in your offsite and/or failover locations?  
   * Can you confirm that your servers have the correct networking/connectivity? Can you access these failover servers from production endpoints?  
   * Does the backup site/failover location’s firewall already have the required allowlisting and firewall rules to ensure proper communication from critical tooling, such as EDR, RMM, and VPN clients?

## Monitor, detect anomalies, and assume breach (defense-in-depth)

Because the hypervisor layer is often less visible to traditional endpoint security tools like EDR, you need an alternative detection strategy. Attackers often perform actions like changing the VIB acceptance level, enabling SSH, disabling lockdown mode, or creating new admin accounts, as precursors to ransomware payload deployment.

Without monitoring, you may only detect the event after the encryption is complete.

What to do:

* Forward ESXi logs to your SIEM and create alerts for key suspicious events (like new root login, service enablement, VIB acceptance change, datastore unmounts).
* Monitor configurations for drift. If any host has lockdown mode disabled, SSH enabled, or execInstalledOnly turned off, flag it for review.
* Log management network traffic. Remember earlier when we recommended putting ESXi and other critical infrastructure control panes on their own VLAN or network segment? Now it's time to look for unusual source IPs accessing the hypervisor management interface (ideally you are only allowing traffic from your jump server), lateral movement attempts, or large datastore IO patterns consistent with VM encryption.
* Use a zero-trust mindset for hypervisor management, and assume credentials may be compromised, and build alerts accordingly.
* Unlike traditional syslog formats, ESXi separates logs by specific activities into distinct files. The following are the most critical log files for detecting and investigating hypervisor compromises: **/var/log/auth.log** (authentication events), **/var/log/hostd.log** (host agent activity), **/var/log/shell.log** (ESXi shell commands), and **/var/log/vobd.log** (VMware observer daemon). For log configuration guidance, see[ ](https://knowledge.broadcom.com/external/article/306962)[Broadcom's documentation](https://knowledge.broadcom.com/external/article/306962) and[ ](https://www.sygnia.co/blog/esxi-ransomware-ssh-tunneling-defense-strategies/)[Sygnia's ESXi defense strategies](https://www.sygnia.co/blog/esxi-ransomware-ssh-tunneling-defense-strategies/).

When partnering with a third-party SOC or MDR provider, consider establishing a shared responsibility model. Your external security partner won't have the necessary business context to distinguish routine internal maintenance from an adversary breaking in at 2 AM.

This distinction is critical: the third-party SOC is best positioned to detect universal evil, like the execution of ransomware itself. To augment this, we recommend that your internal security team focus on monitoring for insider threats and actions that only they can contextualize, such as a late-night login followed by the enabling of SSH.

For this model to succeed, IT teams must strictly adhere to change control procedures and communicate all expected hypervisor changes to internal security. This ensures the SOC is aware of all anticipated activity, enabling all parties to focus their efforts where they are most effective.

## Conclusion

Protecting bare-metal hypervisors like ESXi from ransomware requires a layered, proactive approach. From patching and access control, through runtime hardening and recovery readiness, to detection and logging, you need to cover all angles.

If you need more comprehensive guidance on preparing for the worst, review our guide to [Disaster Recovery Planning](https://www.huntress.com/cybersecurity-101/topic/disaster-recovery-plan?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-12-camp-multi-global-prospect-iis-x-3p%5Fblog&hnt=tjmscapixr9u). Now is the time for your organization to ask: when was the last time we fully updated and tested our IRPs and DRPs, specifically confirming the ability to restore and run all guest virtual machines?

Despite our best prevention and detection efforts, organizations should also prepare for the possibility of a successful compromise. If you find yourself responding to an ESXi environment compromised, we recommend reviewing this comprehensive [ESXi IR Guide](https://mikecybersec.notion.site/ESXi-IR-Guide-0ffbcec7272244d6b10dba4f4d16a7c8#1ec81b1bcfab8048bfade64d81a0916f). The guide provides detailed incident response procedures and forensic artifacts, specifically tailored for ESXi environments.

Leveraging Huntress, you may already apply many of these at the OS/endpoint layer; but the hypervisor demands the same rigor (and often more) because of its potential for mass impact.

If you embed this article’s defense guidance into your environment and security processes, you significantly raise the barrier for ransomware actors.

## Maintain Situational Awareness in 2026—Register for Tradecraft Tuesday

Tradecraft Tuesday provides cybersecurity professionals with an in-depth analysis of the latest threat actors, attack vectors, and mitigation strategies. Each weekly session features technical walkthroughs of recent incidents, comprehensive breakdowns of malware trends, and up-to-date indicators of compromise (IOCs).

Participants gain:

* Detailed briefings on emerging threat campaigns and ransomware variants
* Evidence-driven defense methodologies and remediation techniques
* Direct interaction with Huntress analysts for incident response insights
* Access to actionable threat intelligence and detection guidance

**[Register for Tradecraft Tuesday →](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-12-camp-multi-global-prospect-iis-x-3p%5Fblog&hnt=tjmscapixr9u)**

Advance your defensive posture with real-time intelligence and technical education specifically designed for those responsible for safeguarding their organization’s environment.

_Sponsored and written by [Huntress Labs](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-12-camp-multi-global-prospect-iis-x-3p%5Fblog&hnt=tjmscapixr9u)._