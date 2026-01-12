# Hidden Telegram proxy links can reveal your IP address in one click

![Telegram messenger](https://www.bleepstatic.com/content/hl-images/2021/12/08/Telegram_headpic.jpg)

A single click on what may appear to be a Telegram username or harmless link is all it takes to expose your real IP address to attackers due to how proxy links are handled.

Telegram tells BleepingComputer it will now add warnings to proxy links after researchers demonstrated that specially crafted links could be used to reveal a Telegram user's real IP address without any further confirmation.

## Careful with Telegram links

Security researchers have demonstrated this week that Telegram clients on both Android and iOS automatically attempt to connect to a proxy when a user taps a specially crafted internal link.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

These links can be disguised as ordinary usernames, for example, appearing as @durov in a Telegram message, but actually lead to a Telegram proxy _link._

Telegram proxy links (_t.me/proxy?..._) are special URLs used to quickly configure MTProto proxies in Telegram clients. They allow users to add a proxy by clicking a link instead of manually entering server details:

`https://t.me/proxy?server=[proxy IP address/hostname]&port=[proxy_port]&secret=[MTProto_secret]`

When opened in Telegram, the app reads the proxy parameters (including the server, port, and secret), and prompts the user to add the proxy to their settings.

These links are widely shared to help users bypass network blocks or internet censorship and to conceal their real location, particularly in restrictive environments, making the feature valuable to activists, journalists, and others seeking anonymity.

On Telegram's Android and iOS clients, opening a proxy link also triggers an automatic test connection, causing the app to initiate a direct network request from the user's device to the specified server before the proxy is added.

Attackers can abuse this behavior by setting up their own MTProto proxies and distributing links that are visually disguised as harmless usernames or website URLs but actually point to proxy configuration endpoints.

If a user clicks such a link on a mobile client, the Telegram app will attempt to connect to the attacker-controlled server, allowing the proxy operator to log the user's real IP address.

The exposed IP address could then be used to infer a user's approximate location, launch denial-of-service attacks, or support other targeted abuse.

The issue was brought to light by a Russian-language Telegram channel, _chekist42_ at <https://t.me/chekist42/139>:

![Telegram post that disclosed the issue](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/telegram-proxy-ip/telegram-username-real-link.jpg)

**Telegram post that first disclosed the issue** (BleepingComputer)

The proof-of-concept disguised link shown in the post was [re-shared](http://x.com/GangExposed%5FRU/status/2009961417781457129) by an X account _GangExposed RU_, thereby drawing wider attention to the issue:

`https://t[.]me/proxy?server=**1.1.1.1**&port=**53**&secret=SubscribeToGangExposed_int`

"What happens next," explains the researcher, "\[is that\] Telegram auto-pings the proxy before adding it, the request bypasses all configured proxies, \[and\] your real IP is logged instantly."

"Silent and effective targeted attack."

[0x6rss](https://x.com/0x6rss), a security research and OSINT account on X, further demonstrated the issue with a video PoC:

> ONE-CLICK TELEGRAM IP ADDRESS LEAK!  
>  
> In this issue, the secret key is irrelevant. Just like NTLM hash leaks on Windows, Telegram automatically attempts to test the proxy. Here, the secret key does not matter and the IP address is exposed.  
> Example of a link hidden behind a… <https://t.co/KTABAiuGYI> [pic.twitter.com/NJLOD6aQiJ](https://t.co/NJLOD6aQiJ)
> 
> — 0x6rss (@0x6rss) [January 10, 2026](https://twitter.com/0x6rss/status/2009977902662590787?ref%5Fsrc=twsrc%5Etfw)

The researcher compared this behavior to [NTLM hash leaks ](https://www.bleepingcomputer.com/news/security/windows-ntlm-hash-leak-flaw-exploited-in-phishing-attacks-on-governments/)on Windows, where a single interaction with a crafted resource can trigger an automatic outbound request without user awareness.

In general, IP address disclosure can enable location tracking, profiling, and targeted attacks.

In this case, the flaw requires only a single click and no additional confirmation, making it suitable for targeted deanonymization.

## Telegram downplays the issue, but will warn users

BleepingComputer contacted Telegram to ask whether it considers this behavior a vulnerability.

The company said that any website or proxy operator can see the IP address of visitors and that this is not unique to Telegram compared to other messaging platforms.

"Any website or proxy owner can see the IP address of those who access it regardless of platform," a Telegram spokesperson told BleepingComputer.

"This is not any more relevant to Telegram than WhatsApp or any other service that accesses the internet."

"That said, we're adding a warning that will show when clicking proxy links so users can be more aware of disguised links."

Telegram did not respond to follow-up questions about when the warning will be rolled out to client applications.

In the meantime, users are advised to be cautious with Telegram usernames and links that resolve to _t.me_ domains, as clicking disguised proxy links could unintentionally reveal their real IP address.