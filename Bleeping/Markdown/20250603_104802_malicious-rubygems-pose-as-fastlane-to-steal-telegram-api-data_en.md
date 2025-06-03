# Malicious RubyGems pose as Fastlane to steal Telegram API data

![RubyGems](https://www.bleepstatic.com/content/hl-images/2020/12/16/RubyGems.jpg)

Two malicious RubyGems packages posing as popular Fastlane CI/CD plugins redirect Telegram API requests to attacker-controlled servers to intercept and steal data.

RubyGems is the official package manager for the Ruby programming language, used for distributing, installing, and managing Ruby libraries (gems), similar to npm for JavaScript and PyPI for Python.

The packages intercept sensitive data, including chat IDs and message content, attached files, proxy credentials, and even bot tokens that can be used for hijacking Telegram bots.

The supply chain attack was discovered by Socket researchers, who warned the Ruby developers community about the risk via a report.

The two packages that typosquat Fastlane are still live on RubyGems under the following names:

* **fastlane-plugin-telegram-proxy**: Published on May 30, 2025, has [287 downloads](https://rubygems.org/search?query=fastlane-plugin-telegram-proxy)
* **fastlane-plugin-proxy\_teleram**: Published on May 24, 2025, has [133 downloads](https://rubygems.org/search?query=fastlane-plugin-proxy%5Fteleram)

## Fast lane to data theft

Fastlane is a legitimate open-source plugin that serves as an automation tool for mobile app developers. It is used for code signing, compiling builds, app store uploading, notification delivery, and metadata management.

The 'fastlane-plugin-telegram' is a legitimate plugin that allows Fastlane to send notifications over Telegram using a Telegram bot that posts on a specified channel.

This is helpful for developers who need real-time updates on CI/CD pipelines inside their Telegram workspace, allowing them to keep track of key events without having to check dashboards.

![Malicious result appears when searching for Fastlane](https://www.bleepstatic.com/images/news/u/1220909/2025/June/search.jpg)

**Malicious result appears when searching for Fastlane on RubyGems**  
_Source: Socket_

The malicious gems discovered by Socket are nearly identical to the legitimate plugin, featuring the same public API, readme file, documentation, and core functionality.

The only difference, albeit a crucial one, is swapping out the legitimate Telegram API endpoint (https://api.telegram.org/) with the attacker's proxy-controlled endpoint (rough-breeze-0c37\[.\]buidanhnam95\[.\]workers\[.\]dev), so that sensitive information is intercepted (and very likely collected).

![From the project description](https://www.bleepstatic.com/images/news/u/1220909/2025/June/description.jpg)

**From the project description**  
_Source: Socket_

Stolen data includes the bot token, the message data, any uploaded files, and proxy credentials if configured.

The attacker has ample opportunity for exploitation and persistence because Telegram bot tokens remain valid until manually revoked by the victim.

Socket notes that the gems' landing pages mention that the proxy "does not store or modify your bot tokens," however, there's no way to verify this claim.

"Cloudflare Worker scripts are not publicly visible, and the threat actor retains full ability to log, inspect, or alter any data in transit," [explains Socket](https://socket.dev/blog/malicious-ruby-gems-exfiltrate-telegram-tokens-and-messages-following-vietnam-ban).

"The use of this proxy, combined with the typosquatting of a trusted Fastlane plugin, clearly indicates intent to exfiltrate tokens and message data under the guise of normal CI behavior."

"Moreover, the threat actor has not published the Worker's source code, leaving its implementation entirely opaque."

Developers who have installed the two malicious gems should remove them immediately and rebuild any mobile binaries produced after the installation date. Also, all bot tokens used with Fastlane should be rotated as they have been compromised.

Socket also suggests blocking traffic to '\*.workers\[.\]dev' unless explicitly needed.