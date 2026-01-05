# NordVPN denies breach claims, says attackers have "dummy data"

![NordVPN](https://www.bleepstatic.com/content/hl-images/2026/01/05/nordvpn.jpg)

NordVPN denied allegations that its internal Salesforce development servers were breached, saying that cybercriminals obtained "dummy data" from a trial account on a third-party automated testing platform.

The company's statement comes after a threat actor (using the 1011 handle) claimed on a hacking forum over the weekend that they stole more than 10 databases containing sensitive information like Salesforce API keys and Jira tokens, following a brute-force attack against a NordVPN development server.

"Today i am leaking +10 DB's source codes from a nordvpn development server. This information was acquired by bruteforcing a misconfigured server of Nordypn, which has salesforce and jira information stored. Compromissed information: SalesForce api keys, jira tokens and more," the threat actor said.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

However, as NordVPN revealed today, this is actually test data stolen from a temporary test environment deployed months earlier during trial testing a potential vendor for automated testing.

The Lithuanian VPN service added that the test environment had no connection with its own infrastructure and that the stolen data doesn't include sensitive customer or business information.

![NordVPN breach claims](https://www.bleepstatic.com/images/news/u/1109292/2026/NordVPN-breach_claims.jpg)

_NordVPN breach claims (BleepingComputer)_

​"The leaked elements, such as the specific API tables and database schemas can only be artifacts of an isolated third-party test environment, containing only dummy data used for functionality checks. While no data in the dump points to NordVPN, we have contacted the vendor for additional information," [NordVPN explained](https://nordvpn.com/blog/addressing-alleged-salesforce-breach/).

"Because this was a preliminary test and no contract was ever signed, no real customer data, production source code, or active sensitive credentials were ever uploaded to this environment.

"We ultimately chose a different vendor and did not proceed with the one we tested. The environment in question was never connected to our production systems."

While this was only a false alarm, in 2019, hackers [breached the servers of NordVPN and TorGuard](https://www.bleepingcomputer.com/news/security/hacker-breached-servers-belonging-to-multiple-vpn-providers/), gaining full root access and stealing private keys used to secure their web servers and VPN configurations.

In response to the 2019 incident, [NordVPN introduced](https://www.bleepingcomputer.com/news/security/nordvpn-plans-security-and-privacy-upgrades-after-hack/) a bug bounty program and hired outside cybersecurity experts for a "full-scale" third-party security audit.

The company also announced plans to switch to dedicated servers that they own exclusively and to upgrade their entire 5,100-server infrastructure to RAM servers.