# Darcula PhaaS steals 884,000 credit cards via SMS phishing texts

![Phishing](https://www.bleepstatic.com/content/hl-images/2022/08/23/phishing-hook.jpg)

The Darcula phishing-as-a-service (PhaaS) platform stole 884,000 credit cards from 13 million clicks on malicious links sent via text messages to targets worldwide.

The cyber heist was done over seven months between 2023 and 2024, so it does not reflect the total amount the cybercrime platform has helped to steal.

These numbers come from coordinated research by investigators from NRK, Bayerischer Rundfunk, Le Monde, and Norwegian security firm Mnemonic, who identified 600 operators (cybercrime clients) and the platform's main creator and seller.

## Darcula's rapid rise

Darcula is a PhaaS platform that targets Android and iPhone users in over 100 countries using 20,000 domains that spoof well-known brands, aiming to steal people's account credentials.

These SMS phishing texts commonly pretend to be [road toll fines](https://www.bleepingcomputer.com/news/security/toll-payment-text-scam-returns-in-massive-phishing-wave/) or package shipping notifications that include links to phishing sites.

Netcraft researchers, who were the first to highlight the rising threat in March 2024, noted that Darcula was set apart from similar cybercrime services via its ability to use [RCS and iMessage instead of SMS](https://www.bleepingcomputer.com/news/security/new-darcula-phishing-service-targets-iphone-users-via-imessage/), which made its attacks more effective.

In February 2025, the same researchers reported that Darcula had undergone a significant evolution, now allowing operators to [auto-generate phishing kits for any brand](https://www.bleepingcomputer.com/news/security/darcula-phaas-can-now-auto-generate-phishing-kits-for-any-brand/), while also implementing new stealth features, a credit card to virtual card converter, and a simplified admin panel.

In April 2025, Netcraft saw the [introduction of generative AI](https://www.netcraft.com/blog/ai-enabled-darcula-suite-makes-phishing-kits-more-accessible-easier-to-deploy/) in Darcula, allowing cybercriminals to craft custom scams with the help of LLM tools in any language and for any topic.

![Operator phones loaded with stolen cards](https://www.bleepstatic.com/images/news/u/1220909/2025/May/phones.jpg)

**Operator phones loaded with stolen cards**  
_Source: Mnemonic_

## Lifting the lid

Mnemonic's [investigation](https://www.mnemonic.io/resources/blog/exposing-darcula-a-rare-look-behind-the-scenes-of-a-global-phishing-as-a-service-operation), which involved reverse-engineering the phishing infrastructure, led to the discovery of a powerful phishing toolkit named 'Magic Cat,' which is the backbone of the Darcula operation.

The researchers also infiltrated the Telegram group associated with the Darcula operation, uncovering photos of SIM farms, modems, and evidence of lavish lifestyles financed by the scams.

Through OSINT work and passive DNS analysis, they traced the operation's digital footprints to a Chinese individual and a GitHub developer account, among other things.

NRK [claims](http://www.nrk.no/dokumentar/xl/the-hunt-for-darcula-1.17399157) the individual is a 24-year-old from Henan, China, linked to a company that is believed to have created Magic Cat.

A spokesperson of the firm told the press that Yucheng was a former employee and denied any involvement in fraud, claiming that it only sells "website-creation software."

NRK notes that, although the company acknowledged that Magic Cat is used for phishing, and claimed they would shut it down, a new version was released.

In a [separate post](https://www.nrk.no/dokumentar/xl/inside-the-scam-network-1.17399135), NRK reveals about 600 individual scammers using Darcula to steal payment card information from victims globally, with 884,000 cards captured worldwide.

Operators are organized into closed Telegram groups, which NRK monitored for over a year, finding that most communicate in Chinese and run SIM farms and hardware setups to send mass text messages and process stolen cards via terminals.

NRK's report highlights operators with very high volumes of malicious traffic facilitated by Darcula, including a Thai-based user, 'x66/Kris,' who appears to be high in the hierarchy.

All information the researchers and investigators gathered was shared with the applicable law enforcement authorities.