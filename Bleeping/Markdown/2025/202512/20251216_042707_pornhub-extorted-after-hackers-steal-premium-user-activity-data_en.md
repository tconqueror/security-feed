# PornHub extorted after hackers steal Premium member activity data

![PornHub](https://www.bleepstatic.com/content/hl-images/2025/06/05/PornHub.png)

Adult video platform PornHub is being extorted by the ShinyHunters extortion gang after the search and watch history of its Premium members was reportedly stolen in a recent Mixpanel data breach.

Last week, PornHub disclosed that it was impacted by a [recent breach at analytics vendor Mixpanel](https://www.bleepingcomputer.com/news/security/openai-discloses-api-customer-data-breach-via-mixpanel-vendor-hack/). Mixpanel suffered a breach on November 8th, 2025, after an SMS phishing (smishing) attack enabled threat actors to compromise its systems.

"A recent cybersecurity incident involving Mixpanel, a third-party data analytics provider, has impacted some Pornhub Premium users," reads a [PornHub security notice](https://help.pornhub.com/hc/en-us/articles/47334442459283-Important-Message-From-Pornhub) posted on Friday.

"Specifically, this situation affects only select Premium users. It is important to note this was not a breach of Pornhub Premium's systems. Passwords, payment details, and financial information remain secure and were not exposed."

PornHub says it has not worked with Mixpanel since 2021, indicating the stolen records are historical analytics data from 2021 or earlier.

Mixpanel [says the breach affected](https://mixpanel.com/blog/sms-security-incident/) a "limited number" of customers, with OpenAI and CoinTracker previously disclosing they were affected.

This is the first time it has been publicly confirmed that ShinyHunters was behind the Mixpanel breach.

When contacting PornHub, the company did not provide additional comment to BleepingComputer beyond the security notice.

After publishing our story, Mixpanel told BleepingComputer that it does not believe this data originated from the recent November breach.

"Mixpanel is aware of reports that Pornhub has been extorted with data that that was allegedly stolen from us," Mixpanel told BleepingComputer.

"We can find no indication that this data was stolen from Mixpanel during our November 2025 security Incident or otherwise."

"The data was last accessed by a legitimate employee account at Pornhub’s parent company in 2023\. If this data is in the hands of an unauthorized party, we do not believe that is the result of a security incident at Mixpanel."

## PornHub search and watch history exposed

Today, BleepingComputer learned that ShinyHunters began extorting Mixpanel customers last week, sending emails that began with "We are ShinyHunters" and warned that their stolen data would be published if a ransom was not paid.

In an extortion demand sent to PornHub, ShinyHunters claims it stole 94GB of data containing over 200 million records of personal information in the Mixpanel breach.

ShinyHunters later confirmed to BleepingComputer that they were behind the extortion emails, claiming the data consists of 201,211,943 records of historical search, watch, and download activity for the platform's Premium members.

A small sample of data shared with BleepingComputer shows that the analytic events sent to Mixpanel contain a large amount of sensitive information that a member would not likely want publicly disclosed.

This data includes a PornHub Premium member's email address, activity type, location, video URL, video name, keywords associated with the video, and the time the event occurred.

Activity types seen by BleepingComputer include whether the PornHub subscriber watched or downloaded a video or viewed a channel. However, ShinyHunters also said the events include search histories.

The ShinyHunters extortion group has been behind a string of data breaches this year by compromising various Salesforce integration companies to gain access to Salesforce instances and steal company data.

The threat group is linked to [the exploitation of the Oracle E-Business Suite zero-day](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/) (CVE-2025-61884), as well as [to Salesforce/Drift attacks](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-15-billion-salesforce-records-stolen-in-drift-hacks/) that impacted a [large number of organizations](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) earlier this year.

More recently ShinyHunters [conducted a breach at GainSight](https://www.bleepingcomputer.com/news/security/salesforce-investigates-customer-data-theft-via-gainsight-breach/) that allowed the threat actors to steal further Salesforce data from organizations.

With it now confirmed that ShinyHunters is also behind the Mixpanel breach, the threat actors are responsible for some of the most significant data breaches in 2025, impacting hundreds of companies.

ShinyHunters is also creating a [new ransomware-as-a-service called ShinySpid3r,](https://www.bleepingcomputer.com/news/security/meet-shinysp1d3r-new-ransomware-as-a-service-created-by-shinyhunters/) which will serve as a platform for them and threat actors associated with Scattered Spider to conduct ransomware attacks.