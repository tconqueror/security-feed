# Canada’s House of Commons investigating data breach after cyberattack

![Canada flag](https://www.bleepstatic.com/content/hl-images/2023/11/20/0_Canada_flag.jpg)

The House of Commons of Canada is currently investigating a data breach after a threat actor reportedly stole employee information in a cyberattack on Friday.

While the lower house of the Parliament of Canada has yet to issue a public statement regarding this incident, [CBC News reports](https://www.cbc.ca/news/politics/house-of-commons-data-breach-1.7608061) that House of Commons staff were notified of a breach on Monday via email.

The alert states that the attacker exploited a recent Microsoft vulnerability to gain access to a database containing sensitive information used to manage House of Commons computers and mobile devices. During the breach, the threat actor also stole some employee data that isn't publicly available, including their names, job titles, office locations, and email addresses.

Employees and House of Commons members were also urged to be aware of potential fraudulent attempts to use the information stolen during the attack, which could be used to target and impersonate parliamentarians or exploited in scams.

The House of Commons is now collaborating with the country's Communications Security Establishment (CSE), the national security agency, to investigate the impact of the attack.

CSE told CBC News that it couldn't yet confirm who was behind the attack, saying that "attribution of a cyber incident is difficult."

"Investigating cyber threat activity takes resources and time, and there are many considerations involved in the process of attributing malicious cyber activity," said the CSE.

A spokesperson with Canada's Communications Security Establishment (CSE) was unable to provide a statement immediately when contacted by BleepingComputer earlier today.

## Recently patched Microsoft vulnerabilities

While the House of Commons and CSE didn't disclose the specific Microsoft vulnerability exploited in the breach, the Canadian Centre for Cyber Security recently warned IT professionals across Canada to secure their systems against two Microsoft security bugs: a [Microsoft SharePoint Server flaw](https://www.cyber.gc.ca/en/alerts-advisories/al25-009-vulnerability-impacting-microsoft-sharepoint-server-cve-2025-53770) (tracked as CVE-2025-53770 and dubbed ToolShell) and a [Microsoft Exchange vulnerability](https://www.cyber.gc.ca/en/alerts-advisories/microsoft-exchange-security-advisory-av25-490) (CVE-2025-53786).

The former has been under active and widespread exploitation by various threat groups in zero-day attacks since early July, including [Chinese state-backed hacking groups](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-toolshell-attacks-linked-to-chinese-hackers/) and [ransomware gangs](https://www.bleepingcomputer.com/news/security/ransomware-gangs-join-attacks-targeting-microsoft-sharepoint-servers/).

Attackers have used CVE-2025-53770 exploits to breach [numerous high-profile targets,](https://www.bleepingcomputer.com/news/security/us-nuclear-weapons-agency-hacked-in-microsoft-sharepoint-attacks/) including the U.S. National Nuclear Security Administration, the Department of Education, Florida's Department of Revenue, the Rhode Island General Assembly, and government networks in Europe and the Middle East.

The CVE-2025-53786 high-severity Microsoft Exchange flaw, which can allow attackers to move laterally in Microsoft cloud environments, is [the subject of an emergency directive](https://www.bleepingcomputer.com/news/security/cisa-orders-fed-agencies-to-patch-new-cve-2025-53786-exchange-flaw/) issued by the U.S. Cybersecurity and Infrastructure Security Agency (CISA) last Thursday.

The cybersecurity ordered all non-military agencies within the U.S. executive branch to mitigate this vulnerability over the weekend, and it also warned that failure to secure their systems in time could lead "to a hybrid cloud and on-premises total domain compromise."

On Monday, security threat monitoring platform Shadowserver also reported that over 29,000 Exchange servers exposed online [remain unpatched against CVE-2025-53786](https://www.bleepingcomputer.com/news/security/over-29-000-exchange-servers-unpatched-against-high-severity-flaw/), with more than 800 IP addresses identified in Canada.