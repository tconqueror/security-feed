# 60 malicious Ruby gems downloaded 275,000 times steal credentials

![Ruby](https://www.bleepstatic.com/content/hl-images/2020/12/16/RubyGems.jpg)

Sixty malicious Ruby gems containing credential-stealing code have been downloaded over 275,000 times since March 2023, targeting developer accounts.

The malicious Ruby gems were discovered by Socket, which reports they targeted primarily South Korean users of automation tools for Instagram, TikTok, Twitter/X, Telegram, Naver, WordPress, and Kakao.

RubyGems is the official package manager for the Ruby programming language, enabling the distribution, installation, and management of Ruby libraries, known as gems, much like npm for JavaScript or PyPI for Python.

The malicious gems in this campaign were published onto RubyGems.org under various aliases over the years. The offending publishers are zon, nowon, kwonsoonje, and soonje, spreading the activity over multiple accounts to make the activity harder to trace and block.

The full list of the malicious packages can be found in [Socket's report](https://socket.dev/blog/60-malicious-ruby-gems-used-in-targeted-credential-theft-campaign), but below are some notable cases of deceptively named or typosquatted packages:

* WordPress-style automators: wp\_posting\_duo, wp\_posting\_zon
* Telegram-style bots: tg\_send\_duo, tg\_send\_zon
* SEO/backlink tools: backlink\_zon, back\_duo
* Blog platform mimics: nblog\_duo, nblog\_zon, tblog\_duopack, tblog\_zon
* Naver Café interaction tools: cafe\_basics\[\_duo\], cafe\_buy\[\_duo\], cafe\_bey, \*\_blog\_comment, \*\_cafe\_comment

All 60 gems highlighted in the Socket report present a graphical user interface (GUI) that appears legitimate, as well as the advertised functionality.

In practice, however, they act as phishing tools that exfiltrate the credentials users enter on the login form to the attackers on a hardcoded command-and-control (C2) address (programzon\[.\]com, appspace\[.\]kr, marketingduo\[.\]co\[.\]kr).

![Malicious code snippet present in the 60 gems](https://www.bleepstatic.com/images/news/u/1220909/2025/August/code.jpg)

**Malicious code snippet present in the 60 gems**  
_Source: Socket_

The harvested data includes usernames and passwords in plaintext, device MAC addresses for fingerprinting, and the package name for campaign performance tracking.

In some cases, the tools respond with a fake success or failure message, although no real login or API call to the actual service is made.

Socket has found credential logs on Russian-speaking darknet markets that appear to derive from these gems, based on interactions with marketingduo\[.\]co\[.\]kr, a dubious marketing tool site tied to the attacker.

![Infostealer logs linked to the campaign](https://www.bleepstatic.com/images/news/u/1220909/2025/August/logs.jpg)

**Infostealer logs linked to the campaign**  
_Source: Socket_

The researchers say that at least 16 of the 60 malicious Ruby gems remain available, although they have reported them all to the RubyGems team upon discovery.

Supply chain attacks on RubyGems aren't unprecedented, and they have been going on [for several years now](https://www.bleepingcomputer.com/news/security/malicious-rubygems-packages-used-in-cryptocurrency-supply-chain-attack/).

In June, Socket [reported another case](https://www.bleepingcomputer.com/news/security/malicious-rubygems-pose-as-fastlane-to-steal-telegram-api-data/) of malicious Ruby gems that typosquatted Fastlane, a legitimate open-source plugin that serves as an automation tool for mobile app developers, targeting Telegram bot developers specifically.

Developers should scrutinize libraries they source from open-source repositories for signs of suspicious code like obfuscated parts, consider the publisher's reputation and release history, and lock dependencies to 'known to be safe' versions.