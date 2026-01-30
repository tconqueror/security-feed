# Marquis blames ransomware breach on SonicWall cloud backup hack

![Marquis](https://www.bleepstatic.com/content/hl-images/2026/01/29/Marquis.jpg)

Marquis Software Solutions, a Texas-based financial services provider, is blaming a ransomware attack that impacted its systems and affected dozens of U.S. banks and credit unions in August 2025 on a security breach reported by SonicWall a month later.

The software company provides data analytics, compliance reporting, CRM tools, and digital marketing services to more than 700 banks, credit unions, and mortgage lenders across the United States.

In statements to customers earlier this week seen by BleepingComputer, Marquis says the ransomware operators didn't breach its systems by exploiting an unpatched SonicWall firewall, as previously believed.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Instead, the attackers used information obtained from firewall configuration backup files stolen after gaining unauthorized access to SonicWall's MySonicWall online customer portal.

"Based on the ongoing third-party investigation, we have determined that the threat actor that attacked Marquis was able to circumvent our firewall by leveraging the configuration data extracted from the service provider's cloud backup breach," Marquis said.

"At this time, Marquis is evaluating its options with respect to the firewall provider, including to seek recoupment of any expenses spent by Marquis and its customers in responding to the data incident."

![Marquis statement](https://www.bleepstatic.com/images/news/u/1109292/2026/Marquis-statement.png)

_Marquis statement (BleepingComputer)_

SonicWall disclosed the security breach mentioned by Marquis on September 17, when it warned customers to [reset their MySonicWall account credentials](https://www.bleepingcomputer.com/news/security/sonicwall-warns-customers-to-reset-credentials-after-MySonicWall-breach/) and said the incident affected only about 5% of its firewall customers using its cloud backup service.

The company also warned that threat actors could extract access credentials and tokens, making it "[significantly easier](https://community.sonicwall.com/s/question/0D5VN00000nrJEz0AM/mysonicwall-cloud-backup-potentially-exposed#:~:text=significantly%20easier)" to compromise affected customers' firewalls. However, roughly three weeks later, SonicWall issued an update confirming that [all customers using its cloud backup service were affected](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-configs-stolen-for-all-cloud-backup-customers/) by the September breach.

One month later, it published another update stating that a Mandiant investigation into the September attack found evidence [linking the incident to state-sponsored hackers](https://www.bleepingcomputer.com/news/security/sonicwall-says-state-sponsored-hackers-behind-security-breach-in-september/). 

SonicWall added that the MySonicWall breach was unrelated to attacks by [the Akira ransomware](https://www.bleepingcomputer.com/news/security/akira-ransomware-breaching-mfa-protected-sonicwall-vpn-accounts/) gang that targeted MFA-protected SonicWall VPN accounts in late September.

[Cybersecurity company Huntress reported](https://www.bleepingcomputer.com/news/security/sonicwall-vpn-accounts-breached-using-stolen-creds-in-widespread-attacks/) on October 13 that it had observed threat actors compromising over 100 SonicWall SSLVPN accounts in a large-scale campaign using stolen, valid credentials. However, Huntress found no evidence linking these attacks to the SonicWall cloud backup hack, and SonicWall did not respond to BleepingComputer's requests for comment at the time.

BleepingComputer reached out again earlier this week, but a SonicWall spokesperson has yet to reply.