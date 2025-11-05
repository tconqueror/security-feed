# SonicWall says state-sponsored hackers behind security breach in September

![SonicWall says state-sponsored hackers behind security breach in September](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall.jpeg)

SonicWall's investigation into the September security breach that exposed customers' firewall configuration backup files concludes that state-sponsored hackers were behind the attack.

The network security company says that incident responders from Mandiant confirmed that the malicious activity had no impact on SonicWall's products, firmware, systems, tools, source code, or customer networks.

“The Mandiant investigation is now complete. Their findings confirm that the malicious activity – carried out by a state-sponsored threat actor - was isolated to the unauthorized access of cloud backup files from a specific cloud environment using an API call,” [SonicWall states](https://www.sonicwall.com/blog/cloud-backup-security-incident-investigation-complete-and-strengthened-cyber-resilience).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

“The incident did not impact SonicWall products or firmware. No other SonicWall systems or tools, source code, or customer networks were disrupted or compromised,” the vendor says.

On September 17, the American company [disclosed](https://www.bleepingcomputer.com/news/security/sonicwall-warns-customers-to-reset-credentials-after-MySonicWall-breach/) "an incident that exposed firewall configuration backup files stored in certain MySonicWall accounts."

An attacker could extract from these files sensitive information, like access credentials and tokens, that could make it "significantly easier" for them to exploit a customer's firewalls.

The company immediately advised customers to reset their MySonicWall account credentials, temporary access codes, passwords for LDAP, RADIUS, or TACACS+ servers, passwords for L2TP/PPPoE/PPTP WAN interfaces, and shared secrets in IPSec site-to-site and GroupVPN policies.

In an [update on October 9](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-configs-stolen-for-all-cloud-backup-customers/), SonicWall stated that the security breach affected all customers who used the company’s cloud backup service to store firewall configuration files.

The investigation is now complete,, and the network security vendor states that the breach was contained to a specific part of its environment and did not impact the safety of its products.

Furthermore, the company assured that the investigated nation-state activity has no connection with attacks from [the Akira ransomware](https://www.bleepingcomputer.com/news/security/akira-ransomware-breaching-mfa-protected-sonicwall-vpn-accounts/) gang that targeted MFA-protected SonicWall VPN accounts in late September.

More recently, on October 13, [Huntress reported](https://www.bleepingcomputer.com/news/security/sonicwall-vpn-accounts-breached-using-stolen-creds-in-widespread-attacks/) seeing elevated malicious activity targeting SonicWall SSLVPN accounts and successfully compromising over a hundred of them using valid credentials.

Huntress did not find any evidence connecting these attacks to the September firewall configuration files exposure, and SonicWall did not respond to our requests regarding the matter.