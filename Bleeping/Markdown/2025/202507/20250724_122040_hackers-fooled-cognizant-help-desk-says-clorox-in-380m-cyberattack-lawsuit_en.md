# Hackers fooled Cognizant help desk, says Clorox in $380M cyberattack lawsuit

![Clorox](https://www.bleepstatic.com/content/hl-images/2024/02/03/clorox-shelf.jpg)

Clorox is suing IT giant Cognizant for gross negligence, alleging it enabled a massive August 2023 cyberattack by resetting an employee's password for a hacker without first verifying their identity.

The incident was first made public in September 2023, reportedly carried out by hackers associated with Scattered Spider, who utilized a social engineering attack to breach the company.

The lawsuit says Cognizant provided IT services to Clorox, including service desk support and identity management, which was the point of compromise that led to a [devastating and costly cyberattack](https://www.bleepingcomputer.com/news/security/clorox-says-cyberattack-caused-49-million-in-expenses/) for the company.

Clorox is a major consumer goods company, best known for household cleaning products, bleach, disinfectants, and personal care items. Cognizant is a global IT services and consulting company, providing cloud services, software development, and cybersecurity.

According to the complaint, from 2013 to 2023, Cognizant was contracted by Clorox to handle its IT operations.

"Cognizant provided the service desk ("Service Desk") that Clorox employees could contact when they needed password recovery or reset assistance," reads the complaint shared with BleepingComputer.

"Cognizant's operation of the Service Desk came with a simple, common-sense requirement: never reset anyone's credentials without properly authenticating them first. Clorox made this easy for Cognizant by providing them with straight-forward procedures to follow whenever providing credential recovery or reset assistance."

However, the complaint alleges that on August 11, 2023, recordings show that a cybercriminal called Cognizant's Service Desk multiple times, pretending to be a Clorox representative requesting password and multi-factor authentication resets.

"At no point during any of the calls did the Agent verify that the caller was in fact Employee 1. At no point did the Agent follow Clorox's credential support procedures—either the pre-2023 procedure or the January 2023 update—before changing the password for the cybercriminal. The Agent further reset Employee 1's MFA credentials multiple times without any identity verification at all. And at no point did the Agent send the required emails to the employee or the employee's manager to alert them of the password reset," Clorox claims in the complaint.

This type of social engineering attack has become the hallmark of Scattered Spider attacks, recently used in UK retail attacks on [Marks & Spencer](https://www.bleepingcomputer.com/news/security/mands-confirms-social-engineering-led-to-massive-ransomware-attack/) and [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/).

After allegedly failing to verify the caller's actual identity, Cognizant reset the credentials and multi-factor authentication (MFA) for the hacker, granting them access to Clorox's IT network.

To make matters worse, Clorox alleges that the threat actors used the same playbook to reset the password and MFA for another employee who worked in IT security, which was done without verification once again. This reportedly gave the attackers privileged access to the network, which they used to spread to further devices.

![Transcript of call between hacker and service desk](https://www.bleepstatic.com/images/news/security/c/cognizant/clorox-lawsuit/clorox-employee-2-transcript.jpg)

**Transcript of call between hacker and service desk**  
_Source: Clorox complaint against Cognizant_

Clorox states that Cognizant's actions paralyzed its corporate network, halted manufacturing, and caused widespread product shortages and business interruption.

In addition to this, Clorox described Cognizant's response and recovery support as overly incompetent, resulting in delays in the application of containment measures, failure to shut down compromised accounts, and sending underqualified personnel on premises.

"The resulting Cyberattack was debilitating. It paralyzed Clorox's corporate network and crippled business operations," [describes the legal complaint](https://www.documentcloud.org/documents/26025981-07-22-redacted-clorox-complaint/).

"And to make matters worse, when Clorox called on Cognizant to provide incident response and disaster recovery support services, Cognizant botched its response and compounded the damage it had already caused."

Clorox's complaint alleges breach of contract due to Cognizant's failure to meet ITSA obligations, breach of good faith and fair dealing, gross negligence, and intentional misrepresentation of staff training on the client's credential reset procedures.

For these actions, which resulted in hundreds of millions of dollars in lost sales due to business disruption, as well as reputational damage with long-term consequences, Clorox is seeking $49 million in direct remediation damages and $380,000,000 in total damages.

BleepingComputer attempted to contact Cognizant for a comment on the lawsuit, but the listed press address was returned with a delivery failure.