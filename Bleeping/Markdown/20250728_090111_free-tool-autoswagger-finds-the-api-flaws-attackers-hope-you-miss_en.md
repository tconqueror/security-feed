# Free Tool Autoswagger Finds The API Flaws Attackers Hope You Miss

![Autoswagger header](https://www.bleepstatic.com/content/posts/2025/07/23/header-autoswagger.jpg)

## APIs: Still Easy Targets in 2025

APIs are the backbone of modern applications - and one of the most exposed parts of an organization’s infrastructure. This makes them a prime target for attackers.

One of the highest-profile examples was the [Optus breach](https://www.bbc.co.uk/news/world-australia-63056838) in 2022, where attackers stole millions of customer records through an unauthenticated API endpoint - costing the telecom company $140 million AUD in fallout.

Worryingly, vulnerabilities like this are so easy to exploit you could teach someone with no technical background to do it in a day. And three years on, [Intruder’s](https://www.intruder.io?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger) security team is still finding the same issues in the APIs of major organizations - including members of the S&P 500.

That’s why we built [Autoswagger](https://github.com/intruder-io/autoswagger/) \- a free, open-source tool that scans APIs for broken authorization flaws. Read on to see how it works and some of the most surprising issues it uncovered when we put it to the test.

## What is Autoswagger and How Does it Work?

[Autoswagger](https://github.com/intruder-io/autoswagger/) scans domains to detect exposed API documentation - like OpenAPI or Swagger schemas - then parses them to generate a list of endpoints to test. It sends requests using valid parameters from the documentation and flags any endpoint that returns data without proper access control (i.e. no 401 or 403).

If a response includes sensitive data - like credentials or personally identifiable information (PII) - and the endpoint isn’t properly secured, it gets flagged in the output.

![Autoswagger tool](https://www.bleepstatic.com/images/news/security/i/intruder/autoswagger/autoswagger.jpg)

Autoswagger is free to download and install via **[GitHub](https://github.com/intruder-io/autoswagger/)**.

For more advanced testing, [Autoswagger](https://github.com/intruder-io/autoswagger/) can be run with the --brute flag to attempt to bypass validation checks. This helps uncover flaws in endpoints that reject generic input but accept specific data formats or values.

## [Always-On API Security Without The Noise](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger%5Fcta)

APIs are one of the easiest ways into systems - and attackers know it.

Thousands of teams trust Intruder’s always-on exposure management platform to secure their apps and APIs and fix critical issues before attackers find them. Upload your API schema and get peace of mind in minutes.

[Start Free Trial](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger%5Fcta)

## Broken Authorization in Action: Four Real API Vulnerabilities Found by Autoswagger

We put [Autoswagger](https://github.com/intruder-io/autoswagger/) to the test on targets from several large Bug Bounty programs, scanning for vulnerable APIs at scale.

Here are a few real-world examples to show you what broken authorization looks like in the wild.

**Microsoft MPN Credentials**

One vulnerability we found was in an endpoint simply named ‘config’, which exposed credentials and API keys for Microsoft Partner Program data stores. Among the data exposed was a valid set of credentials for a Redis database containing the PII of the partners, including the courses and certifications they had undertaken.

The vulnerable endpoint was buried six layers deep (/1/dashboard/mpn/program/api/config/), making it nearly impossible to guess or discover through brute-force - it was only identified because the API’s OpenAPI schema was exposed.

**60,000+ Salesforce Records**

Another case involved an API connected to a Salesforce instance at a large tech company. The API returned customer records - including names, contact details, and product orders - which could be extracted in bulk by incrementing the ‘ByDate’ url parameter to retrieve 1,000 records per request.

**SQL Access on Internal Training App**

We also found an internal staff training API at a well-known soda company, running in Azure Functions, that allowed unauthenticated users to run arbitrary SQL queries against the database.

While the data was limited to internal training records, it included staff names and email addresses - the kind of detail an attacker could use to craft a convincing phishing campaign.

Azure Functions APIs don’t normally expose documentation, but a developer had deployed an extension that did. While this may have been for another service to consume, there was no clear reason for it to be publicly accessible since the app was meant for internal use.

**Active Directory (AD) Enumeration (Octopus Deploy)**

Finally, Autoswagger discovered [CVE-2025-0589](https://cvemon.intruder.io/cves/CVE-2025-0589?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger), which allowed an unauthenticated attacker to [enumerate Active Directory user information](https://www.intruder.io/research/octopus-deploy-cve-2025-0589?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger) if AD was integrated with the Octopus Deploy server.

## Automated Documentation = Attack Surface Risk

Automated API documentation is great for developers - but just as useful for attackers. When an API’s schema is exposed, it gives them a clear map of every endpoint to target. Without that map, most wouldn’t even bother - fuzzing endpoints blindly takes far more effort.

Hiding documentation isn’t a substitute for proper [API vulnerability management](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger), but publicly exposing docs you don’t need is an unnecessary risk. Most of the vulnerabilities we found were in APIs never meant to be public - yet their documentation was exposed anyway.

Take a look at your own environment: if your internal APIs are documented and exposed to the internet, they might be handing attackers everything they need.

**Intruder continuously scans API endpoints to detect a wide range of vulnerabilities, including exposed documentation.**

**[Check your APIs today by starting a free 14-day trial.](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger)**

### _About the author:_

_Daniel Andrew, Head of Security Services, Intruder_

_Daniel Andrew heads up offensive security at Intruder, where he leads Intruder's Private Bug Bounty team. His background is as a CREST-certified penetration tester and .NET software engineer._

_Sponsored and written by [Intruder](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger)._