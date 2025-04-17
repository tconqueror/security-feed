# Chrome extensions with 6 million installs have hidden tracking code

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

A set of 57 Chrome extensions with 6,000,000 users have been discovered with very risky capabilities, such as monitoring browsing behavior, accessing cookies for domains, and potentially executing remote scripts.

These extensions are 'hidden,' meaning they don't show up on Chrome Web Store searches, nor do search engines index them, and can only be installed if the user has the direct URL.

Typically, such extensions are private software like internal company tools or add-ons still under development. Still, threat actors might be using them to evade detection while aggressively pushing them through ads and malicious sites.

## Risky Chrome extensions

The extensions were discovered by Secure Annex researcher John Tuckner, who uncovered the first 35 after examining what he claims is a suspicious extension named 'Fire Shield Extension Protection.'

The extension is heavily obfuscated and contains callbacks to an API for sending information collected from the browser.

![Tracking function in Fire Shield extension](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Tracking function in Fire Shield extension**  
_Source: Secure Annex_

Through a domain called "unknow.com" contained in the extension, Tuckner found additional extensions containing the same domain that claim to provide ad-blocking or privacy protection services.

![Finding more extensions phoning the same external domain](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Finding more extensions phoning the same external domain**  
_Source: Secure Annex_

However, all of these include overly broad permissions allowing them to perform the following actions:

* Access cookies, including sensitive headers (e.g., 'Authorization')
* Monitor user browsing behavior
* Modify search providers (and results)
* Inject and execute remote scripts on visited pages via iframes
* Activate advanced tracking remotely

While Tuckner didn't catch any extensions stealing user passwords or cookies, the excessively risky capabilities, heavily obfuscated code, and hidden logic were enough for the researcher to label them as risky and, potentially, spyware.

"There are additional obfuscated signals in other functions that there is significant command and control potential like the ability to list top sites visited, open/close tabs, get top sites visited, and run many of the capabilities above in an ad hoc manner," [explains Tuckner](https://secureannex.com/blog/searching-for-something-unknow/).

"Many of these capabilities have not been validated, but again, the presence of this capability in 35 extensions which claim to do simple things like protect you from malicious extensions is quite concerning."

**Excessive permissions secured by the extensions**  
_Source: Secure Annex_

Earlier today, the researcher [added 22 more extensions](https://x.com/tuckner/status/1912616945284788246) believed to belong to the same operation, taking the total to 57 extensions used by 6 million people. Some of the newly added extensions are public, too.

Tuckner says that many of the extensions have been removed from the Chrome Web Store following his report from last week, but others still remain.

**One of the risky extensions still hosted on the Web Store**  
_Source: BleepingComputer_

The complete list is [available here](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), with the ones with the highest download counts listed below:

1. **Cuponomia – Coupon and Cashback** (700,000 users, public)
2. **Fire Shield Extension Protection** (300,000 users, unlisted)
3. **Total Safety for Chrome™** (300,000 users, unlisted)
4. **Protecto for Chrome™** (200,000 users, unlisted)
5. **Browser WatchDog for Chrome** (200,000 users, public)
6. **Securify for Chrome™** (200,000 users, unlisted)
7. **Browser Checkup for Chrome by Doctor** (200,000 users, public)
8. **Choose Your Chrome Tools** (200,000 users, unlisted)

If you have any of the above installed, it is recommended that you remove them immediately and, out of an abundance of caution, perform password resets on online accounts.

Google told BleepingComputer that they are aware of Tuckner's report and are investigating the extensions.

BleepingComputer also contacted the developer of these extensions with questions about the obfucated code but has not received a reply at this time.

### Related Articles:

[Chrome 136 fixes 20-year browser history privacy risk](https://www.bleepingcomputer.com/news/security/chrome-136-fixes-20-year-browser-history-privacy-risk/)

[Malicious Chrome extensions can spoof password managers in new attack](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-can-spoof-password-managers-in-new-attack/)

[Google fixes Chrome zero-day exploited in espionage campaign](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/)

[23andMe files for bankruptcy, customers advised to delete DNA data](https://www.bleepingcomputer.com/news/security/23andme-files-for-bankruptcy-customers-advised-to-delete-dna-data/)

[WhatsApp patched zero-click flaw exploited in Paragon spyware attacks](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/)