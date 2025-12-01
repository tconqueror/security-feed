# ShadyPanda browser extensions amass 4.3M installs in malicious campaign

![Chrome and Edge logos](https://www.bleepstatic.com/content/hl-images/2025/12/01/chrome-edge-buttons.jpg)

A long-running malware operation known as "ShadyPanda" has amassed over 4.3 million installations of seemingly legitimate Chrome and Edge browser extensions that evolved into malware.

The operation, discovered by Koi Security, unfolded in distinct phases that gradually introduced additional malicious functionality, turning the browser extension from a legitimate tool into spyware.

The ShadyPanda campaign consists of 145 malicious extensions (20 Chrome and 125 Edge) over the years. While Google has removed them from the Web Store, Koi reports that the campaign remains active on the Microsoft Edge Add-ons platform, with one extension listed as having 3 million installs.

It should be noted that it is unclear if the installations of these extensions have been manually inflated to increase their legitimacy.

## The ShadyPanda campaign

While the initial submissions of ShadyPanda extensions occurred in 2018, the first signs of malicious activity were observed in 2023, with a set of extensions posing as wallpaper and productivity tools.

According to Koi researchers, these extensions engaged in affiliate fraud by injecting tracking codes from eBay, Booking.com, and Amazon into legitimate links to generate revenue from users' purchases.

In early 2024, an extension called Infinity V+ began performing search hijacking, indicating that the ShadyPanda operators were becoming bolder.

Koi says the extension redirected search queries to trovi\[.\]com, exfiltrated users' cookies to dergoodting\[.\]com, and exfiltrated users' search queries to gotocdn subdomains.

In 2024, five extensions from the set, including three uploaded in 2018 and 2019, which had gained a good reputation in the meantime, were modified to include a "backdoor" delivered via an update that enabled them to perform remote code execution.

"Every infected browser runs a remote code execution framework. Every hour, it checks api.extensionplay\[.\]com for new instructions, downloads arbitrary JavaScript, and executes it with full browser API access," explains [Koi Security](http://www.koi.ai/blog/4-million-browsers-infected-inside-shadypanda-7-year-malware-campaign) about the backdoor's functionality.

"This isn't malware with a fixed function. It's a backdoor."

![The RCE function](https://www.bleepstatic.com/images/news/u/1220909/2025/November/rce.jpg)

**The RCE function**  
_Source: Koi Security_

The backdoor also exfiltrates browsing URLs, fingerprinting information, and persistent identifiers to api\[.\]cleanmasters\[.\]store, using AES encryption.

A notable extension in this set is Clean Master on the Google Chrome Store, which had 200,000 installs at the time it was detected as malicious. In total, the extensions that carried the same payload had reached 300,000 installs.

![The Clean Master extension](https://www.bleepstatic.com/images/news/u/1220909/2025/November/cleanmaseter.jpg)

**The Clean Master extension**  
_Source: Koi Security_

The fourth and final phase of the attack, which is the only one still underway, concerns five Microsoft Edge extensions published by 'Starlab Technology' in 2023\. Since then, the extensions have accumulated 4 million installs.

According to the researchers, the spyware component in these extensions collects the following data, sending it to 17 domains in China:

* Browsing history
* Search queries and keystrokes
* Mouse clicks with coordinates
* Fingerprint data
* Local/session storage & cookies

**Data stolen from infected devices**  
_Source: Koi Security_

Koi Security notes that these extensions also have sufficient permissions to deliver a similar backdoor seen in the Clean Master set via an update. However, no sign of this more malicious activity has been seen at this time.

The researchers told BleepingComputer that they contacted Google and Microsoft about the malicious extensions. While they were later removed from the Google Play Store, at the time of writing, BleepingComputer found "WeTab 新标签页" (3 million users) and "Infinity New Tab (Pro)" (650k users) extensions from the publisher still present on the Microsoft Edge Add-ons store.

**Spyware Edge extension**  
_Source: Koi Security_

A complete list of all extension IDs linked to the ShadyPanda operation is available at the bottom of Koi Security's report.

Users are recommended to remove them immediately and reset their account passwords across their entire online presence.

BleepingComputer has contacted both Google and Microsoft about Koi Security's findings, and we will add their statements once we receive a response. We have also contacted the known developers of these extensions, but did not receive a response to our email.