# Kickidler employee monitoring software abused in ransomware attacks

![Hacker](https://www.bleepstatic.com/content/hl-images/2022/10/09/hacker-looking-at-screens.jpg)

Ransomware operations are using legitimate Kickidler employee monitoring software for reconnaissance, tracking their victims' activity, and harvesting credentials after breaching their networks.

In attacks observed by cybersecurity companies [Varonis](https://www.varonis.com/blog/seo-poisoning#initial-access-and-persistence) and [Synacktiv](https://www.synacktiv.com/en/publications/case-study-how-hunters-international-and-friends-target-your-hypervisors), Qilin and Hunters International ransomware affiliates installed Kickidler, an [employee monitoring tool](http://www.kickidler.com/for-it/docs/grabber/) that can capture keystrokes, take screenshots, and create videos of the screen.

Kickidler's developer says the tool is used by over 5,000 organizations from 60 countries and provides visual monitoring and data loss prevention features.

The attacks started with the threat actors taking out Google Ads displayed when people searched for RVTools, a free Windows utility for managing VMware vSphere deployments. Clicking on the advertisement led to a fake RVTools site (rv-tool\[.\]net), promoting a trojanized program version.

The program is a malware loader that downloads and runs the SMOKEDHAM PowerShell .NET backdoor, which was used to deploy Kickidler on the device.

![Attack flow](https://www.bleepstatic.com/images/news/u/1109292/2025/Attack-flow(1).jpg)

_Attack flow (Varonis)_

While these attacks targeted enterprise administrators, whose accounts would typically provide the threat actors with privileged credentials after compromise, Varonis believes they may have maintained access to the victims' systems for days and even weeks to collect credentials needed to access off-site cloud backups without being detected.

"Given the increased targeting of backup solutions by attackers in recent years, defenders are decoupling backup system authentication from Windows domains. This measure prevents attackers from accessing backups even if they gain high-level Windows credentials," Varonis told BleepingComputer.

"Kickidler addresses this issue by capturing keystrokes and web pages from an administrator's workstation. This enables attackers to identify off-site cloud backups and obtain the necessary passwords to access them. This is done without dumping memory or other high-risk tactics that are more likely to be detected."

In both cases, after resuming malicious activity on the breached networks, the ransomware operators deployed payloads that targeted the victims' VMware ESXi infrastructure, encrypting VMDK virtual hard disk drives and causing widespread disruption.

The deployment script used by Hunters International leveraged VMware PowerCLI and WinSCP Automation to enable the SSH service, deploy the ransomware, and execute it on ESXi servers, Synacktiv said.

## **Legitimate RMM software abused in attacks**

While employee monitoring software isn't the go-to tool for ransomware gangs, they've abused legitimate remote monitoring and management (RMM) software for years.

As CISA, the NSA, and MS-ISAC warned in a [January 2023 joint advisory](https://www.bleepingcomputer.com/news/security/cisa-federal-agencies-hacked-using-legitimate-remote-desktop-tools/), attackers part of many ransomware operations are tricking victims into installing portable remote desktop solutions to bypass software controls and take over their systems without requiring admin privileges.

Since mid-October 2022, CISA has also discovered malicious activity within the networks of multiple [federal civilian executive branch](https://www.cisa.gov/agencies) (FCEB) agencies linked to this type of attack.

Recently, attackers have been seen [targeting vulnerable SimpleHelp RMM clients](https://www.bleepingcomputer.com/news/security/hackers-exploit-simplehelp-rmm-flaws-to-deploy-sliver-malware/) to create administrator accounts, install backdoors, and potentially set the stage for Akira ransomware attacks.

To defend against potential security breaches, network defenders are advised to audit installed remote access tools and identify authorized RMM software.

It's also recommended to use application controls to prevent the execution of unauthorized RMM software and to enforce the use of only authorized remote desktop tools, along with approved remote access solutions such as VPN or VDI.

Additionally, security teams should block inbound and outbound connections on standard RMM ports and protocols if not used.