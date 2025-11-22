# WhatsApp API flaw let researchers scrape 3.5 billion accounts

![WhatsApp](https://www.bleepstatic.com/content/hl-images/2022/05/31/WhatsApp.jpg)

Researchers compiled a list of 3.5 billion WhatsApp mobile phone numbers and associated personal information by abusing a contact-discovery API that lacked rate limiting.

The team reported the issue to WhatsApp, and the company has since added rate-limiting protections to prevent similar abuse.

While this study was conducted by researchers who have not released the data, it illustrates a common tactic used by threat actors to scrape user information from publicly exposed and unprotected APIs.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

## Abusing WhatsApp API

The researchers from the University of Vienna and SBA Research used WhatsApp's contact-discovery feature, which lets you submit a phone number to the platform's `GetDeviceList` API endpoint to determine whether a phone number is associated with an account and what devices were used.

Without strict rate limiting, APIs like this can be abused to perform large-scale enumeration across a platform.

The researchers found this to be the case with WhatsApp, as they were able to send a high volume of queries directly to WhatsApp's servers, checking more than 100 million numbers per hour.

They ran the entire operation from a single university server using just five authenticated sessions, initially expecting to get caught by WhatsApp. However, the platform never blocked the accounts, never throttled their traffic, never restricted their IP address, and never reached out despite all the abusive activity coming from one device.

The researchers then generated a global set of 63 billion potential mobile numbers and tested all of them against the API. Their queries returned 3.5 billion active WhatsApp accounts.

The results also gave a previously unknown snapshot of how WhatsApp is used globally, showing where the platform is most used:

* **India:** 749 million
* **Indonesia:** 235 million
* **Brazil:** 206 million
* **United States:** 138 million
* **Russia:** 133 million
* **Mexico:** 128 million

Millions of active accounts were also identified inside countries where WhatsApp was banned at the time, including China, Iran, North Korea, and Myanmar. In Iran, usage continued to grow as the ban was lifted in December 2024.

In addition to confirming whether a phone number was used on WhatsApp, the researchers used other API endpoints to enumerate additional information about users, including the `[GetUserInfo](https://pkg.go.dev/go.mau.fi/whatsmeow)`, `GetPrekeys`, and `FetchPicture`.

Using these additional APIs, the researchers were able to collect profile photos, "about" text, and information about other devices associated with a WhatsApp phone number.

A test of US numbers downloaded 77 million profile photos without any rate limiting, with many showing identifiable faces. If public "about" text was available, it also revealed personal details and links to other social accounts.

Finally, when the researchers compared their findings with the [2021 Facebook phone-number scrape](https://www.bleepingcomputer.com/news/security/533-million-facebook-users-phone-numbers-leaked-on-hacker-forum/), they found that 58% of the leaked Facebook numbers were still active on WhatsApp in 2025\. The researchers explain that large-scale phone number leaks are so damaging because they can remain useful in other malicious behavior for years.

"With 3.5 B records (i.e., active accounts), we analyze a dataset that would, to our knowledge, classify as the largest data leak in history, had it not been collated as part of a responsibly-conducted research study," explains the "[Hey there! You are using WhatsApp: Enumerating Three Billion Accounts for Security and Privacy](https://github.com/sbaresearch/whatsapp-census/blob/main/Hey%5Fthere%5FYou%5Fare%5Fusing%5FWhatsApp.pdf)" paper.

"The dataset contains phone numbers, timestamps, about text, profile pictures, and public keys for E2EE encryption, and its release would entail adverse implications to the included users."

## Other malicious cases of API abuse

WhatsApp's lack of rate limiting for its APIs is illustrative of a widespread issue on online platforms, where APIs are designed to make it easy to share information and perform tasks, but they also become vectors for large-scale scraping.

In 2021, threat actors exploited a bug in Facebook's "Add Friend" feature that allowed them to upload contact lists from a phone and check whether those contacts were on the platform. However, this API also did not properly rate-limit requests, allowing threat actors to create profiles for 533 million users that included their phone numbers, Facebook IDs, names, and genders.

Meta [later confirmed](https://about.fb.com/news/2021/04/facts-on-news-reports-about-facebook-data/) that the data came from automated scraping of an API that lacked proper safeguards, with the Irish Data Protection Commission (DPC) [fining Meta €265 million over the leak](https://www.bleepingcomputer.com/news/security/meta-fined-265m-for-not-protecting-facebook-users-data-from-scrapers/).

Twitter [faced a similar problem](https://www.bleepingcomputer.com/news/security/twitter-confirms-zero-day-used-to-expose-data-of-54-million-accounts/) when attackers exploited an API vulnerability to match phone numbers and email addresses to 54 million accounts.

Dell disclosed that 49 million customer records were scraped after attackers [abused an unprotected API endpoint](https://www.bleepingcomputer.com/news/security/dell-api-abused-to-steal-49-million-customer-records-in-data-breach/).

All of these incidents, including WhatsApp's, are caused by APIs that perform account or data lookups without adequate rate limits, making them easy targets for large-scale enumeration.