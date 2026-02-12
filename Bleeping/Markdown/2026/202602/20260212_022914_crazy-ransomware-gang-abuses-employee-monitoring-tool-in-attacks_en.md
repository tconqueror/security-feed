# Crazy ransomware gang abuses employee monitoring tool in attacks

![Hacker monitoring employees](https://www.bleepstatic.com/content/hl-images/2026/02/11/hacker-employee-monitoring.jpg)

A member of the Crazy ransomware gang is abusing legitimate employee monitoring software and the SimpleHelp remote support tool to maintain persistence in corporate networks, evade detection, and prepare for ransomware deployment.

The breaches were observed by researchers at [Huntress](https://www.huntress.com/blog/employee-monitoring-simplehelp-abused-in-ransomware-operations), who investigated multiple incidents where threat actors deployed Net Monitor for Employees Professional alongside SimpleHelp for remote access to a breached network, while blending in with normal administrative activity.

In one intrusion, attackers installed Net Monitor for Employees Professional using the Windows Installer utility, msiexec.exe, allowing them to deploy the monitoring agent on compromised systems directly from the developer's site.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices) 

Once installed, the tool allowed attackers to remotely view the victim's desktop, transfer files, and execute commands, effectively providing full interactive access to compromised systems.

The attackers also attempted to enable the local administrator account using this command:

```
net user administrator /active:yes
```

For redundant persistence, attackers downloaded and installed the SimpleHelp remote access client via PowerShell commands, using file names similar to the legitimate Visual Studio vshost.exe.

The payload was then executed, allowing attackers to maintain remote access even if the employee monitoring tool was removed.

The SimpleHelp binary was sometimes disguised using filenames that pretended to be related to OneDrive:

```
C:\ProgramData\OneDriveSvc\OneDriveSvc.exe
```

The attackers used the monitoring software to execute commands remotely, transfer files, and monitor system activity in real time.

Researchers also observed the attackers disabling Windows Defender by attempting to stop and delete associated services.

![Disabling Windows Defender](https://www.bleepstatic.com/images/news/security/n/netmonitor-abuse-crazy-ransomware/disabling-defender.jpg)

**Disabling Windows Defender**  
_Source: Huntress_

In one incident, the hackers configured monitoring rules in SimpleHelp to alert them when devices accessed cryptocurrency wallets or were using remote management tools as they prepared for ransomware deployment and potential cryptocurrency theft.

"The logs show the agent continuously cycling through trigger and reset events for cryptocurrency-related keywords, including wallet services (metamask, exodus, wallet, blockchain), exchanges (binance, bybit, kucoin, bitrue, poloniex, bc.game, noones), blockchain explorers (etherscan, bscscan), and the payment platform payoneer," explains Huntress.

"Alongside these, the agent also monitored for remote access tool keywords, including RDP, anydesk, ultraview, teamview, and VNC, likely to detect if anyone was actively connecting to the machine."

**Keywords monitored by SimpleHelp agent**  
_Source: Huntress_

The use of multiple remote access tools provided redundancy for the attackers, ensuring they retained access even if one tool was discovered or removed.

While only one incident led to the deployment of Crazy ransomware, Huntress believes the same threat actor is behind both incidents.

"The same filename (vhost.exe) and overlapping C2 infrastructure were reused across both cases, strongly suggesting a single operator or group behind both intrusions," explains Huntress.

The use of legitimate remote management and monitoring tools has become increasingly [common in ransomware intrusions](https://www.bleepingcomputer.com/news/security/dragonforce-ransomware-abuses-simplehelp-in-msp-supply-chain-attack/), as these tools allow attackers to blend in with legitimate network traffic.

Huntress warns that organizations should closely monitor for unauthorized installations of remote monitoring and support tools.

Furthermore, as both breaches were enabled through compromised SSL VPN credentials, organizations need to enforce MFA on all remote access services used to access the network.