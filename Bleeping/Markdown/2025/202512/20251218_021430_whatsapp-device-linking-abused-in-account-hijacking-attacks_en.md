# WhatsApp device linking abused in account hijacking attacks

![WhatsApp device linking abused in account hijacking attacks ?](https://www.bleepstatic.com/content/hl-images/2024/11/20/Ghost-Mobile.jpg)

Threat actors are abusing the legitimate device-linking feature to hijack WhatsApp accounts via pairing codes in a campaign dubbed GhostPairing.

This type of attack does not require any authentication, as the victim is tricked into linking the attacker’s browser to a WhatsApp device.

By doing so, threat actors gain access to the full conversation history and shared media, and may leverage information to impersonate users or commit fraud.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

Gen Digital (formerly Symantec Corporation and NortonLifeLock) says that the campaign was first spotted in Czechia but warns that the propagation mechanism allows it to spread to other regions, with compromised accounts acting as springboards to reach new targets.

## How GhostPairing works

The attack starts with a short message from a known contact, sharing a link allegedly leading to an online photo of the victim. To instill some trust, the link is displayed as a content preview from Facebook.

![Malicious message sent to the target](https://www.bleepstatic.com/images/news/u/1220909/2025/December/message.jpg)

**Malicious message sent to the target**  
_Source: Gen Digital_

Furthermore, the link takes the victim to a fake Facebook page hosted on typosquatted or similar-looking domains, which informs that users need to be verified by logging in before accessing the content.

The verification page is deceptive and actually triggers WhatsApp’s device-pairing workflow. Victims are asked for their phone number, which the attacker uses to initiate a legitimate device-linking or login process.

**The fake Facebook site**  
_Source: Gen Digital_

WhatsApp generates a pairing code that the attacker displays on the fake page. WhatsApp also prompts the victim to enter the code to link the new device to their account.

While WhatsApp's message is clear that the notification is for an attempt to link a new device to the account, users are likely to miss it.

Once the victim enters the pairing code, the attacker has complete access to the account without needing to bypass any protections.

WhatsApp Web provides access to new messages in real time and allows viewing or downloading shared media. It can be used to send messages and forward the same lure to available contacts and groups.

“Many victims are unaware that a second device has been added in the background, which is what makes the scam even more dangerous – criminals are hiding in your account, watching your every conversation without you even knowing it,” [Gen Digital warns](https://www.gendigital.com/blog/insights/research/ghostpairing-whatsapp-attack).

The only way to uncover the compromise is to go to Settings → Linked Devices, and check for unauthorized devices linked to the account.

Users are encouraged to block and report suspicious messages and activate two-factor authentication account protection. If you are rushed into taking action, you should always take your time, analyze the received message, if it makes sense, and if the person contacting you is indeed who they claim.

It should be noted that linking devices is also possible by scanning a QR code using the mobile WhatsApp application.

The feature is available in multiple messaging apps and has been [exploited by Russian threat actors](https://www.bleepingcomputer.com/news/security/russian-phishing-campaigns-exploit-signals-device-linking-feature/) in the past to gain access to Signal accounts of interest.