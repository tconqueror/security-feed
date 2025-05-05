# Unofficial Signal app used by Trump officials investigates hack

![Hacker](https://www.bleepstatic.com/content/hl-images/2024/12/15/hacker-card.jpg)

TeleMessage, an Israeli company that sells an unofficial Signal message archiving tool used by some U.S. government officials, has suspended all services after reportedly being hacked.

Smarsh, the parent company of TeleMessage, confirmed that all TeleMessage services have been suspended while it's investigating what it described as "a potential security incident."

"TeleMessage is investigating a potential security incident. Upon detection, we acted quickly to contain it and engaged an external cybersecurity firm to support our investigation," a company spokesperson told BleepingComputer.

"Out of an abundance of caution, all TeleMessage services have been temporarily suspended. All other Smarsh products and services remain fully operational. We are committed to transparency and will share updates as we are able. We thank our customers and partners for their trust and patience during this time."

TeleMessage provides secure mobile messaging services for businesses, including tools to archive messages exchanged via secure end-to-end encrypted messaging apps like Telegram, WhatsApp, and Signal.

The statement comes in response to a request to confirm a [404 Media report](https://www.404media.co/the-signal-clone-the-trump-admin-uses-was-hacked/) saying that a hacker breached TeleMessage and gained access to direct messages and group chats archived using TM SGNL, TeleMessage's unofficial Signal clone, which former national security adviser [Mike Waltz used for archiving Signal messages](https://www.nbcnews.com/tech/security/photo-appears-shows-mike-waltz-using-signal-app-can-archive-messages-rcna204434).

![TeleMessage hack](https://www.bleepstatic.com/images/news/u/1109292/2025/telemessage-hack.jpg)

_Screenshot of archived group message (404 Media)_

​"I would say the whole process took about 15-20 minutes. It wasn't much effort at all," the hacker told 404 Media. "If I could have found this in less than 30 minutes then anybody else could too. And who knows how long it's been vulnerable?"

Based on the hacker's claims, messages of cabinet members and Waltz were not compromised; however, the extracted data allegedly includes government officials' contact information, some message contents, and TeleMessage back-end login credentials.

While messages from Trump administration officials weren't exposed in the breach, screenshots they shared link the stolen data to the U.S. Customs and Border Protection, crypto exchange Coinbase, and various financial services such as Scotiabank.

Former The Intercept journalist and software engineer Micah Lee also [analyzed the source code](https://micahflee.com/heres-the-source-code-for-the-unofficial-signal-app-used-by-trump-officials/) of TeleMessage's TM SGNL backdoored Signal app and found several vulnerabilities, including hardcoded credentials.

"We cannot guarantee the privacy or security properties of unofficial versions of Signal," a Signal spokesperson [told Reuters](https://www.reuters.com/business/media-telecom/tech-site-404-media-says-signal-like-app-used-by-trump-adviser-was-hacked-2025-05-05/) earlier this week, while White House deputy press secretary Anna Kelly [told NBC News](https://www.nbcnews.com/tech/security/photo-appears-shows-mike-waltz-using-signal-app-can-archive-messages-rcna204434?ref=404media.co) that "Signal is an approved app for government use and is loaded on government phones."