# CoinMarketCap briefly hacked to drain crypto wallets via fake Web3 popup

![Cryptocurrency](https://www.bleepstatic.com/content/hl-images/2024/12/05/Cryptocurrency.jpg)

CoinMarketCap, the popular cryptocurrency price tracking site, suffered a website supply chain attack that exposed site visitors to a wallet drainer campaign to steal visitors' crypto.

On Friday evening, January 20, CoinMarketCap visitors [began seeing Web3 popups](https://twitter.com/DarkWebInformer/status/1936209452878745680) asking them to connect their wallets to the site. However, when visitors connected their wallets, a malicious script drained cryptocurrency from them.

The company later confirmed threat actors utilized a vulnerability in the site's homepage "doodle" image to inject malicious JavaScript into the site.

"On June 20, 2025, our security team identified a vulnerability related to a doodle image displayed on our homepage. This doodle image contained a link that triggered malicious code through an API call, resulting in an unexpected popup for some users when visited our homepage," reads a statement [posted on X](https://x.com/CoinMarketCap/status/1936273633611334081).

"Upon discovery, We acted immediately to remove the problematic content, identified the root cause, and comprehensive measures have been implemented to isolate and mitigate the issue."

"We can confirm all systems are now fully operational, and CoinMarketCap is safe and secure for all users."

Cybersecurity firm c/side explained that the attack worked by the threat actors somehow modifying the API used by the site to retrieve a doodle image to display on the homepage. This tampered [JSON payload](https://web.archive.org/web/20250620230124/https://static.cdnkit.io/cmc/6855a83d80876056dab0a5cf.json) now included a [malicious script tag](http://web.archive.org/web/20250620230124/https://static.cdnkit.io/cmc/popup.js) that injected a wallet drainer script into CoinMarketCap from an external site named "static.cdnkit\[.\]io".

When someone visited the page, the script would execute and display a fake wallet connect popup showing CoinMarketCap branding and mimicking a legitimate Web3 transaction request. However, this script was actually a wallet drainer designed to steal connected wallets' assets.

"This was a supply chain attack, meaning the breach didn' target CMC's own servers but a third-party tool or resource used by CMC," [explains c/side](http://medium.com/@csideai/coinmarketcap-client-side-attack-a-comprehensive-analysis-by-c-side-ce0b58e77dec).

"Such attacks are hard to detect because they exploit trusted elements of a platform."

More details about the attack came later from a threat actor [known as Rey](https://x.com/ReyXBF/status/1936276263137574931), who said that the attackers behind the CoinMarketCap supply chain attack shared a screenshot of the drainer panel on a Telegram channel.

This panel indicated that $43,266 was stolen from 110 victims as part of this supply chain attack, with the threat actors speaking in French on the Telegram channel.

![Screenshot of drainer panel shared on Telegram](https://www.bleepstatic.com/images/news/security/attacks/c/coinmarketcap/coinmarketcap/drainer-panel.jpg)

**Screenshot of drainer panel shared on Telegram**  
_Source: Rey_

As the popularity of cryptocurrency has boomed, so has the threat from wallet drainers, which are commonly used in attacks.

Unlike traditional phishing, these types of attacks are more often promoted through social media posts, advertisements, spoofed sites, and malicious browser extensions that include malicious wallet-draining scripts.

Reports indicate that [wallet drainers stole almost $500 million ](https://www.bleepingcomputer.com/news/security/cryptocurrency-wallet-drainers-stole-494-million-in-2024/)in 2024 through attacks targeting more than 300,000 wallet addresses.

The problem has become so pervasive that [Mozilla recently introduced a new system](https://www.bleepingcomputer.com/news/security/mozilla-launches-new-system-to-detect-firefox-crypto-drainer-add-ons/) to detect wallet drainers in browser add-ons uploaded to the Firefox Add-on repository.