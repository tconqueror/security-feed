# New Android spyware ClayRat imitates WhatsApp, TikTok, YouTube

![New Android spyware ClayRat imitates WhatsApp, TikTok, YouTube](https://www.bleepstatic.com/content/hl-images/2024/05/03/Android-3.jpg)

A new Android spyware called ClayRat is luring potential victims by posing as popular apps and services like WhatsApp, Google Photos, TikTok, and YouTube.

The malware is targeting Russian users through Telegram channels and malicious websites that appear legitimate. It can steal SMS meessages call logs, notifications, take pictures, and even make phone calls.

Malware researchers at mobile security company Zimperium say that they documented more than 600 samples and 50 distinct droppers over the past three months, indicating an active effort from the attacker to amplify the operation.

## ClayRat campaign

The ClayRat campaign, named after the malware’s command and control (C2) server, uses carefully crafted phishing portals and registered domains that closely mimic legitimate service pages.

These sites host or redirect visitors to Telegram channels where the Android package files (APKs) are provided to unsuspecting victims.

To add legitimacy to these sites, the threat actors have added fake comments, inflated download counts, and used a bogus Play Store-like UX with step-by-step instructions on how to sideload APKs and bypass Android’s security warnings.

![Fake update loading the spyware in the background](https://www.bleepstatic.com/images/news/u/1220909/2025/October/fakeupdate.jpg)

**Fake update loading the spyware in the background**  
_Source: Zimperium_

According to Zimperium, some ClayRat malware samples act as droppers, where the app the user sees is a fake Play Store update screen and an encrypted payload is hidden in the app's assets.

The malware nests in the device using a “[session-based](https://www.bleepingcomputer.com/news/security/cybercrime-service-bypasses-android-security-to-install-malware/)” installation method to bypass [Android 13+ restrictions](https://www.bleepingcomputer.com/news/security/malware-devs-already-bypassed-android-13s-new-security-feature/) and reduce user suspicion.

"This session-based installation method lowers perceived risk and increases the likelihood that a webpage visit will result in spyware being installed," the researchers say.

Once active on the device, the malware can use the new host to propagate to more victims by using it as a springboard to send SMS to the victim’s contact list.

![Telegram channel spreading the droppers](https://www.bleepstatic.com/images/news/u/1220909/2025/October/telegram.jpg)

**Telegram channel spreading ClayRat droppers**  
_Source: Zimperium_

## Spyware’s capabilities

The ClayRat spyware assumes the default SMS handler role on infected devices, allowing it to read all incoming and stored SMS, intercept them before other apps, and modify SMS databases.

**ClayRat becoming the default SMS handler**  
_Source: Zimperium_

The spyware establishes communication with the C2, that are AES-GCM encrypted in its latest versions, and then receives one of the 12 supported commands:

* get\_apps\_list — send list of installed apps to C2
* get\_calls — send call logs
* get\_camera — take a front-camera photo and send it to the server
* get\_sms\_list — exfiltrate SMS messages
* messsms — send mass SMS to all contacts
* send\_sms / make\_call — send SMS or place calls from the device
* notifications / get\_push\_notifications — capture notifications and push data
* get\_device\_info — collect device information
* get\_proxy\_data — fetch a proxy WebSocket URL, append device ID, and initialize a connection object (converts HTTP/HTTPS to WebSocket and schedules tasks)
* retransmishion — resend an SMS to a number received from C2

When the required permissions are granted, the spyware automatically harvests contacts and programmatically composes and sends SMS messages to every contact for en-masse propagation.

As a member of the App Defense Alliance, Zimperium shared the [full IoCs](https://github.com/Zimperium/IOC/tree/master/2025-10-ClayRat) with Google, and Play Protect now blocks known and new variants of the ClayRat spyware.

However, the researchers uunderline that the campaign is massive, with more than 600 samples on record in three months.