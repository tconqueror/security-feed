# Threat actors abuse X’s Grok AI to spread malicious links

![X](https://www.bleepstatic.com/content/hl-images/2024/01/05/X-logo-flare.jpg)

Threat actors are using Grok, X's built-in AI assistant, to bypass link posting restrictions that the platform introduced to reduce malicious advertising.

As discovered by Guardio Labs' researcher [Nati Tal](https://x.com/bananahacks/status/1963184353250353488), mavertisers often run sketchy video ads containing adult content baits and avoid including a link to the main body to avoid being blocked by X.

Instead, they hide it in the small "From:" metadata field under the video card, which apparently isn't scanned by the social media platform for malicious links.

![Hiding the malicious link in an ignored field](https://www.bleepstatic.com/images/news/u/1220909/2025/August/2.jpeg)

**Hiding the malicious link in an ignored field**  
_Source: [@bananahacks](https://x.com/bananahacks)_

Next, (likely) the same actors ask Grok via a reply to the ad something about the post, like "where is this video from," or "what is the link to this video."

Grok parses the hidden "From:" field and replies with the full malicious link in clickable format, allowing users to click it and go straight to the malicious site.

![Replies triggering a Grok response](https://www.bleepstatic.com/images/news/u/1220909/2025/August/reply.jpeg)

**Replies triggering a Grok response**  
_Source: [@bananahacks](https://x.com/bananahacks)_: 

Because Grok is automatically a trusted system account on the X platform, its post boosts the link's credibility, reach, SEO, and reputation, increasing the likelihood that it will be broadcast to a large number of users.

The researcher has found that many of these links funnel through shady ad networks, leading to scams such as fake CAPTCHA tests, information-stealing malware, and other malicious payloads.

Instead of being blocked by X, they are instead promoted to users on the platform via malicious ads that receive a further boost from Grok.

Tal calls the technique of exploiting this loophole "Grokking," and notes that it's very effective, in some cases amplifying malicious ads to reach millions of impressions, as shown below.

**Reaching millions of impressions**  
_Source: [@bananahacks](https://x.com/bananahacks)_

Potential solutions include scanning all fields, blocking hidden links, and adding context sanitization to Grok, so the AI assistant does not blindly echo links when asked by users, but instead filters and checks them against blocklists.

Tal confirmed to us that he has contacted X to report the issue and received unofficial confirmation that Grok engineers received the report. 

BleepingComputer has also contacted X to ask if they're aware of this abuse and whether they plan to do anything about it, but we received no response by publication time.