# Malicious Chrome extensions with 1.7M installs found on Web Store

![Malicious extensions with 1.7M installs found on Chrome Web Store](https://www.bleepstatic.com/content/hl-images/2021/09/23/Chrome_flare.jpg)

Almost a dozen malicious extensions with 1.7 million downloads in Google's Chrome Web Store could track users, steal browser activity, and redirect to potentially unsafe web addresses.

Most of the add-ons provide the advertised functionality and pose as legitimate tools like color pickers, VPNs, volume boosters, and emoji keyboards.

Researchers at Koi Security, a company providing a platform for security self-provisioned software, discovered the malicious extensions in Chrome Web Store and reported them to Google.

Some of the extensions are no longer present but many of them continue to be available.

![Two of the Chrome extensions featuring tracking code](https://www.bleepstatic.com/images/news/u/1220909/2025/July/1.jpg)

**Two of the Chrome extensions featuring tracking code**  
_Source: BleepingComputer_

Many of those extensions are verified, have hundreds of positive reviews, and are featured prominently on the Chrome Web Store, misleading users about their safety.

Users should check for the following add-ons in Chrome browser and remove them as soon as possible:

* Color Picker, Eyedropper — Geco colorpick
* Emoji keyboard online — copy&paste your emoji
* Free Weather Forecast
* Video Speed Controller — Video manager
* Unlock Discord — VPN Proxy to Unblock Discord Anywhere
* Dark Theme — Dark Reader for Chrome
* Volume Max — Ultimate Sound Booster
* Unblock TikTok — Seamless Access with One-Click Proxy
* Unlock YouTube VPN
* Unlock TikTok
* Weather

One of them, ‘Volume Max — Ultimate Sound Booster,’ has also been [flagged by LayerX](https://layerxsecurity.com/blog/sleeper-sound-layerx-uncovers-malicious-sleeper-sound-management-extensions-with-nearly-1-5-million-users-worldwide/) researchers last month, who warned about its potential for spying on users; but no malicious activity could be confirmed at the time.

![Risky Chrome extension flagged by two security teams](https://www.bleepstatic.com/images/news/u/1220909/2025/July/3.jpg)

**Risky Chrome extension flagged by two security teams**  
_Source: BleepingComputer_

According to the researchers, the malicious functionality is implemented in the background service worker of each extension using the Chrome Extensions API, registering a listener that is triggered every time a user navigates to a new webpage.

The listener captures the URL of the visited page and exfiltrates the information to a remote server along with a unique tracking ID for each user.

The server can respond with redirection URLs, hijacking the user’s browsing activity and potentially taking them to unsafe destinations that may enable cyberattacks.

Although the possibility is there, it should be noted that Koi Security has not observed malicious redirections in their testing.

Furthermore, the malicious code was not present in the initial versions of the extensions, but was introduced at a later time via updates.

Google’s auto-update system silently deploys the newest versions to users without requiring any user approval or interaction.

Given that some of these extensions were safe for years, it is possible that they were hijacked/compromised by external actors who introduced the malicious code.

BleepingComputer contacted several publishers to inquire about this possibility, but we have not yet heard back from any of them.

Before publishing this article, Koi Security researchers [discovered](https://medium.com/@idandrd/fb4ed4f40ff5) that cybercriminals have also planted malicious extensions in the official store for Microsoft Edge, which shows a total count of 600,000 downloads.

"Combined, these eighteen extensions have infected over 2.3 million users across both browsers, creating one of the largest browser hijacking operations we’ve documented," the researchers say.

They recommend users remove all listed extensions immediately, clear the browsing data to purge any tracking identifiers, check the system for malware, and monitor accounts for suspicious activity.