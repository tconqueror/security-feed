# Match Group breach exposes data from Hinge, Tinder, OkCupid, and Match

![Match Group breach exposes data from Hinge, Tinder, OkCupid, and Match](https://www.bleepstatic.com/content/hl-images/2026/01/29/Match_Group.png)

Match Group, the owner of multiple popular online dating services, Tinder, Match.com, Meetic, OkCupid, and Hinge, confirmed a cybersecurity incident that compromised user data.

The company stated that hackers stole a "limited amount of user data" after the ShinyHunters threat group leaked 1.7 GB of compressed files allegedly containing 10 million records of Hinge, Match, and OkCupid user information, as well as internal documents.

In a statement to BleepingComputer, a spokesperson for Match Group confirmed the incident.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"We are aware of claims being made online related to a recently identified security incident," the company spokesperson said.

"Match Group takes the safety and security of our users seriously and acted quickly to terminate the unauthorized access."

![The Match Group data leak](https://www.bleepstatic.com/images/news/u/1220909/2026/January/shiny.jpg)

**The Match Group data leak**  
_Source: BleepingComputer_

The company said the investigation into the incident is in progress with the help of external experts, and that there is no indication that the hackers accessed user log-in credentials, financial information, or private communications.

"We believe the incident affects a limited amount of user data, and we are already in the process of notifying individuals, as appropriate," Match Group says.

Match Group is a giant in online dating, generating annual revenue of $3.5 billion, and the active user base across all its apps is estimated to be more than 80 million.

This latest incident is part of a new ShinyHunters voice phishing (vishing) campaign [targeting single sign-on (SSO) accounts](https://www.bleepingcomputer.com/news/security/shinyhunters-claim-to-be-behind-sso-account-data-theft-attacks/) at Okta, Microsoft, and Google across [over a hundred](https://www.silentpush.com/blog/slsh-alert/) high-value organizations, using links to supposedly internal login portals.

In the case of Match Group, BleepingComputer was told that the attacker stole data after compromising an Okta SSO account that gave them access to the company's AppsFlyer marketing analytics instance and Google Drive and Dropbox cloud storage accounts.

BleepingComputer has learned that the social engineering attack used the phishing domain at ‘matchinternal.com.’

The hackers said that the data contains personally identifiable information (PII), but not a lot of it. and that most of it consists of tracking information.

Companies can add defenses against attacks based on social-engineering by implementing solutions that are resistant to phishing attempts.

"While this is not the result of a security vulnerability in vendors’ products or infrastructure, we strongly recommend moving toward phishing-resistant MFA, such as FIDO2 security keys or passkeys where possible, as these protections are resistant to social engineering attacks in ways that push-based or SMS authentication are not," Charles Carmakal, Mandiant's Chief Technology Officer, says.

Furthermore, "administrators should also implement strict app authorization policies and monitor logs for anomalous API activity or unauthorized device enrollments."

In a post last week, Okta also recommends phishing resistance to prevent access to resources."When using Okta for workforce authentication, that would equate to enrolling users in Okta FastPass, passkeys or both for the sake of redundancy," [says Moussa Diallo](https://www.okta.com/en-gb/blog/threat-intelligence/phishing-kits-adapt-to-the-script-of-callers/), threat researcher at Okta Threat Intelligence.

"Social engineering actors can also be frustrated by setting network zones or tenant access control lists that deny access via the anonymizing services favoured by threat actors. The key is to know where your legitimate requests come from, and allowlist those networks,” Diallo said.

The researcher notes that there are some financial institutions, like [Monzo Bank](https://monzo.com/help/monzo-fraud-category/monzo-call-status-web) and the [Crypto exchange](https://crypto.com/eea/product-news/live-inapp-call-warning), currently testing live caller checks, where users can verify in the official mobile app from the company if an authorized representative is on the phone with them.