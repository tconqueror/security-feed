# Brave's Cookiecrumbler tool taps community to help block cookie notices

![Brave](https://www.bleepstatic.com/content/hl-images/2022/06/22/Brave.jpg)

Brave has open-sourceed a new tool called "Cookiecrumbler," which uses large language models (LLMs) to detect cookie consent notices and then community-driven reviews to block those that won't break site functionality.

The Brave browser has been blocking cookie consent banners by default on all websites [since 2022](https://www.bleepingcomputer.com/news/security/brave-browser-to-start-blocking-annoying-cookie-consent-banners/) but found that blocking consent banners may cause website problems that severely disrupt and degrade the site's usability.

"Overly broad or incorrect blocking can break essential website functionality, from checkout flows to layout problems," [explains Brave](https://brave.com/privacy-updates/33-cookiecrumbler/).

"We've encountered many issues (broken scrolling, blank pages) when a cookie consent notice block is applied indiscriminately."

Cookiecrumbler uses AI to find websites utilizing consent management platforms (CMPs) and report them as issues in its GitHub Project. Cookiecrumbler's suggestions are then reviewed manually before applying to avoid breaking essential site functionality.

The way the tool works is summarized as follows:

1. Crawls top websites using regional proxies.
2. Loads pages with Puppeteer to find potential cookie notices.
3. Passes these to the LLM for classification and suggestions for fixing.
4. Publishes detection results as [GitHub issues](https://github.com/brave-experiments/cookiecrumbler-issues/issues) for community triage and improvement.

Essentially, Cookiecrumbler enables large-scale, regionally aware cookie banner detection and blocking while reducing false positives and site problems.

Being a privacy-focused software, Brave's announcement makes several points about how Cookiecrumbler's operation does not expose sensitive details.

First, it is clarified that Cookiecrumber runs entirely on Brave's backend, and not on the user's browser, which means no user data is involved in its detection and analysis process.

Secondly, the tool does not interact with the actual user sessions; instead, it uses proxies and automated crawlers to simulate browsing from different regions using public site lists like Tranco.

Ultimately, privacy preservation is the main reason why Cookiecrumbler is currently not baked into the Brave browser but instead is used internally as a backend tool for analysis.

Brave Software says Cookiecrumbler will be integrated into Brave only after it has gone through a full privacy review that ensures its operation adheres to the software's strict stance on user privacy.

With Cookiecrumbler being open-source and free [via GitHub](https://github.com/brave/cookiecrumbler/), it can be used directly by other privacy tool developers, website auditors, adblock list maintainers, or even tech-savvy users who want to generate or improve their own filter rules.