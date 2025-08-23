# Google patched bug leaking phone numbers tied to accounts

![Google](https://www.bleepstatic.com/content/hl-images/2023/12/29/Google_headpic.jpg)

A vulnerability allowed researchers to brute-force any Google account's recovery phone number simply by knowing their profile name and an easily retrieved partial phone number, creating a massive risk for phishing and SIM-swapping attacks.

The attack method involves abusing a now-deprecated JavaScript-disabled version of the Google username recovery form, which lacked modern anti-abuse protections.

The flaw was discovered by [security researcher BruteCat](https://brutecat.com/articles/leaking-google-phones), the same one who demonstrated in February that it's possible to expose the private [email addresses of YouTube accounts](https://www.bleepingcomputer.com/news/security/google-fixes-flaw-that-could-unmask-youtube-users-email-addresses/).

BruteCat told BleepingComputer that while the attack retrieves the phone number users configured for the Google account recovery, this is the same as the account holder's primary phone number in the vast majority of cases.

## Brute-forcing Google numbers

BruteCat discovered that he could access a legacy no-JavaScript username recovery form, which appeared to be working as expected.

The form allowed querying if a phone number was associated with a Google account based on a user's profile display name ("John Smith") via two POST requests.

The researcher bypassed the rudimentary rate-limiting defenses on the form by using IPv6 address rotation to generate trillions of unique source IPs via /64 subnets for these requests.

The CAPTCHAs displayed by many requests were bypassed by substituting the 'bgresponse=js_disabled' parameter with a valid BotGuard token from the JS-enabled form.

![Captured BotGuard token from a Google JS-enabled username recovery form](https://www.bleepstatic.com/images/news/u/1220909/2025/June/bgtoken.jpg)

**Captured BotGuard token from a Google JS-enabled username recovery form**  
_Source: BruteCat_

With the technique set, BruteCat developed a brute-forcing tool (gpb) that iterates through number ranges using country-specific formats and filters false positives.

The researcher used Google's 'libphonenumber' to generate valid number formats, built a country mask database to identify phone formats by region, and wrote a script to generate BotGuard tokens via headless Chrome.

On a brute-forcing rate of 40,000 requests per second, US numbers would take about 20 minutes, UK 4 minutes, and the Netherlands less than 15 seconds.

![Time to brute-force phone numbers](https://www.bleepstatic.com/images/news/u/1220909/2025/June/table(1).jpg)

**Time to brute-force phone numbers**  
_Source: BruteCat_

To start an attack against someone, their email address is required for the form, but Google has set this to hidden since last year.

BruteCat found he could retrieve it by creating a Looker Studio document and transferring ownership to the target's Gmail address.

Once ownership is transferred, the target's Google display name appears on the document creator's Looker Studio dashboard, requiring zero interaction with the target.

Armed with this email address, they could perform repeated queries to determine all phone numbers associated with the profile name.

However, as there can be thousands of accounts with the same profile name, the researcher narrowed it down using the target's partial number.

To get a partial phone number for the user, the researcher utilized Google's "account recovery" workflow, which will display two digits of a configured recovery phone number.

"This time can also be significantly reduced through phone number hints from password reset flows in other services such as PayPal, which provide several more digits (ex. +14•••••1779)", explains BruteCat.

The leaking of phone numbers associated with a Google account can cause a massive security risk to users, who can then be targeted in targeted vishing attacks or SIM swap attacks.

A demonstration of exploiting this flaw can be seen in the video below.

## Bug fixed

BruteCat reported his findings to Google via the tech giant's Vulnerability Reward Program (VRP) on April 14, 2025.

Google initially considered the exploitability risk low, but on May 22, 2025, it upgraded the issue to "medium severity," applying interim mitigations and paying the researcher a reward of $5,000 for the disclosure.

On June 6, 2025, Google confirmed that it had fully deprecated the vulnerable no-JS recovery endpoint.

The attack vector is no longer exploitable, but whether or not it was ever maliciously exploited remains unknown.