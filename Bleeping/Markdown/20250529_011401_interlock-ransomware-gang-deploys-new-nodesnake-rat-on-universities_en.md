# Interlock ransomware gang deploys new NodeSnake RAT on universities

![Snake](https://www.bleepstatic.com/content/hl-images/2024/07/11/snake.jpg)

The Interlock ransomware gang is deploying a previously undocumented remote access trojan (RAT) named NodeSnake against educational institutes for persistent access to corporate networks.

QuorumCyber researchers report seeing NodeSnake's deployment in at least two cases targeting universities in the UK in January and March 2025.

The two malware samples significantly differ, indicating active development to add new features and capabilities on NodeSnake.

As first reported by BleepingComputer, Interlock is a ransomware group [launched in September 2024](https://www.bleepingcomputer.com/news/security/meet-interlock-the-new-ransomware-targeting-freebsd-servers/). It has previously targeted the [Texas Tech University](https://www.bleepingcomputer.com/news/security/texas-tech-university-system-data-breach-impacts-14-million-patients/), the [DaVita](https://www.bleepingcomputer.com/news/security/interlock-ransomware-claims-davita-attack-leaks-stolen-data/) kidney dialysis firm, and the [Kettering Health](https://www.bleepingcomputer.com/news/security/kettering-health-hit-by-system-wide-outage-after-ransomware-attack/) medical network in Ohio.

The threat group has also been seen leveraging ['ClickFix' attacks](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/) that impersonate IT tools to achieve initial infection and network infiltration.

## The new NodeSnake RAT malware

Interlock's latest attacks on educational institutions start with phishing emails carrying malicious links or attachments that lead to NodeSnake RAT infections.

The JavaScript malware, which is executed with NodeJS, establishes persistence upon infection by using PowerShell or CMD scripts to write a deceptive Registry entry named 'ChromeUpdater' to impersonate Google Chrome's updater.

For evasion, the malware runs as a detached background process, filenames and payloads are assigned random names, and command-and-control (C2) addresses are cycled through with randomized delays.

Moreover, the malware features heavy code obfuscation, XOR encryption with a rolling key and random seeds, and performs console tampering to disrupt normal debug output.

Although the C2 IP address is hardcoded, the connection is routed through Cloudflare-proxied domains for obfuscation.

Once active on the infected machine, it collects key metadata about the user, running processes, services, and network configurations and exfiltrates it to the C2.

![Gathering system data](https://www.bleepstatic.com/images/news/u/1220909/2025/May/gatherdata.jpg)

**Gathering system data**  
_Source: QuorumCyber_

The malware can kill active processes or load additional EXE, DLL, or JavaScript payloads on the device.

The newer NodeSnake variant can also execute CMD commands and use additional modules to change C2 polling behavior dynamically. The command results are bundled in the exfiltrated data packs, allowing real-time shell interaction.

![CMD command execution](https://www.bleepstatic.com/images/news/u/1220909/2025/May/cmd.jpg)

**CMD command execution**  
_Source: QuorumCyber_

The existence of NodeSnake and its continuous development is an indication of Interlock's continued evolution and focus on long-term stealthy persistence.

The complete list of the indicators of compromise for this threat is available at the bottom of the [QuorumCyber report](https://www.quorumcyber.com/wp-content/uploads/2025/04/20250416-Higher-Education-Sector-RAT-MP.pdf).

Monitoring for these could help block ransomware attacks early on before Interlock proceeds to the data exfiltration and encryption phase.