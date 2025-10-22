# PhantomCaptcha ClickFix attack targets Ukraine war relief orgs

![PhantomCaptcha ClickFix attack targets Ukraine war relief orgs](https://www.bleepstatic.com/content/hl-images/2024/12/15/hacker-card.jpg)

A spearphishing attack that lasted a single day targeted members of the Ukrainian regional government administration and organizations critical for the war relief effort in Ukraine, including the International Committee of the Red Cross, UNICEF, and various NGOs.

Dubbed PhantomCaptcha, the one-day campaign attempted to trick victims into running commands used in ClickFix attacks, disguised as Cloudflare CAPTCHA verification prompts, to install a WebSocket Remote Access Trojan (RAT).

SentinelLABS, the threat research division at SentinelOne, says that the campaign started and ended on October 8, and that the attacker spent significant time and effort to set up the necessary infrastructure, as some domains used in the operation were registered at the end of March.

### "I am not a robot" ClickFix attacks

The attacks started with emails impersonating the Ukrainian President’s Office, carrying malicious PDF attachments that linked to a domain impersonating the Zoom (zoomconference\[.\]app) communication platform.

![Spear-phishing email sent to targets](https://www.bleepstatic.com/images/news/u/1220909/2025/October/email.jpg)

**Spear-phishing email sent to targets**  
_Source: SentinelLabs_

When clicking on the fake Zoom conference link, visitors saw an automated browser check process before redirecting to the communication platform.

During this stage, a client identifier is generated and passed to the attacker's server over a Websocket connection.

![Fake Cloudflare CAPTCHA page](https://www.bleepstatic.com/images/news/u/1220909/2025/October/captcha.jpg)

**Fake Cloudflare CAPTCHA page**  
_Source: SentinelLabs_

"If the WebSocket server responded with a matching identifier, the victim’s browser would redirect to a legitimate, password-protected Zoom meeting," [SentinelLABS' analysis showed](https://www.sentinelone.com/labs/phantomcaptcha-multi-stage-websocket-rat-targets-ukraine-in-single-day-spearphishing-operation/).

According to the researchers, this path likely led to the threat actor engaging in live social engineering calls with the victim.

If the client ID did not match, visitors had to pass another security check and prove that they were real people and not robots.

They could complete the fake CAPTCHA verification by following instructions in Ukrainian that prompted them to press a button to copy a "token" and paste it in the Windows Command Prompt.

**ClickFix instructions**  
_Source: SentinelLabs_

What the copy/paste action did was to run a PowerShell command that downloaded and executed a malicious script (_cptch_) for delivering the second-stage payload, a reconnaissance and system-profiler utility.

The tool collects system data like computer name, domain information, username, process ID, and system UUID, and sends it to the command-and-control (C2) server.

The final payload is a lightweight WebSocket RAT capable of remote command execution and data exfiltration through base64-encoded JSON commands.

**The two infection paths used in the attack**  
_Source: SentinelLabs_

The researchers found that the short-lived campaign was linked to a subsequent operation that targeted users in Lviv, Ukraine, with adult-themed Android APKs or cloud storage tools.

These apps act as spyware, monitoring the victim’s real-time location, call logs, contact list, and images, exfiltrating them to the attackers.

While SentinelLABS made no attribution for the "I am not a robot" ClickFix attacks, the researchers note that the WebSocket RAT was hosted on Russian infrastructure, and the adult-themed campaign may be related to Russia/Belarus source development.

Additionally, a report from the Google Threat Intelligence Group (GTIG) yesterday describes a malicious ["I am not a robot" captcha challenge](https://www.bleepingcomputer.com/news/security/russian-hackers-evolve-malware-pushed-in-i-am-not-a-robot-clickfix-attacks/) used in attacks attributed to ColdRiver (a.k.a. Star Blizzard, UNC4057, Callisto), a threat group attributed to the Russian intelligence service (FSB).

GTIG highlighted that the hackers were quick to operationalize new malware families after researchers had disclosed publicly older tools that ColdRiver deployed in cyberespionage activities.