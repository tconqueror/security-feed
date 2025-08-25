# Malicious Android apps with 19M installs removed from Google Play

![Malicious Android apps with 19M installs removed from Google Play](https://www.bleepstatic.com/content/hl-images/2024/05/03/Android-2.jpg)

Seventy-seven malicious Android apps with more than 19 million installs were delivering multiple malware families to Google Play users.

This malware infiltration was discovered by [Zscaler's ThreatLabs](https://www.zscaler.com/blogs/security-research/android-document-readers-and-deception-tracking-latest-updates-anatsa) team while investigating a new infection wave with Anatsa (Tea Bot) banking trojan targeting Android devices.

While most of the malicious apps (over 66%) included adware components, the most common Android malware was Joker, which researchers encountered in almost 25% of the analyzed apps.

Once Joker malware is installed on a device, it can read and send text messages, take screenshots, make phone calls, and steal contact lists, access device information, and subscribe users to premium services.

A smaller percentage of the apps included maskware, a term used to define a malicious app that disguises itself as something that would not raise any suspicion.

This type of malware may pose as a legitimate app that works as advertised. However, it performs malicious activity in the background, such as stealing credentials, banking info, or other sensitive data (location, SMS). Cybercriminals can also use maskware to deliver other malware.

Zscaler researchers also found a variant of the Joker malware called Harly, which comes as a legitimate app that has a malicious payload hidden deeper in the code to avoid detection during the review process.

![](https://cms.zscaler.com/cdn-cgi/image/format=auto/sites/default/files/images/blogs/anatsa_2025_figure_5_0.png)

Caption

In a report in March, Human Security [researchers said](https://www.humansecurity.com/learn/blog/satori-perpectives-tracking-the-ongoing-evolution-of-harly-trojan-android-fraud/) that Harly can hide in popular apps, like games, wallpapers, flashlights, and photo editors.

### Anatsa trojan keeps evolving

According to Zscaler, the latest version of the Anatsa banking trojan has further expanded its targeting scope, increasing the number of banking and cryptocurrency apps to 831, from 650 previously, that it attempts to steal data from.

The malware operators use an app named 'Document Reader – File Manager' as a decoy, which only downloads the malicious Anatsa payload after installation, to evade Google's code review.

![Anatsa trojan app on Google Play](https://www.bleepstatic.com/images/news/u/1220909/2025/August/play.jpg)

**Anatsa trojan app on Google Play**  
_Source: Zscaler_

The latest campaign has switched from remote DEX dynamic code loading used in the past to direct payload installation, unpacking it from JSON files, and then deleting them.

In terms of evasion, it uses malformed APK archives to break static analysis, runtime DES-based string decryption, and emulation detection. Package names and hashes are also periodically changed.

**Detecting emulation (left) and fetching the payload (right)**  
_Source: Zscaler_

Capability-wise, Anatsa abuses Accessibility permissions on Android to auto-grant itself extensive privileges.

It fetches phishing pages from its server for over 831 apps, now also covering Germany and South Korea, while a keylogger module has also been added for generic data theft.

This latest Anatsa campaign follows another recent wave discovered by ThreatFabric in July, where the trojan sneaked into Google Play posing as a PDF viewer, achieving over [50,000 downloads](https://www.bleepingcomputer.com/news/security/android-malware-anatsa-infiltrates-google-play-to-target-us-banks/).

Older Anatsa campaigns include a PDF and QR Code Reader attack in May 2024 that achieved [70,000 infections](https://www.bleepingcomputer.com/news/security/over-90-malicious-android-apps-with-55m-installs-found-on-google-play/), a Phone Cleaner and PDF attack in February 2024 that got [150,000 downloads](https://www.bleepingcomputer.com/news/security/anatsa-android-malware-downloaded-150-000-times-via-google-play/), and another PDF Viewer attack in March 2023 that achieved [30,000 installs](https://www.bleepingcomputer.com/news/security/anatsa-android-trojan-now-steals-banking-info-from-users-in-us-uk/).

## Malicious app wave on Google Play

In addition to the malicious Anatsa apps, Zscaler discovered this time, most were adware families, followed by 'Joker,' 'Harly,' and various maskware.

"ThreatLabz identified a sharp rise in adware applications on the Google Play Store alongside malware, such as Joker, Harly, and banking trojans like Anatsa," explained Zscaler researcher Himanshu Sharma.

"Conversely, there has been a noticeable decline in malware families such as Facestealer and Coper."

Tools and personalization apps accounted for over half of the lures used to spread those apps, so these two categories, together with entertainment, photography, and design, should be treated as high-risk.

In total, the 77 malicious apps, including those containing Anatsa, were downloaded 19 million times from Google Play.

Zscaler reports that Google removed all of the malicious apps they discovered this time from the Play Store following their reporting.

Android users must ensure their Play Protect service is active on their device to flag malicious apps for removal.

In the case of Anatsa trojan infections, separate steps need to be taken with the bank to protect potentially compromised e-banking accounts or credentials.

To minimize the risk from malware loaders on Google Play, only trust reputable publishers, read at least a couple of user reviews, and only grant permissions that are directly related to the app's core functionality.