# Microsoft: Russian hackers use ISP access to hack embassies in AiTM attacks

![Russian hackers](https://www.bleepstatic.com/content/hl-images/2023/11/08/Russian_hacker_headpic.jpg)

Microsoft warns that a cyber-espionage group linked to Russia's Federal Security Service (FSB) is targeting diplomatic missions in Moscow using local internet service providers.

The hacking group tracked by Microsoft as Secret Blizzard (also known as Turla, Waterbug, and Venomous Bear) has been observed exploiting its adversary-in-the-middle (AiTM) position at the internet service provider (ISP) level to infect the systems of diplomatic missions with custom ApolloShadow malware.

To do this, they redirect targets to captive portals, tricking them into downloading and executing the malware. While Microsoft first detected the attacks in February 2025, the company believes this cyber-espionage campaign has been active since at least 2024.

Once deployed, ApolloShadow installs a trusted root certificate disguised as Kaspersky Anti-Virus, which helps trick compromised devices into recognizing malicious websites as legitimate, allowing threat actors to maintain long-term access for intelligence gathering after infiltrating diplomatic systems.

"This is the first time Microsoft can confirm Secret Blizzard's capability to conduct espionage at the ISP level, meaning diplomatic personnel using local internet providers and telecommunications in Russia are at high risk of being targets of Secret Blizzard's AiTM position within those services," Microsoft said.

"This campaign, which has been ongoing since at least 2024, poses a high risk to foreign embassies, diplomatic entities, and other sensitive organizations operating in Moscow, particularly to those entities who rely on local internet providers."

![Secret Blizzard infection chain](https://www.bleepstatic.com/images/news/u/1109292/2025/Secret_Blizzard_infection_chain.jpg)

_Secret Blizzard infection chain (Microsoft)_

Secret Blizzard hackers are also [taking advantage of Russia's domestic interception systems](http://www.microsoft.com/en-us/security/blog/2024/12/04/frequent-freeloader-part-i-secret-blizzard-compromising-storm-0156-infrastructure-for-espionage/), including the System for Operative Investigative Activities (SORM), to carry out their large-scale AiTM campaigns.

## Unorthodox cyberspies focused on high-profile targets

Turla has been orchestrating cyber-espionage and information theft campaigns targeting embassies, governments, and research facilities across over 100 countries since at least 1996.

Two years ago, CISA [linked](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-129a) the group to Center 16 of Russia's Federal Security Service (FSB) and a peer-to-peer (P2P) network of computers infected with Snake cyber-espionage malware that was later [taken down](https://www.bleepingcomputer.com/news/security/fbi-nukes-russian-snake-data-theft-malware-with-self-destruct-command/) in a joint action involving Five Eyes cybersecurity and intelligence agencies.

These Russian state-backed hackers are also the primary suspects behind attacks targeting the [U.S. Central Command](https://www.nytimes.com/2010/08/26/technology/26cyber.html), [NASA](https://www.kaspersky.com/blog/moonlight-maze-the-lessons/6713/), [the Pentagon](https://www.kaspersky.com/blog/moonlight-maze-the-lessons/6713/), multiple [Eastern European Ministries of Foreign Affairs](https://www.welivesecurity.com/wp-content/uploads/2020/05/ESET%5FTurla%5FComRAT.pdf), the [Finnish Foreign Ministry](https://yle.fi/uutiset/osasto/news/russian%5Fgroup%5Fbehind%5F2013%5Fforeign%5Fministry%5Fhack/8591548), and [EU governments and embassies](https://www.bleepingcomputer.com/news/security/russian-turla-hackers-breach-european-government-organization/).

This threat group is known for its unconventional tactics, including the control of malware through [comments on Britney Spears' Instagram photos](https://www.bleepingcomputer.com/news/security/russian-state-hackers-use-britney-spears-instagram-posts-to-control-malware/) and the use of [backdoor trojans with their own APIs](https://www.bleepingcomputer.com/news/security/cyber-espionage-malware-is-so-advanced-it-has-its-own-api/).

Turla also utilized the [hijacked infrastructure and malware of the Iranian APT OilRig](https://www.bleepingcomputer.com/news/security/russian-hackers-use-iranian-threat-groups-tools-servers-as-cover/) in their own campaigns to mislead and deceive defenders into attributing their attacks to Iranian state hackers.

Most recently, they've also been spotted hijacking the infrastructure of [Pakistani threat actor Storm-0156](https://www.bleepingcomputer.com/news/security/russian-cyber-spies-hide-behind-other-hackers-to-target-ukraine/) to target Ukrainian military devices connected via Starlink.