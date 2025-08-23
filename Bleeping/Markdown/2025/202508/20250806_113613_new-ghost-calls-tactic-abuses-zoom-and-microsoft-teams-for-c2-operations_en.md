# New Ghost Calls tactic abuses Zoom and Microsoft Teams for C2 operations

![Zoom](https://www.bleepstatic.com/content/hl-images/2022/09/15/Zoom.jpg)

A new post-exploitation command-and-control (C2) evasion method called 'Ghost Calls' abuses TURN servers used by conferencing apps like Zoom and Microsoft Teams to tunnel traffic through trusted infrastructure.

Ghost Calls uses legitimate credentials, WebRTC, and custom tooling to bypass most existing defenses and anti-abuse measures, without relying on an exploit.

This new tactic was presented by [Praetorian](https://www.praetorian.com/blog/ghost-calls-abusing-web-conferencing-for-covert-command-control-part-2-of-2/)'s security researcher Adam Crosser at BlackHat USA, where it was highlighted that the new technique can be used by Red Teams when performing penetration emulation exercises.

"We leverage web conferencing protocols, which are designed for real-time, low-latency communication and operate through globally distributed media servers that function as natural traffic relays," [reads the presentation's briefing](https://www.blackhat.com/us-25/briefings/schedule/index.html#ghost-calls-abusing-web-conferencing-for-covert-command--control-45491).

"This approach allows operators to blend interactive C2 sessions into normal enterprise traffic patterns, appearing as nothing more than a temporarily joined online meeting."

## How Ghost Calls works

TURN (Traversal Using Relays around NAT) is a networking protocol commonly used by video call, VoIP, and WebRTC services that helps devices behind NAT firewalls communicate with each other when a direct connection is not possible.

When a Zoom or Teams client joins a meeting, it receives temporary TURN credentials that the Ghost Calls can hijack to set up a TURN-based WebRTC tunnel between the attacker and the victim.

This tunnel can then be used to proxy arbitrary data or disguise C2 traffic as regular video conferencing traffic through trusted infrastructure used by Zoom or Teams.

As the traffic is routed through legitimate domains and IPs that are widely used in the enterprise, malicious traffic can bypass firewalls, proxies, and TLS inspection. Additionally, WebRTC traffic is encrypted, so it's well hidden.

By abusing these tools, attackers also avoid exposing their own domains and infrastructure while enjoying high-performance, reliable connectivity, and the adaptability of using both UDP and TCP over port 443.

In comparison, traditional C2 mechanisms are slow, conspicuous, and often lack the real-time exchange capabilities required to facilitate VNC operations.

![Local port forwarding via Ghost Calls](https://www.bleepstatic.com/images/news/u/1220909/2025/July/local-port.jpg)

**Local port forwarding via Ghost Calls**  
_Source: Praetorian_

## TURNt-ing it

Crosser's research culminated with the development of a custom open-source ([available on GitHub](https://github.com/praetorian-inc/turnt/)) utility called 'TURNt' that can be used for tunneling C2 traffic via WebRTC TURN servers provided by Zoom and Teams.

TURNt consists of two components, namely a Controller running on the attacker's side, and a Relay deployed on a compromised host.

The Controller runs a SOCKS proxy server to accept connections tunneled through TURN. Relay connects back to the Controller using TURN credentials, and sets up a WebRTC data channel through the provider's TURN server.

![SOCKS proxying on TURNt](https://www.bleepstatic.com/images/news/u/1220909/2025/July/socks-turnt.jpg)

**SOCKS proxying on TURNt**  
_Source: Praetorian_

TURNt can perform SOCKS proxying, local or remote port forwarding, data exfiltration, and facilitate hidden VNC (Virtual Network Computing) traffic tunneling.

Although Ghost Calls does not exploit any vulnerabilities in Zoom or Microsoft Teams, BleepingComputer has contacted both vendors to ask if they plan to introduce additional safeguards to reduce its feasibility. We will update this post once we receive a response from either.