# Cloudflare blames today's outage on emergency React2Shell patch

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2025/09/02/Cloudflare.jpg)

Earlier today, [Cloudflare experienced a widespread outage](https://www.bleepingcomputer.com/news/technology/cloudflare-down-websites-offline-with-500-internal-server-error/) that caused websites and online platforms worldwide to go down, returning a "500 Internal Server Error" message.

In a status page update, the internet infrastructure company has now blamed the incident on an emergency patch designed to address a critical remote code execution vulnerability in React Server Components, which is now actively exploited in attacks.

"A change made to how Cloudflare's Web Application Firewall parses requests caused Cloudflare's network to be unavailable for several minutes this morning," [Cloudflare said](https://www.cloudflarestatus.com/incidents/lfrm31y6sw9q#:~:text=Posted%204%20hours%20ago%2E%20Dec%2005%2C%202025%20%2D%2009%3A20%20UTC).

"This was not an attack; the change was deployed by our team to help mitigate the industry-wide vulnerability disclosed this week in React Server Components. We will share more information as we have it today."

Tracked as [CVE-2025-55182](https://www.bleepingcomputer.com/news/security/critical-react2shell-flaw-in-react-nextjs-lets-hackers-run-javascript-code/), this maximum severity security flaw (dubbed React2Shell) affects the React open-source JavaScript library for web and native user interfaces, as well as dependent React frameworks such as Next.js, React Router, Waku, @parcel/rsc, @vitejs/plugin-rsc, and RedwoodSDK.

The vulnerability was found in the React Server Components (RSC) 'Flight' protocol, and it allows unauthenticated attackers to gain remote code execution in React and Next.js applications by sending maliciously crafted HTTP requests to React Server Function endpoints.

While multiple React packages in their default configuration (i.e., react-server-dom-parcel, react-server-dom-turbopack, and react-server-dom-webpack) are vulnerable, the flaw only affects React versions 19.0, 19.1.0, 19.1.1, and 19.2.0 released during the past year.

## Ongoing React2Shell exploitation

Although the impact is not as widespread as initially believed, security researchers with Amazon Web Services (AWS) have reported that multiple China-linked hacking groups (including Earth Lamia and Jackpot Panda) [have begun exploiting the React2Shell vulnerability](https://www.bleepingcomputer.com/news/security/react2shell-critical-flaw-actively-exploited-in-china-linked-attacks/) hours after the max-severity flaw was disclosed.

The NHS England National CSOC also [said on Thursday](https://digital.nhs.uk/cyber-alerts/2025/cc-4723) that several functional CVE-2025-55182 [proof-of-concept exploits](http://x.com/stephenfewer/status/1996697494525264219) are [already available](https://x.com/dez%5F/status/1996720660505145810) and warned that "continued successful exploitation in the wild is highly likely."

Last month, Cloudflare experienced [another worldwide outage](https://www.bleepingcomputer.com/news/technology/cloudflare-blames-this-weeks-massive-outage-on-database-issues/) that brought down the company's Global Network for almost 6 hours, an incident described by CEO Matthew Prince as the "worst outage since 2019."

Cloudflare [fixed another massive outage](https://www.bleepingcomputer.com/news/technology/google-cloud-and-cloudflare-hit-by-widespread-service-outages/) in June, which caused Access authentication failures and Zero Trust WARP connectivity issues across multiple regions, and also impacted Google Cloud's infrastructure.