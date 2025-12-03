# Marquis data breach impacts over 74 US banks, credit unions

![Marquis](https://www.bleepstatic.com/content/hl-images/2025/12/03/marquis.png)

Financial software provider Marquis Software Solutions is warning that it suffered a data breach that impacted dozens of banks and credit unions across the US.

Marquis Software Solutions provides data analytics, CRM tools, compliance reporting, and digital marketing services to over 700 banks, credit unions, and mortgage lenders.

In data breach notifications filed with US Attorney General offices, Marquis says it suffered a ransomware attack on August 14, 2025, after its network was breached through its SonicWall firewall.

This allowed the hackers to steal "certain files from its systems" during the attack.

"The review determined that the files contained personal information received from certain business customers," reads a notification filed with Maine's AG office.

"The personal information potentially involved for Maine residents includes names, addresses, phone numbers, Social Security numbers, Taxpayer Identification Numbers, financial account information without security or access codes, and dates of birth."

Marquis is now filing notifications on behalf of its customers, in some cases breaking down the number of people impacted per bank in a state. These notifications state that similar data was exposed in the attack for customers in other U.S. states.

According to notifications filed in [Maine](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/d8efd2f6-f52d-49d3-be53-028e9a8cb837.html), [Iowa](https://www.iowaattorneygeneral.gov/media/cms/11262025%5FMarquis%5FSoftware%5FSolutions%5FC797355999F87.pdf), and Texas, over 400,000 customers have been impacted from the following 74 banks and credit unions.

| 1st Northern California Credit Union       | Abbott Laboratories Employees Credit Union | Advantage Federal Credit Union               |
| ------------------------------------------ | ------------------------------------------ | -------------------------------------------- |
| Agriculture Federal Credit Union           | Alltrust Credit Union                      | BayFirst National Bank                       |
| Bellwether Community Credit Union          | C&N Bank                                   | Cape Cod Five                                |
| Capital City Bank Group                    | Central Virginia Federal Credit Union      | Clark County Credit Union                    |
| Community 1st Credit Union                 | Community Bancshares of Mississippi, Inc.  | Cornerstone Community Financial Credit Union |
| CPM Federal Credit Union                   | CSE Federal Credit Union                   | CU Hawaii Federal Credit Union               |
| d/b/a Community Bank                       | Discovery Federal Credit Union             | Earthmover Credit Union                      |
| Educators Credit Union                     | Energy Capital Credit Union                | Fidelity Cooperative Bank                    |
| First Community Credit Union               | First Northern Bank of Dixon               | Florida Credit Union                         |
| Fort Community Credit Union                | Founders Federal Credit Union              | Freedom of Maryland Federal Credit Union     |
| Gateway First Bank                         | Generations Federal Credit Union           | Gesa Credit Union                            |
| Glendale Federal Credit Union              | Hope Federal Credit Union                  | IBERIABANK n/k/a First Horizon Bank          |
| Industrial Federal Credit Union            | Interior Federal                           | Interior Federal Credit Union                |
| Interra Credit Union                       | Jonestown Bank & Trust Co.                 | Kemba Financial Credit Union                 |
| Liberty First Credit Union                 | Maine State Credit Union                   | Market USA FCU                               |
| MemberSource Credit Union                  | Michigan First Credit Union                | MIT Federal Credit Union                     |
| New Orleans Firemen's Federal Credit Union | New Peoples Bank                           | Newburyport Five Cents Savings Bank          |
| NIH Federal Credit Union                   | Pasadena Federal Credit Union              | Pathways Financial Credit Union              |
| Peake Federal Credit Union                 | Pelican Credit Union                       | Pentucket Bank                               |
| PFCU Credit Union                          | QNB Bank                                   | Security Credit Union                        |
| Seneca Savings                             | ServU Credit Union                         | StonehamBank Cooperative                     |
| Suncoast Credit Union                      | Texoma Community Credit Union              | Thomaston Savings Bank                       |
| Time Bank                                  | TowneBank                                  | Ulster Savings Bank                          |
| University Credit Union                    | Valley Strong Credit Union                 | Westerra Credit Union                        |
| Whitefish Credit Union                     | Zing Credit Union                          |                                              |

At this time, Marquis says that there is no evidence that data has been misused or published anywhere.

However, as previously reported by [Comparitech](https://www.comparitech.com/news/software-vendor-serving-700-banks-hacked-credit-union-says/), a now-deleted filing by Community 1st credit union claimed that Marquis paid a ransomm, which is done to prevent the leaking and abuse of stolen data.

"Marquis paid a ransomware shortly after 08/14/25\. On 10/27/25 C1st was notified that nonpublic personal information related to C1st members was included in the Marquis breach," reads the deleted notification seen by Comparitech.

While the company's data breach notifications state only that it has "taken steps to reduce the risk of this type of incident," a filing by [CoVantage Credit Union](https://mm.nh.gov/files/uploads/doj/remote-docs/covantage-credit-union-marquis-software-solutions-20251126.pdf) with the New Hampshire AG shares further details about how the company is increasing security.

This notification states that Marquis has now enhanced its security controls by doing the following:

* Ensuring that all firewall devices are fully patched and up to date,
* Rotating passwords for local accounts,
* Deleting old or unused accounts,
* Ensuring that multi-factor authentication is enabled for all firewall and virtual private network ("VPN") accounts,
* Increasing logging retention for firewall devices, (
* Applying account lock-out policies at the VPN for too many failed logins,
* Applying geo-IP filtering to only allow connections from specific countries needed for business operations, and
* Applying policies to automatically block connections to/from known Botnet Command and Control servers at the firewall.

These steps indicate that the threat actors likely gained access to the company network through a SonicWall VPN account, a known tactic used by some ransomware gangs, especially Akira ransomware.

## Targeting SonicWall firewalls

While Marquis has not shared any further details about the ransomware attack, the Akira ransomware gang has been targeting SonicWall firewalls to gain initial access to corporate networks since at least early September 2024.

Akira started breaching SonicWall SSL VPN devices in 2024 by [exploiting the CVE-2024-40766 vulnerability](https://www.bleepingcomputer.com/news/security/critical-sonicwall-sslvpn-bug-exploited-in-ransomware-attacks/), which allowed attackers to steal VPN usernames, passwords, and seeds to generate one-time passcodes.

Even after SonicWall patched the bug, many organizations didn't properly reset their VPN credentials, allowing Akira to [continue breaching patched devices](https://www.bleepingcomputer.com/news/security/akira-ransomware-exploiting-critical-sonicwall-sslvpn-bug-again/) with previously stolen credentials.

A recent report shows the group is still signing in to SonicWall VPN accounts [even when MFA is enabled](https://www.bleepingcomputer.com/news/security/akira-ransomware-breaching-mfa-protected-sonicwall-vpn-accounts/), suggesting the attackers stole OTP seeds during the earlier exploitation.

Once Akira gets in through the VPN, they move quickly to scan the network, perform reconnaissance, gain elevated privileges in the Windows Active Directory, and steal data before deploying ransomware.