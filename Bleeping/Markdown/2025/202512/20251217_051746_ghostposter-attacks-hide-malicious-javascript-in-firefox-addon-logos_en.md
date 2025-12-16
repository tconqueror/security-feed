# GhostPoster attacks hide malicious JavaScript in Firefox addon logos

![GhostPoster attacks hide malicious JavaScript in Firefox addon logos](https://www.bleepstatic.com/content/hl-images/2025/05/29/firefox-header.jpg)

A new campaign dubbed 'GhostPoster' is hiding JavaScript code in the image logo of malicious Firefox extensions with more than 50,000 downloads, to monitor browser activity and plant a backdoor.

The malicious code grants operators persistent high-privilege access to the browser, enabling them to hijack affiliate links, inject tracking code, and commit click and ad fraud.

The hidden script is acting as a loader that fetches the main payload from a remote server. To make the process more difficult to detect, the payload is intentionally retrieved only once in ten attempts.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

Koi Security researchers discovered the GhostPoster campaign and identified 17 compromised Firefox extensions that either read the PNG logo to extract and execute the malware loader or download the main payload from the attacker's server.

It should be noted that the malicious extensions are from popular categories:

1. free-vpn-forever
2. screenshot-saved-easy
3. weather-best-forecast
4. crxmouse-gesture
5. cache-fast-site-loader
6. freemp3downloader
7. google-translate-right-clicks
8. google-traductor-esp
9. world-wide-vpn
10. dark-reader-for-ff
11. translator-gbbd
12. i-like-weather
13. google-translate-pro-extension
14. 谷歌-翻译
15. libretv-watch-free-videos
16. ad-stop
17. right-click-google-translate

The researchers say that not all the extensions above use the same payload loading chain, but all of them exhibit the same behavior and communicate with the same infrastructure.

The FreeVPN Forever extension was the one Koi Security analyzed initially after its AI tool flagged it for parsing the raw bytes of its logo image file to locate a JavaScript snippet hidden using the steganography technique.

![Malicious extension on the Firefox store](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ext.jpg)

**Malicious extension on the Firefox store**  
_Source: Koi Security_

The JavaScript loader activates 48 hours later to fetch a payload from a hardcoded domain. A second backup domain is available if the payload is not retrieved from the first one.

According to [Koi Security](https://www.koi.ai/blog/inside-ghostposter-how-a-png-icon-infected-50-000-firefox-browser-users), the loader is mostly dormant and gets the payload only 10% of the time, making it likely to evade detection from traffic monitoring tools.

The downloaded payload is heavily obfuscated via case swapping and base64 encoding. A cipher decodes it and then XOR-encrypts it using a key derived from the extension’s runtime ID.

**Parsing the logo data for the malicious snippet**  
_Source: Koi Security_

The final payload has the following capabilities:

* Hijacks affiliate links on major e-commerce sites, redirecting commissions to the attackers.
* Injects Google Analytics tracking into every page the user visits.
* Strips security headers from all HTTP responses.
* Bypasses CAPTCHA via three distinct mechanisms to circumvent bot protections.
* Injects invisible iframes for ad fraud, click fraud, and tracking, which self-delete after 15 seconds.

Although the malware does not harvest passwords or redirect users to phishing pages, it still threatens user privacy.

Moreover, due to the stealthy loader employed by GhostPoster, the campaign could quickly become far more dangerous if the operator decides to deploy a more harmful payload.

Users of the listed extensions are recommended to remove them and should consider resetting passwords for critical accounts.

Many of the malicious extensions were still available on Firefox’s Add-Ons page at the time of writing. BleepingComputer has contacted Mozilla about it, but a comment wasn’t immediately available.