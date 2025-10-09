# Hacktivists target critical infrastructure, hit decoy plant

![Pro-Russian hacktivists target fake water treatment systems](https://www.bleepstatic.com/content/hl-images/2023/01/18/Russian__hacker.jpg)

A pro-Russian hacktivist group called TwoNet pivoted in less than a year from launching distributed denial-of-service (DDoS) attacks to targeting critical infrastructure.

Recently, the threat actor claimed an attack on a water treatment facility that turned out to be a realistic honeypot system set up by threat researchers specifically to observe adversaries’ movements.

The compromise at the decoy facility occurred in September and revealed that the threat actor moved from initial access to disruptive action in about 26 hours.

### Decoy plant but real threat

Researchers at Forescout, a company providing cybersecurity solutions for enterprise IT and industrial networks, monitoring TwoNet’s activity in the fake water treatment plant, noticed the hackers trying default credentials and gaining initial access at 8:22 AM.

During the first day, the hacktivist group attempted to enumerate the databases on the system; they succeeded in a second attempt, after using the correct set of SQL queries for the system.

The attacker proceeded to create a new user account called Barlati and announced their intrusion by exploiting an old stored cross-site-scripting (XSS) vulnerability tracked as CVE-2021-26829.

They leveraged the security issue to trigger a pop-up alert on the human machine interface (HMI) that displayed the message “Hacked by Barlati.”

However, they engaged in more damaging actions to disrupt processes and disable logs and alarms.

Forescout researchers say that TwoNet, unaware of breaching a decoy system, disabled the real-time updates by removing the connected programmable logic controllers (PLCs) from the data source list, and changed the PLC setpoints in the HMI.

“The attacker did not attempt privilege escalation or exploitation of the underlying host, focusing exclusively on the web application layer of the HMI,” - [Forescout](https://www.forescout.com/blog/anatomy-of-a-hacktivist-attack-russian-aligned-group-targets-otics/)

The following day, at 11:19 AM, Forescout researchers logged the intruder's last login.

While TwoNet started initially as another pro-Russian hacktivist group focused on launching DDoS attacks against entities showing support for Ukraine, the gang appears to be engaged in various cyber activities.

On the attacker’s Telegram channel, Forescout found that TwoNet tried to target HMI or SCADA interfaces of critical infrastructure organizations in “enemy countries.”

The gang also published personal details of intelligence and police personnel, commercial offerings for cybercrime services like ransomware-as-a-service (RaaS), hacker-for-hire, or for initial access to SCADA systems in Poland.

“This pattern mirrors other groups that have shifted from 'traditional' DDoS/defacement into OT/ICS operations,” Forescout researchers say.

To reduce the risk of a breach, Forescout recommends organizations in the critical infrastructure sector to make sure that systems have strong authentication and are not exposed to the public web.

Properly segmenting the production network, combined with IP-based access control lists for admin interface access, can keep threat actors at bay if they breach the corporate network.

Forescout also recommends using protocol-aware detection that alerts on exploitation attempts and changes in the HMI.