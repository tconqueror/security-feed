# Scattered Spider is running a VMware ESXi hacking spree

![Scattered Spider is running a VMware ESXi hacking spree](https://www.bleepstatic.com/content/hl-images/2024/11/25/ghost-spider-center.jpg)

Scattered Spider hackers have been aggressively targeting virtualized environments by attacking VMware ESXi hypervisors at U.S. companies in the retail, airline, transportation, and insurance sectors.

According to the Google Threat Intelligence Group (GITG), the attackers keep employing their usual tactics that do not include vulnerability exploits but rely on perfectly executed social engineering "to bypass even mature security programs."

### A Scattered Spider attack

The researchers say that the gang starts an attack by impersonating an employee in a call to the IT help desk. The threat actor's purpose is to convince the agent to change the employee's Active Directory password and thus obtain initial access.

This allows Scattered Spider to scan the network devices for IT documentation that would provide high-value targets, like the names of domain or VMware vSphere administrators, and security groups that can provide administrative permissions over the virtual environment.

At the same time, they scan for privileged access management (PAM) solutions that could hold sensitive data useful for moving to valuable network assets.

"Armed with the name of a specific, high-value administrator, they make additional calls to the help desk. This time, they impersonate the privileged user and request a password reset, allowing them to seize control of a privileged account" - [Google Threat Intelligence Group](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944)

The hackers then work their way to obtain access to the company's VMware vCenter Server Appliance (vCSA) - a virtual machine that allows managing VMware vSphere environments, which includes the ESXi hypervisor for managing all the virtual machines on a physical server.

This level of access allows them to enable SSH connections on ESXi hosts and reset the root passwords. Further, they execute a so-called “disk-swap” attack to extract the critical NTDS.dit database for the Active Directory.

A disk-swap attack occurs when the threat actors powers off a Domain Controller virtual machine (VM) and dettaches its virtual disk only to attach it to another, unmonitored VM they control. After copying the sensitive data (e.g NTDS.dit file), they revert the process and power on the domain controller machine.

It is important to note that the level of control Scattered Spider obtains on the virtual infrastructure allows them to manage every assets available, including the backup machines, which are wiped of backup jobs, snaphots, and repositories.

In the last phase of the attack Scattered Spider leverages their SSH access to deliver and deploy ransomware binaries to encrypt all VM files detected in the datastores.

Based on their observations, GTIG researchers say that a Scattered Spider attack has five distinct phases that allow hackers to move from low-level access to taking complete control over the hypervisor.

![Scattered Spider attack chain](https://www.bleepstatic.com/images/news/u/1220909/2025/July/attack-chain.jpg)

**Scattered Spider attack chain**  
_Source: Google_

A Scattered Spider attack chain, complete from initial access to data exfiltration and ransomware deployment, could happen in just a few hours.

Even without exploiting any software vulnerabilities, the threat actor manages to obtain “an unprecedented level of control over an entire virtualized environment, allowing them to bypass many traditional in-guest security controls,” a Google representative told BleepingComputer.

While targeting ESXi hypervisors is not new (seen in Scattered Spider high-profile breaches like the [2023 MGM Resorts attack](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/)) GTIG notes that they’re seeing more ransomware groups adopting this tactic and expect the problem to grow.

One reason behind this could be that adversaries have noticed that VMware infrastructure is often poorly understood by organizations and, consequently, not as robustly defended.

To help organizations protect against these attacks, Google [published a technical post](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944) describing the stages of a Scattered Spider attack, explaining why it is efficient, and providing actions that a company can take to detect the breach at an earlier phase.

The proposed measures can be summarized in three main pillars:

* Lock down vSphere with execInstalledOnly, VM encryption, and disabled SSH. Avoid direct AD joins on ESXi, delete orphaned VMs, and enforce strict MFA and access policies. Continuously monitor for config drift.
* Use phishing-resistant MFA across VPN, AD, and vCenter. Isolate Tier 0 assets (DCs, backups, PAM) and avoid hosting them on the same infrastructure they secure. Consider separate cloud IdPs to break AD dependency.
* Centralize logs in a SIEM and alert on key behaviors, such as admin group changes, vCenter logins, and SSH enablement. Use immutable, air-gapped backups and test recovery against hypervisor-layer attacks.

Scattered Spider (also known as UNC3944, Octo Tempest, 0ktapus) is a financially motivated threat group specialized in social engineering to a level that it can impersonate company employees using the appropriate vocabulary and accent.

It has recently upped its activity with attacks on[ large UK retail firms](https://www.bleepingcomputer.com/news/security/uk-ncsc-cyberattacks-impacting-uk-retailers-are-a-wake-up-call/),[ airline and transportation](https://www.bleepingcomputer.com/news/security/scattered-spider-hackers-shift-focus-to-aviation-transportation-firms/) entities, and[ insurance companies](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/).

Although the UK’s National Crime Agency[ arrested four suspected members](https://www.bleepingcomputer.com/news/security/four-arrested-in-uk-over-mands-co-op-harrods-cyberattacks/) of the group, the malicious activity, originating from other clusters, has not subsided.