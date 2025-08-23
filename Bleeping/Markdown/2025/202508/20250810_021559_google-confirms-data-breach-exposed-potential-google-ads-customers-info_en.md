# Google confirms data breach exposed potential Google Ads customers' info

![Google Ads](https://www.bleepstatic.com/content/hl-images/2025/01/15/Google-Ads.jpg)

Google has confirmed that a [recently disclosed data breach](https://www.bleepingcomputer.com/news/security/google-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/) of one of its Salesforce CRM instances involved the information of potential Google Ads customers.

"We're writing to let you know about an event that affected a limited set of data in one of Google's corporate Salesforce instances used to communicate with prospective Ads customers," reads a data breach notification shared with BleepingComputer.

"Our records indicate basic business contact information and related notes were impacted by this event."

Google says the exposed information includes business names, phone numbers, and "related notes" for a Google sales agent to contact them again.

The company says that payment information was not exposed and that there is no impact on Ads data in Google Ads Account, Merchant Center, Google Analytics, and other Ads products.

The breach was conducted by threat actors known as ShinyHunters, who have been behind an ongoing wave of data theft attacks targeting Salesforce customers.

While Google has not shared how many individuals were impacted, ShinyHunters says the stolen information contains approximately 2.55 million data records. It is unclear if there are duplicates within these records.

ShinyHunters further told BleepingComputer that they are also working with threat actors associated with "Scattered Spider, who are responsible for first gaining initial access to targeted systems.

"Like we have said repeatedly already, ShinyHunters and Scattered Spider are one and the same," ShinyHunters told BleepingComputer.

"They provide us with initial access and we conduct the dump and exfiltration of the Salesforce CRM instances. Just like we did with Snowflake."

The threat actors are now referring to themselves as "Sp1d3rHunters," to illustrate the overlapping group of people who are involved in these attacks.

As part of these attacks, the threat actors conduct social engineering attacks against employees to gain access to credentials or trick them into linking a malicious version of Salesforce's Data Loader OAuth app to the target's Salesforce environment.

The threat actors then download the entire Salesforce database and extort the companies via email, threatening to release the stolen data if a ransom is not paid.

These Salesforce attacks were [first reported by the Google Threat Intelligence Group (GTIG)](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) in June, with the company suffering the same fate a month later.

Databreaches.net reported that the threat actors have already [sent an extortion demand to Google](http://databreaches.net/2025/08/08/shinyhunters-sent-google-an-extortion-demand-shiny-comments-on-current-activities/). After publishing the story, ShinyHunters told BleepingComputer that they demanded 20 Bitcoins, or approximately $2.3 million, from Google to not leak the data.

"I don't care about ransoming Google anyway, I just sent them a bogus email for the lulz of it," said the threat actor.

ShinyHunters says they have since switched to a new custom tool that makes it easier and quicker to steal data from compromised Salesforce instances.

In an update, [Google recently acknowledged](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion#:~:text=UNC6040%20%28Evolving%20TTPs%29) the new tooling, stating that they have seen Python scripts used in the attacks instead of the Salesforce Data Loader.

_Update 8/9/25: Added further information about the extortion demand._