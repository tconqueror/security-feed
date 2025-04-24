# Hackers abuse Zoom remote control feature for crypto-theft attacks

![Zoom](https://www.bleepstatic.com/content/hl-images/2022/09/15/Zoom.jpg)

A hacking group dubbed 'Elusive Comet' targets cryptocurrency users in social engineering attacks that exploit Zoom's remote control feature to trick users into granting them access to their machines.

Zoom's remote control feature allows meeting participants to take control of another participant's computer.

According to cybersecurity firm Trail of Bits, which encountered this social engineering campaign, the perpetrators mirror techniques used by the Lazarus hacking group in the [massive $1.5 billion Bybit crypto heist](https://www.bleepingcomputer.com/news/security/fbi-confirms-lazarus-hackers-were-behind-15b-bybit-crypto-heist/).

"The ELUSIVE COMET methodology mirrors the techniques behind the recent $1.5 billion Bybit hack in February, where attackers manipulated legitimate workflows rather than exploiting code vulnerabilities," explains the Trail of Bits report.

## Zoom-based interview scheme

Trail of Bits learned of this new campaign after the threat actors attempted to conduct the social engineering attack on its CEO via X direct messages.

The attack starts with an invitation to a "Bloomberg Crypto" interview via Zoom, sent to high-value targets via sock-puppet accounts on X, or via email (bloombergconferences\[@\]gmail.com).

The fake accounts impersonate crypto-focused journalists or Bloomberg outlets and reach out to the targets via direct messages on social media platforms.

![Fake accounts used in the attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/April/sockpuppets.jpg)

**Fake accounts used in the attacks**  
_Source: Trail of Bits_

The invitations are sent through Calendly links to schedule a Zoom meeting. Since both Calendly and Zoom invites/links are authentic, they work as expected and lower the target's suspicions.

![Calendly page used in the attack](https://www.bleepstatic.com/images/news/u/1220909/2025/April/calendly.jpg)

**Calendly page used for scheduling the interview**  
_Source: Trail of Bits_

During the Zoom call, the attacker initiates a screen-sharing session and sends a remote control request to the target.

The trick employed in this stage is that the attackers rename their Zoom display name to "Zoom," so the prompt the victim sees reads "Zoom is requesting remote control of your screen," making it appear as a legitimate request from the app.

**The deceptive request on Zoom**  
_Source: Trail of Bits_

However, approving the request gives the attackers full remote input control over the victim's system, allowing them to steal sensitive data, install malware, access files, or initiate crypto transactions.

The attacker may act quickly to establish persistent access by implanting a stealthy backdoor for later exploitation and disconnect, leaving victims with little chance to realize the compromise.

"What makes this attack particularly dangerous is the permission dialog's similarity to other harmless Zoom notifications," [says Trail of Bits](https://blog.trailofbits.com/2025/04/17/mitigating-elusive-comet-zoom-remote-control-attacks/).

"Users habituated to clicking "Approve" on Zoom prompts may grant complete control of their computer without realizing the implications."

To defend against this threat, Trail of Bits suggests the implementation of system-wide Privacy Preferences Policy Control (PPPC) profiles that prevent accessibility access, which is possible by using this [collection of tools](https://github.com/trailofbits/it-releases).

The firm recommends removing Zoom entirely from all systems for security-critical environments and organizations that handle valuable digital assets.

"For organizations handling particularly sensitive data or cryptocurrency transactions, the risk reduction from eliminating the Zoom client entirely often outweighs the minor inconvenience of using browser-based alternatives," explains Trail of Bits.