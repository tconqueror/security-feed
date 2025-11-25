# Code beautifiers expose credentials from banks, govt, tech orgs

![Code beautifiers expose credentials from banks, govt, tech orgs](https://www.bleepstatic.com/content/hl-images/2024/04/16/2.jpg)

Thousands of credentials, authentication keys, and configuration data impacting organizations in sensitive sectors have been sitting in publicly accessible JSON snippets submitted to the JSONFormatter and CodeBeautify online tools that format and structure code.

Researchers discovered more than 80,000 user pastes totaling over 5GB exposed through a feature called Recent Links provided by both services, which is freely accessible to anyone.

Some of the companies and organizations with sensitive data leaked this way are in high-risk sectors like government, critical infrastructure, banking, insurance, aerospace, healthcare, education, cybersecurity, and telecommunications.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

## Saving secrets online

Researchers at external attack surface management company WatchTowr examined the JSONFormatter and CodeBeautify online platforms and found that their Recent Links feature provided access to JSON snippets that users had saved on the services' servers for temporary sharing purposes.

When clicking the 'save' button, the platform generates a unique URL pointing to that page and adds it to the user’s Recent Links page, which has no protection layer, thus leaving the content accessible to anyone.

Since Recent Links pages follow a structured, predictable URL format, the URL can be easily retrieved with a simple crawler.

![The Recent Links section](https://www.bleepstatic.com/images/news/u/1220909/2025/November/publishedpages.jpg)

**The Recent Links section on JSON Formatter**  
_Source: watchTowr_

## Level of exposure

By scraping these public “Recent Links” pages and pulling the raw data using the platforms’ getDataFromID API endpoints, watchTowr collected over 80,000 user pastes corresponding to five years of JSONFormatter data and one year of CodeBeautify data with sensitive details:

* Active Directory credentials
* Database and cloud credentials
* Private keys
* Code repository tokens
* CI/CD secrets
* Payment gateway keys
* API tokens
* SSH session recordings
* Large amounts of personally identifiable information (PII), including know-your-customer (KYC) data
* An AWS credential set used by an international stock exchange’s Splunk SOAR system
* Credentials for a bank exposed by an MSSP onboarding email

In one case, the researchers found "materially sensitive information" from a cybersecurity company that could be easily identified. The content included "encrypted credentials for a very sensitive configuration file," SSL certificate private key passwords, external and internal hostnames and IP addresses, and paths to keys, certificates, and configuration files.

**JSON snippet for a cybersecurity company**  
_Source: watchTowr_

Pastes from a government entity included 1,000 lines of PowerShell code that configured a new host by fetching installers, "configuring registry keys, hardening configurations, and finally deploying a web app."

Even if the script did not include sensitive data, [watchTowr says](https://labs.watchtowr.com/stop-putting-your-passwords-into-random-websites-yes-seriously-you-are-the-problem/) that it had valuable information that an attacker could use, such as details about internal endpoints, IIS configuration values and properties, and hardening configurations with the corresponding registry keys.

A technology company providing Data Lake-as-a-Service (DLaaS) products exposed a configuration file for cloud infrastructure, complete with domain names, email addresses, hostnames, and credentials for Docker Hub, Grafana, JFrog, and RDS Database.

The researchers also found valid production AWS credentials from a "major financial exchange" that were associated with Splunk SOAR automation.

A managed security service provider (MSSP) leaked the Active Directory credentials for its environment, as well as email and ID-based credentials for a bank in the U.S., which watchTowr describes as "the MSSP’s largest, most heavily advertised client."

As threat actors are constantly scanning for sensitive information on easy-to-access systems, watchTowr wanted to see if any attacker was already scanning the publicly available JSONs.

To this end, they used the [Canarytokens service](https://canarytokens.org/nest/generate) to generate fake but valid-looking AWS access keys and planted them on the JSONFormatter and CodeBeautify platforms in JSONs accessible through links set to expire in 24 hours.

However, the researchers' honeypot system recorded access attempts using the fake keys 48 hours after the initial upload and save.

"More interestingly, they were tested 48 hours after our initial upload and save (for those mathematically challenged, this is 24 hours after the link had expired and the 'saved' content was removed)," watchTowr says in the report.

watchTowr emailed many of the affected organizations, and while some remediated the issues, many did not respond.

Currently, the Recent Links are still freely accessible on the two code-formatting platforms, allowing threat actors to scrape the resources for sensitive data.