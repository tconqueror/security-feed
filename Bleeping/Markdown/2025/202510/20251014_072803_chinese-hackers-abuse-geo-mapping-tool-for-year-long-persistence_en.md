# Chinese hackers abuse geo-mapping tool for year-long persistence

![Chinese hackers abuse geo-mapping tool for year-long persistence](https://www.bleepstatic.com/content/hl-images/2025/05/28/China.jpg)

Chinese state hackers remained undetected in a target environment for more than a year by turning a component in the ArcGIS geo-mapping tool into a web shell.

The ArcGIS geographic information system (GIS) is developed by Esri (Environmental Systems Research Institute) and has support for server object extensions (SOE) that can extend the basic functionality.

The software is used by municipalities, utilities, and infrastructure operators to collect, analyze, visualize, and manage spatial and geographic data through maps.

Researchers at cybersecurity company ReliaQuest are confident that the threat actor is a Chinese APT group and have moderate confidence that it is Flax Typhoon.

In a report shared with BleepingComputer, they say that the hackers used valid administrator credentials to log into a public-facing ArcGIS server that was linked to a private, internal ArcGIS server.

The attacker used their access to upload a malicious Java SOE acting as a web shell that accepted base64-encoded commands through a REST API parameter (layer) and executed them on the internal ArcGIS server, where they appeared as routine operations.

The exchange was protected by a hardcoded secret key, ensuring that only the attackers had access to this backdoor.

## From ArcGIS to SoftEther VPN

To establish persistence and extend their capabilities beyond the ArcGIS portal, Flax Typhoon used the malicious SOE to download and install SoftEther VPN Bridge, and registered it as a Windows service that started automatically when the system booted.

Once launched, it established an outbound HTTPS tunnel to the attacker's server at 172.86.113\[.\]142, linking the victim's internal network to the threat actor's machine.

The VPN used normal HTTPS traffic on port 443, blending with legitimate traffic, and even if the SOE was detected and deleted, the VPN service would still be active.

Leveraging the VPN connection, the attacker could scan the local network, move laterally, access internal hosts, dump credentials, or exfiltrate data, without relying on the web shell for this activity.

ReliaQuest [observed](http://reliaquest.com/blog/threat-spotlight-inside-flax-typhoons-arcgis-compromise) suspicious actions targeting two workstations belonging to the target organization's IT staff, as the hacker tried to dump the Security Account Manager (SAM) database, security registry keys, and LSA secrets.

"These were clear "hands-on keyboard" attempts to escalate privileges and gain the credentials needed to deepen their foothold in the network," the researchers say.

"A particularly noteworthy observation was a file "pass.txt.lnk" being written to disk and accessed, suggesting active credential harvesting likely to move laterally within the Active Directory (AD) environment and compromise additional systems" - [ReliaQuest](http://reliaquest.com/blog/threat-spotlight-inside-flax-typhoons-arcgis-compromise)

Flax Typhoon, notorious for targeting government, critical infrastructure, and IT organizations, has been using evasion tactics like ["living off the land" binaries](https://www.bleepingcomputer.com/news/security/microsoft-stealthy-flax-typhoon-hackers-use-lolbins-to-evade-detection/) for a while now, but SOE is a novel method.

The threat group is known for espionage campaigns for establishing long-term, stealthy access through legitimate software.

[The FBI linked](https://www.bleepingcomputer.com/news/security/flax-typhoon-hackers-infect-260-000-routers-ip-cameras-with-botnet-malware/) the Flax Typhoon to the massive "Raptor Train" botnet, which impacted the U.S., and, earlier this year, the Treasury's Office of Foreign Assets Control (OFAC) [sanctioned](https://www.bleepingcomputer.com/news/security/us-sanctions-chinese-company-linked-to-flax-typhoon-hackers/) companies that supported the state-sponsored hackers.

Ersi confirmed that this is the first time they have seen an SOE being used this way. The developer says that it will update their documentation to warn users of the risk of malicious SOEs.