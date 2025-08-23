# Pi-hole discloses data breach via GiveWp WordPress plugin flaw

![Pi-hole](https://www.bleepstatic.com/content/hl-images/2025/08/01/Pi-hole-headpic.jpg)

Pi-hole, a popular network-level ad-blocker, has disclosed that donor names and email addresses were exposed through a security vulnerability in the GiveWP WordPress donation plugin.

Pi-hole acts as a DNS sinkhole, filtering out unwanted content before it reaches the users' devices. While initially designed to run on Raspberry Pi single-board computers, it now supports various Linux systems on dedicated hardware or virtual machines.

The organization stated that they first learned of the incident on Monday, July 28, after donors [began reporting](https://www.reddit.com/r/pihole/comments/1mbks5z/pihole%5Fdonation%5Femail%5Frecipient%5Flist%5Fleaked/) that they were receiving suspicious emails at [addresses used exclusively for donations](https://www.reddit.com/r/pihole/comments/1mblu68/spam%5Fcoming%5Fto%5Fme%5Ffrom%5Femail%5Fonly%5Fused%5Fwith/).

As explained in a [Friday post-mortem](http://pi-hole.net/blog/2025/07/30/compromised-donor-emails-a-post-mortem/), the breach affected users who donated through the Pi-hole website's donation form to support development, exposing personal information that was visible to anyone who viewed the webpage's source code due to a GiveWP security flaw.

[The vulnerability](https://github.com/impress-org/givewp/issues/8042) stemmed from GiveWP, a WordPress plugin used to process donations on the Pi-hole website. The plugin inadvertently made donor information publicly accessible without requiring authentication or special access privileges.

While Pi-hole didn't disclose the number of affected customers, the 'Have I Been Pwned' data breach notification service added the Pi-hole breach, saying that it impacted almost 30,000 donors, with 73% of the exposed records already in its database.

[![https://bsky.app/profile/haveibeenpwned.com/post/3lvca3viu322x](https://www.bleepstatic.com/images/news/u/1109292/2025/HIBP-Pi-hole.png)](https://bsky.app/profile/haveibeenpwned.com/post/3lvca3viu322x)

## No financial information exposed

Pi-hole added that no donor financial data was compromised, as credit card information and other payment details are handled directly by Stripe and PayPal. It also clarified that the Pi-hole software product itself was not affected in any way.

"We make it clear in the donation form that we don't even require a valid name or email address, it's purely for users to see and manage their donations," [Pi-hole said](https://pi-hole.net/blog/2025/07/30/compromised-donor-emails-a-post-mortem/). "It is also important to note that Pi-hole the product is categorically not the subject of this breach. There is no action needed from users with a Pi-hole installed on their network."

Although GiveWP released a patch within hours of the vulnerability being reported on GitHub, Pi-hole criticized the plugin developer's response, citing a 17.5-hour delay before notifying users and what it described as insufficient acknowledgment of the security flaw's potential impact on donor names and email addresses.

Pi-hole apologized to affected donors and acknowledged potential reputation damage stemming from this security incident, saying that while the vulnerability was unforeseeable, they accept accountability for the resulting data breach.

"The names and email addresses of anyone that had ever donated via our donation page was there for the entire world to see (provided they were savvy enough to right click->View page source). Within a couple of hours of this report, they had patched the bad code and released 4.6.1," Pi-hole added in a blog post analyzing the incident.

"We take full responsibility for the software we deploy. We placed our trust in a widely-used plugin, and that trust was broken."