# OpenAI discloses API customer data breach via Mixpanel vendor hack

![OpenAI discloses API customer data breach via Mixpanel vendor hack](https://www.bleepstatic.com/content/hl-images/2025/11/27/OpenAI.jpg)

OpenAI is notifying some ChatGPT API customers that limited identifying information was exposed following a breach at its third-party analytics provider Mixpanel.

Mixpanel offers event analytics that OpenAI uses to track user interactions on the frontend interface for the API product.

According to the AI company, the cyber incident affected “limited analytics data related to some users of the API” and did not impact users of ChatGPT or other products.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

“This was not a breach of OpenAI’s systems. No chat, API requests, API usage data, passwords, credentials, API keys, payment details, or government IDs were compromised or exposed,”[ OpenAI says](https://openai.com/index/mixpanel-incident/) in a press release.

Mixpanel[ reported](https://mixpanel.com/blog/sms-security-incident/) that the attack “impacted a limited number of our customers” and resulted from a smishing (SMS phishing) campaign that the company detected on November 8.

OpenAI received details of the affected dataset on November 25 after being informed of Mixpanel’s ongoing investigation.

The AI company notes that the exposed information may include:

* Name that was provided to us on the API account
* Email address associated with the API account
* Approximate coarse location based on API user browser (city, state, country)
* Operating system and browser used to access the API account
* Referring websites
* Organization or User IDs associated with the API account

Because no sensitive credentials were exposed, users do not need to reset passwords or regenerate API keys.

Some users are [reporting](https://x.com/danielh9277/status/1993878460482376011) that CoinTracker, a cryptocurrency portfolio tracker and tax platform, has also been impacted, with exposed data also including device metadata and limited transaction count.

OpenAI has started an investigation to determine the full scope of the incident. As a precaution, it has removed Mixpanel from its production services and is notifying organizations, administrators, and individual users directly.

While OpenAI underlines that only users of its API are impacted, it notified all its subscribers.

The company warns that the leaked data could be leveraged in phishing or social-engineering attacks and advises users to watch for credible-looking malicious messages related to the incident.

Messages containing links or attachments should be verified to ensure they originate from an official OpenAI domain.

The company also urges users to enable 2FA and never send sensitive information, including passwords, API keys, or verification codes, through email, text, or chat.

Mixpanel’s CEO, Jen Taylor, said that all impacted customers have been contacted directly. “If you have not heard from us, you were not impacted,” she noted.

In response to the attack, Mixpanel secured affected accounts, revoked active sessions and sign-ins, rotated compromised credentials, blocked the threat actor’s IP addresses, and reset passwords for all employees. The company has also implemented new controls to prevent similar incidents in the future.