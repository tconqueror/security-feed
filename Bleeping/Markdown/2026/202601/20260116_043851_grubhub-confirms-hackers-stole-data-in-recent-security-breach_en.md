# Grubhub confirms hackers stole data in recent security breach

![GrubHub](https://www.bleepstatic.com/content/hl-images/2025/02/04/GrubHub.jpg)

**_Exclusive:_** Food delivery platform Grubhub has confirmed a recent data breach after hackers accessed its systems, with sources telling BleepingComputer the company is now facing extortion demands.

"We're aware of unauthorized individuals who recently downloaded data from certain Grubhub systems," Grubhub told BleepingComputer.

"We quickly investigated, stopped the activity, and are taking steps to further increase our security posture. Sensitive information, such as financial information or order history, was not affected."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Grubhub would not respond to any further questions regarding the breach, including when it occurred, whether customer data was involved, or if they were being extorted.

However, the company confirmed that it is working with a third-party cybersecurity firm and has notified law enforcement.

Last month, Grubhub was also linked to a wave of scam emails sent from its `b.grubhub.com` subdomain that promoted a cryptocurrency scam promising a tenfold return on Bitcoin payments.

Grubhub said at the time that it contained the issue and took steps to prevent further unauthorized messages, but would not answer further questions related to the incident.

It is unclear if the two incidents are connected.

## Extorted by hackers

While Grubhub would not share further details, multiple sources have told BleepingComputer that the ShinyHunters cybercrime group is extorting the company.

BleepingComputer attempted to verify these claims with the threat actors, but they refused to comment.

According to sources, the threat actors are demanding a Bitcoin payment to prevent the release of older [Salesforce data from a February 2025 breach](https://www.bleepingcomputer.com/news/security/grubhub-data-breach-impacts-customers-drivers-and-merchants/) and newer Zendesk data that was stolen in the recent breach.

Grubhub uses Zendesk to power its online support chat system, which provides support for orders, account issues, and billing.

While it is unclear when the breach occurred, BleepingComputer was told that it was through secrets/credentials stolen in the recent [Salesloft Drift data theft attacks](http://breach.).

In August, threat actors used stolen OAuth tokens for Salesloft's Salesforce integration to conduct a data theft campaign between August 8 and August 18, 2025.

According to a report by Google's Threat Intelligence team (Mandiant), the stolen data was then used to harvest credentials and secrets to conduct follow-up attacks on other platforms.

"GTIG observed UNC6395 targeting sensitive credentials such as Amazon Web Services (AWS) access keys (AKIA), passwords, and Snowflake-related access tokens," [reports Google](https://cloud.google.com/blog/topics/threat-intelligence/data-theft-salesforce-instances-via-salesloft-drift?e=48754805).

ShinyHunters [claimed at the time to be behind the breach](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-15-billion-salesforce-records-stolen-in-drift-hacks/), stating they stole approximately 1.5 billion data records from the "[Account](https://help.salesforce.com/s/articleView?id=commerce.om%5Faccount%5Ffields.htm&type=5)", "[Contact](https://help.salesforce.com/s/articleView?id=commerce.om%5Fcontact%5Ffields.htm&language=en%5FUS&type=5)", "[Case](https://help.salesforce.com/s/articleView?id=sfdo.cm%5Fdata%5Fdictionary.htm&language=en%5FUS&type=5)", "[Opportunity](https://help.salesforce.com/s/articleView?id=sfdo.eda%5Fopportunity.htm&language=en%5FUS&type=5)", and "[User](https://help.salesforce.com/s/articleView?id=platform.user%5Ffields.htm&type=5&utm%5Fsource=chatgpt.com)" Salesforce object tables for 760 companies.

As threat actors continue to abuse previously stolen Salesforce data to carry out follow-on attacks, organizations impacted by the Salesloft Drift breaches must rotate all affected access tokens and secrets as soon as possible if they have not already done so.