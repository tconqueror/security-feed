# New ‘IndonesianFoods’ worm floods npm with 100,000 packages

![New ‘IndonesianFoods’ worm floods npm with 100,000 packages](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_head_pic.jpg)

A self-spreading package published on npm spams the registry by spawning new packages every every seven seconds, creating large volumes of junk.

The worm, dubbed ‘IndonesianFoods,’ due to its distinctive package naming scheme that picks random Indonesian names and food terms, has published over 100,000 packages according to Sonatype, and the number is growing exponentially.

Although the packages do not have a malicious component for developers (e.g., stealing data, backdooring hosts), this could change with an update that introduces a dangerous payload.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

The level of automation and large-scale nature of the attack create the potential for broad supply-chain compromise.

Security researcher Paul McCarty, who [first reported](https://sourcecodered.com/indonesianfoods-npm-worm/) this spam campaign, [created a page](https://github.com/6mile/Indonesian-Foods-Worm) to track the offending npm publishers and the number of packages they have released on the platform.

Sonatype [reports](https://www.sonatype.com/blog/unprecedented-automation-indonesianfoods-pits-open-source-against-itself) that the same actors performed another attempt on September 10, with a package named ‘fajar-donat9-breki.’ Although that package contained the same replication logic, it failed to spread.

“This attack has overwhelmed multiple security data systems, demonstrating unprecedented scale,” Sonatype’s principal security researcher, Garret Calpouzos, told BleepingComputer.

“Amazon Inspector is flagging these packages through OSV advisories, triggering a massive wave of vulnerability reports. Sonatype’s database alone saw 72,000 new advisories in a single day.”

The researcher commented that IndonesianFoods does not appear to focus on infiltrating developer machines, but rather to stress the ecosystem and disrupt the world’s largest software supply chain.

“The motivation is unclear, but the implications are striking,” noted Calpouzos.

A [report from Endor Labs](https://www.endorlabs.com/learn/the-great-indonesian-tea-theft-analyzing-a-npm-spam-campaign) on the IndonesianFoods campaign mentions that some packages appear to abuse the TEA Protocol, a blockchain system that rewards OSS contributions with TEA tokens, containing _tea.yaml_ files listing TEA accounts and wallet addresses.

By publishing thousands of interconnected packages, attackers inflated their impact scores to earn more tokens, indicating a financial motive behind the attack.

![The auto-publishing function](https://www.bleepstatic.com/images/news/u/1220909/2025/November/name-publish.jpg)

**The auto-publishing function**  
_Source: Endor Labs_

Also, Endor Labs reports that the spam campaign actually began two years ago, with 43,000 packages being added in 2023, TEA monetization being implemented in 2024, and the worm-like replication loop introduced in 2025.

The IndonesianFoods campaign comes in the context of several similar automation-based supply-chain attacks on open-source ecosystems, including the [GlassWorm attack](https://www.bleepingcomputer.com/news/security/self-spreading-glassworm-malware-hits-openvsx-vs-code-registries/) on OpenVSX, the [Shai-Hulud worm](https://www.bleepingcomputer.com/news/security/self-propagating-supply-chain-attack-hits-187-npm-packages/) employing dependency confusion propagation, and the hijacks of widely used packages [like chalk and debug](https://www.bleepingcomputer.com/news/security/hackers-hijack-npm-packages-with-2-billion-weekly-downloads-in-supply-chain-attack/).

Individually, these incidents [caused limited damage](https://www.bleepingcomputer.com/news/security/hackers-left-empty-handed-after-massive-npm-supply-chain-attack/), but they highlight a new trend in which attackers increasingly exploit automation and scale to overwhelm open-source ecosystems.

Sonatype also warned that these simple yet impactful operations create ideal conditions for threat actors to slip in more serious malware into open-source ecosystems.

As the attack continues to unfold, software developers are advised to lock down dependency versions, monitor for abnormal publishing patterns, and implement strict digital signature validation policies.