# Hackers plant 4G Raspberry Pi on bank network in failed ATM heist

![Hacker being sneaky](https://www.bleepstatic.com/content/hl-images/2021/12/28/hacker.jpg)

The UNC2891 hacking group, also known as LightBasin, used a 4G-equipped Raspberry Pi hidden in a bank's network to bypass security defenses in a newly discovered attack.

The single-board computer was physically connected to the ATM network switch, creating an invisible channel into the bank's internal network, allowing the attackers to move laterally and deploy backdoors.

According to [Group-IB](https://www.group-ib.com/blog/unc2891-bank-heist/), which discovered the intrusion while investigating suspicious activity on the network, the goal of the attack was to spoof ATM authorization and perform fraudulent withdrawals of cash.

While LightBasin failed at that, the incident is a rare example of an advanced hybrid (physical+remote access) attack that employed several anti-forensics techniques to maintain a high degree of stealthiness.

The particular group is notorious for attacking banking systems, as Mandiant highlighted in a 2022 report presenting the then-new [Unix kernel rootkit "Caketap,"](https://www.bleepingcomputer.com/news/security/new-unix-rootkit-used-to-steal-atm-banking-data/) created for running on Oracle Solaris systems used in the financial sector.

Caketap manipulates Payment Hardware Security Module (HSM) responses, specifically the card verification messages, to authorize fraudulent transactions that the bank's systems would otherwise block.

Active since 2016, LightBasin has also successfully [attacked telecommunication systems](https://www.bleepingcomputer.com/news/security/lightbasin-hacking-group-breaches-13-global-telecoms-in-two-years/) for years, using the TinyShell open-source backdoor to move traffic between networks and route it through specific mobile stations.

## Raspberry $i

In the latest case, LightBasin gained physical access to a bank branch either on their own or by bribing a rogue employee who helped them to install a Raspberry Pi with a 4G modem on the same network switch as the ATM.

The device's outbound internet connectivity capabilities enabled the attackers to maintain persistent remote access to the bank's internal network while bypassing perimeter firewalls.

The Raspberry Pi hosted the TinyShell backdoor which the attacker leveraged for establishing an outbound command-and-control (C2) channel via mobile data.

In the subsequent phases of the attack, the threat actors moved laterally to the Network Monitoring Server, which had extensive connectivity to the bank's data center.

![The LightBasin attack](https://www.bleepstatic.com/images/news/u/1220909/2025/July/attack(1).jpg)

**Overview of the LightBasin attack**  
_Source: Group-IB_

From there, the attacker also pivoted to the Mail Server, which had direct internet access, and enabled persistence even when the Raspberry Pi was discovered and removed.

The backdoors used in lateral movement were named as 'lightdm' to mimic the legitimate LightDM display manager found on Linux systems, hence appearing innocuous.

Another element that contributed to the attack's high degree of stealth was LightBasin mounting alternative filesystems like tmpfs and ext4 over the '/proc/\[pid\]' paths of the malicious processes, essentially obscuring the related metadata from forensics tools.

Based on Group-IB's investigation, the Network Monitoring Server inside the bank network was found beaconing every 600 seconds to the Raspberry Pi on port 929, indicating that the device served as a pivot host.

The researchers say the attackers' ultimate goal was to deploy the Caketap rootkit, but that plan was foiled before it could materialize.