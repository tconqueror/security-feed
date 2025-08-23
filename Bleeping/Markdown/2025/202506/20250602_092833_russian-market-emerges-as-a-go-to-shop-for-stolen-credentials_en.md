# ‘Russian Market’ emerges as a go-to shop for stolen credentials

![Shop](https://www.bleepstatic.com/content/hl-images/2023/12/12/shop.jpg)

The "Russian Market" cybercrime marketplace has emerged as one of the most popular platforms for buying and selling credentials stolen by information stealer malware.

Although the marketplace has been active for roughly six years and became relatively popular by 2022, [ReliaQuest reports](https://reliaquest.com/resources/research-reports/stolen-credential-attacks-russian-marketplace/) that the Russian Market has recently reached new heights. Part of this surge in popularity is due to the [takedown of the Genesis Market](https://www.bleepingcomputer.com/news/security/fbi-seizes-stolen-credentials-market-genesis-in-operation-cookie-monster/), which created a large vacuum in the field.

Although the majority (85%) of credentials sold on the Russian Market are "recycled" from existing sources, it has still won massive cybercrime audiences thanks to its wide selection of items of sale and availability of logs at prices as low as $2.

An infostealer log is commonly a text file, or multiple files, created by infostealer malware that contains the account passwords, session cookies, credit card data, cryptocurrency wallet data, and system profiling data stolen from an infected device.

Each log can contain dozens or even thousands of credentials, so the total number of stolen credentials could be hundreds of millions or more. Once collected, the logs are uploaded back to an attacker's server, where they are collected for use in further malicious activity or sold on marketplaces like the Russian Market.

![Logs on the marketplace](https://www.bleepstatic.com/images/news/u/1220909/2025/May/market-logs.jpg)

**Logs page on the marketplace**  
_Source: ReliaQuest_

Infostealers have become an immensely popular tool for threat actors, with [many campaigns](https://www.bleepingcomputer.com/news/security/north-korean-hackers-adopt-clickfix-attacks-to-target-crypto-firms/) now [targeting the enterprise](https://www.bleepingcomputer.com/news/security/fake-google-meet-conference-errors-push-infostealing-malware/) to steal session cookies and corporate credentials.

ReliaQuest says this is reflected in the Russian Market, with 61% of the stolen logs containing SaaS credentials from platforms like Google Workspace, Zoom, and Salesforce. Also, 77% of the logs included SSO (Single Sign-On) credentials.

"Compromised cloud accounts afford attackers access to critical systems and present the perfect opportunity to steal sensitive data," explains the researchers.

## Lumma falters, Acreed rises

ReliaQuest analyzed over 1.6 million posts on the Russian Market to graph the rise and fall in popularity of specific info-stealing malware.

Until recently, most logs were stolen by Lumma stealer, which accounts for 92% of all credential logs sold on the Russian Market.

![Infostealer logs percentage of Russian Market](https://www.bleepstatic.com/images/news/u/1220909/2025/May/percentage.jpg)

**Infostealer logs percentage of Russian Market**  
_Source: ReliaQuest_

Lumma dominated the market after the collapse of Raccoon Stealer, following [law enforcement action](https://www.bleepingcomputer.com/news/security/raccoon-stealer-malware-operator-gets-5-years-in-prison-after-guilty-plea/). However, the same fate could be unfolding for Lumma, as its operations were recently [disrupted by a global law enforcement operation](https://www.bleepingcomputer.com/news/security/lumma-infostealer-malware-operation-disrupted-2-300-domains-seized/) where 2,300 domains were seized.

The long-term results of this operation remain unclear, and [Check Point reported](https://blog.checkpoint.com/security/lumma-infostealer-down-but-not-out/) that Lumma's developers are currently attempting to rebuild and restart their cybercrime operations.

In the meantime, ReliaQuest reports seeing a sudden rise of a new infostealer named Acreed, which is rapidly gaining traction following the takedown of Lumma.

Acreed's swift ascent in the Russian Market is reflected in the over 4,000 logs uploaded within its first week of operations, [according to Webz](https://webz.io/dwp/acreed-infostealer-everything-we-know-so-far/).

Acreed isn't different from a typical info-stealer regarding the information it targets, which includes data stored in Chrome, Firefox, and their various derivatives, including passwords, cookies, cryptocurrency wallets, and credit card details.

Info-stealers are infecting users via phishing emails, "ClickFix" attacks, malvertising for premium software, and YouTube or TikTok videos. So, vigilance and good software download practices are recommended to avoid this widespread risk.