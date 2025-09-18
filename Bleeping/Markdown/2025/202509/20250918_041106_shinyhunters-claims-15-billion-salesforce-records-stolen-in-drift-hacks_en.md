# ShinyHunters claims 1.5 billion Salesforce records stolen in Drift hacks

![Hand sifting data](https://www.bleepstatic.com/content/hl-images/2022/10/28/hand-sifting-data.jpg)

The ShinyHunters extortion group claims to have stolen over 1.5 billion Salesforce records from 760 companies using compromised Salesloft Drift OAuth tokens.

For the past year, the threat actors have been [targeting Salesforce customers in data theft attacks](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) using social engineering and malicious OAuth applications to breach Salesforce instances and download data. The stolen data is then used to extort companies into paying a ransom to prevent the data from being publicly leaked.

These attacks have been claimed by threat actors stating they are part of the ShinyHunters, Scattered Spider, and Lapsus$ extortion groups, now calling themselves "Scattered Lapsus$ Hunters." Google tracks this activity as UNC6040 and UNC6395.

In March, one of the threat actors [breached Salesloft's GitHub repository](https://www.bleepingcomputer.com/news/security/salesloft-march-github-repo-breach-led-to-salesforce-data-theft-attacks/), which contained the private source code for the company.

ShinyHunters told BleepingComputer that the threat actors used the [TruffleHog](https://github.com/trufflesecurity/trufflehog) security tool to scan the source code for secrets, which resulted in the finding of OAuth tokens for the Salesloft Drift and the Drift Email platforms.

Salesloft Drift is a third-party platform that connects the Drift AI chat agent with a Salesforce instance, allowing organizations to sync conversations, leads, and support cases into their CRM. Drift Email is used to manage email replies and organize CRM and marketing automation databases.

Using these stolen Drift OAuth tokens, ShinyHunters told BleepingComputer that the threat actors stole approximately 1.5 billion data records for 760 companies from the "[Account](https://help.salesforce.com/s/articleView?id=commerce.om%5Faccount%5Ffields.htm&type=5)", "[Contact](https://help.salesforce.com/s/articleView?id=commerce.om%5Fcontact%5Ffields.htm&language=en%5FUS&type=5)", "[Case](https://help.salesforce.com/s/articleView?id=sfdo.cm%5Fdata%5Fdictionary.htm&language=en%5FUS&type=5)", "[Opportunity](https://help.salesforce.com/s/articleView?id=sfdo.eda%5Fopportunity.htm&language=en%5FUS&type=5)", and "[User](https://help.salesforce.com/s/articleView?id=platform.user%5Ffields.htm&type=5&utm%5Fsource=chatgpt.com)" Salesforce object tables.

Of these records, approximately 250 million were from the Account, 579 million from Contact, 171 million from Opportunity, 60 million from User, and about 459 million records from the Case Salesforce tables.

The Case table was used to store information and text from support tickets submitted by customers of these companies, which, for tech companies, could include sensitive data.

As proof that they were behind the attack, the threat actor shared a text file listing the source code folders in the breached Salesloft GitHub repository.

BleepingComputer contacted Salesloft with questions about these record counts and the total number of companies impacted, but did not receive a response to our email. However, a source confirmed that the numbers are accurate.

Google Threat Intelligence (Mandiant) reported that the stolen Case data was analyzed for hidden secrets, such as credentials, authentication tokens, and access keys, to enable the attackers to pivot into other environments for further attacks.

"After the data was exfiltrated, the actor searched through the data to look for secrets that could be potentially used to compromise victim environments," [explained Google](https://cloud.google.com/blog/topics/threat-intelligence/data-theft-salesforce-instances-via-salesloft-drift?e=48754805).

"GTIG observed UNC6395 targeting sensitive credentials such as Amazon Web Services (AWS) access keys (AKIA), passwords, and Snowflake-related access tokens."

The stolen Drift and Drift Email tokens were used in large-scale data theft campaigns that hit major companies, including [Google](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/), [Cloudflare](https://www.bleepingcomputer.com/news/security/cloudflare-hit-by-data-breach-in-salesloft-drift-supply-chain-attack/), [Zscaler](https://www.bleepingcomputer.com/news/security/zscaler-data-breach-exposes-customer-info-after-salesloft-drift-compromise/), [Tenable](https://www.tenable.com/blog/tenable-response-to-salesforce-and-salesloft-drift-incident), [CyberArk](https://www.cyberark.com/resources/blog/salesloft-drift-incident-overview-and-cyberarks-response), [Elastic](https://www.elastic.co/blog/elastic-update-salesloft-drift-security-incident), [BeyondTrust](https://www.beyondtrust.com/trust-center/security-advisories/salesforce-salesloft-drift-security-incident), [Proofpoint](https://www.proofpoint.com/us/blog/corporate-news/salesloft-drift-supply-chain-incident-response), [JFrog](https://jfrog.com/help/r/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift), [Nutanix](https://www.nutanix.com/blog/third-party-salesloft-drift-application-incident-response-our-impact-and-action), [Qualys](https://blog.qualys.com/misc/2025/09/06/salesloft-drift-supply-chain-incident), [Rubrik](https://www.rubrik.com/blog/company/25/salesforce-connected-third-party-drift-application-supply-chain-incident-response), [Cato Networks](https://www.catonetworks.com/blog/cato-networks-statement-on-salesforce-salesloft-drift-incident/), [Palo Alto Networks](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/), and [many more](https://www.driftbreach.com/).

Due to the sheer volume of these attacks, the [FBI recently released an advisory](https://www.bleepingcomputer.com/news/security/fbi-warns-of-unc6040-unc6395-hackers-stealing-salesforce-data/) warning about the UNC6040 and UNC6395 threat actors, sharing IOCs discovered during the attacks.

Last Thursday, the threat actors claiming to be part of Scattered Spider stated that they planned to "go dark" and stop discussing operations on Telegram.

In a parting post, the threat actors claimed to have breached Google's Law Enforcement Request system (LERS), which is used by law enforcement to issue data requests, and the FBI eCheck platform, used for conducting background checks.

After contacting Google about these claims, the company confirmed that [a fraudulent account was added to its LERS platform](https://www.bleepingcomputer.com/news/security/google-confirms-fraudulent-account-created-in-law-enforcement-portal/).

"We have identified that a fraudulent account was created in our system for law enforcement requests and have disabled the account," Google told BleepingComputer.

"No requests were made with this fraudulent account, and no data was accessed."

While the threat actors indicated they are retiring, researchers from [ReliaQuest](https://reliaquest.com/blog/threat-spotlight-shinyhunters-data-breach-targets-salesforce-amid-scattered-spider-collaboration/) report that the threat actors began targeting financial institutions in July 2025 and are likely to continue conducting attacks.

To protect against these data theft attacks, [Salesforce recommends](https://www.salesforce.com/blog/protect-against-social-engineering/) that customers follow security best practices, including enabling multi-factor authentication (MFA), enforcing the principle of least privilege, and carefully managing connected applications.