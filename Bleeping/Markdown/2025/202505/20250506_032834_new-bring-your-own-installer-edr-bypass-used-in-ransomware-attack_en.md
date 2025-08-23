# New "Bring Your Own Installer" EDR bypass used in ransomware attack

![Hacker with arms raised](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

A new "Bring Your Own Installer" EDR bypass technique is exploited in attacks to bypass SentinelOne's tamper protection feature, allowing threat actors to disable endpoint detection and response (EDR) agents to install the Babuk ransomware.

This technique exploits a gap in the agent upgrade process that allows the threat actors to terminate running EDR agents, leaving devices unprotected.

The attack was discovered by John Ailes and Tim Mashni of Aon's Stroz Friedberg Incident Response team during an engagement with a customer who suffered a ransomware attack earlier this year.

The technique does not rely on third-party tools or drivers like we normally see with EDR bypasses but instead abuses the SentinelOne installer itself.

SentinelOne recommends customers enable the "Online Authorization" setting, which is turned off by default, to mitigate this attack.

"We want to get the word out to ensure SentinelOne's customers know to enable Local Upgrade protection," John Ailes, Manager, Aon's Stroz Friedberg DFIR, told BleepingComputer.

"We've investigated environments with SentinelOne since their guidance was sent to customers and have seen clients that still don't have it enabled. At the end of the day, getting the word out to mitigate this bypass is the most important thing."

## Actively exploited in ransomware attacks

The Stroz Friedberg researchers explain that SentinelOne protects its EDR agent with an anti-tamper protection feature that requires a manual action in the SentinelOne management console or a unique code to remove an agent.

However, like many other software installers, when installing a different version of the agent, the SentinelOne installer terminates any associated Windows processes just before existing files are overwritten with the new version.

Threat actors discovered they could exploit this small window of opportunity by running a legitimate SentinelOne installer and then forcefully terminating the install process after it shuts down the running agent's services, leaving devices unprotected.

![Bring Your Own Installer EDR bypass attack chain](https://www.bleepstatic.com/images/news/security/b/bring-your-own-installer-edr-bypass/Bring-Your-Own-Installer-EDR-Bypass-attack-flow.png)

**Bring Your Own Installer EDR bypass attack chain**  
_Source: Stroz Friedberg_

Earlier this year, Stroz Friedberg was engaged to investigate an attack on a customer's network, with logs showing that the attackers gained administrative access to the customer's network through a vulnerability.

The attackers then used this new bypass by terminating the SentinelOne Windows Installer ("`msiexec.exe`") process before it could install and launch the new version of the agent. With protections disabled on the device, the threat actors were then able to deploy the ransomware.

In a conversation with BleepingComputer, Ailes said that threat actors can utilize new or older versions of the agent to conduct this attack, so even if the latest version runs on devices, they are still vulnerable.

"Stroz Friedberg also observed that the host went offline in the SentinelOne management console shortly after the installer was terminated," warns [Stroz Friedberg's report](https://www.aon.com/en/insights/cyber-labs/bring-your-own-installer-bypassing-sentinelone).

"Further testing showed that the attack was successful across multiple versions of the SentinelOne agent and was not dependent on the specific versions observed in this incident."

Stroz Friedberg responsibly disclosed this attack to SentinelOne, who privately shared mitigations with customers in January 2025.

The mitigation is to enable the "Online Authorization" feature in the Sentinel Policy settings that, when enabled, requires approval from the SentinelOne management console before local upgrades, downgrades, or uninstalls of the agent can occur.

SentinelOne also shared Stroz Friedberg's advisory on this new technique with all other major EDR vendors, in case they were also affected.

Palo Alto Networks confirmed to Stroz Friedberg that this attack did not impact its EDR software.