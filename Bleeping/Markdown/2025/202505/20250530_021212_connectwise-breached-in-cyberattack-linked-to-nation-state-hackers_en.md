# ConnectWise breached in cyberattack linked to nation-state hackers

![ConnectWise](https://www.bleepstatic.com/content/hl-images/2025/05/29/connectwise-logo.jpg)

IT management software firm ConnectWise says a suspected state-sponsored cyberattack breached its environment and impacted a limited number of ScreenConnect customers.

"ConnectWise recently learned of suspicious activity within our environment that we believe was tied to a sophisticated nation state actor, which affected a very small number of ScreenConnect customers," ConnectWise shared in a [brief advisory](https://www.connectwise.com/company/trust/advisories#:~:text=May%2028%2C%202025%20Security%20Event%20Advisory).

"We have launched an investigation with one of the leading forensic experts, Mandiant. We have contacted all affected customers and are coordinating with law enforcement."

ConnectWise is a Florida-based software company that provides IT management, RMM (remote monitoring and management), cybersecurity, and automation solutions for managed service providers (MSPs) and IT departments.

One of its products is ScreenConnect, a remote access and support tool that allows technicians to securely connect to client systems for troubleshooting, patching, and system maintenance.

As first reported by [CRN](https://www.crn.com/news/channel-news/2025/connectwise-confirms-screenconnect-cyberattack-says-systems-now-secure-exclusive?itc=refresh), the company now says it has implemented enhanced monitoring and hardened the security across its network.

They also state that they have not seen any further suspicious activity in customer instances.

ConnectWise did not answer BleepingComputer's questions about how many customers were impacted, when the breach occurred, or whether any malicious activity was observed in customers' ScreenConnect instances.

However, a source told BleepingComputer that the breach occurred in August 2024, with ConnectWise discovering the suspicious activity in May 2025, and that it only impacted cloud-based ScreenConnect instances.

In a [Reddit thread](https://www.reddit.com/r/msp/comments/1kxpwrn/connectwise%5Fconfirms%5Fscreenconnect%5Fcyberattack/), customers said the incident is linked to a ScreenConnect vulnerability tracked as [CVE-2025-3935](http://www.connectwise.com/company/trust/security-bulletins/screenconnect-security-patch-2025.4), patched on April 24.

The CVE-2025-3935 flaw is a high-severity ViewState code injection bug caused by unsafe deserialization of ASP.NET ViewState in ScreenConnect versions 25.2.3 and earlier.

Threat actors with privileged system-level access can steal the secret machine keys used by a ScreenConnect server and utilize them to craft malicious payloads that trigger remote code execution on the server.

While ConnectWise did not state that this vulnerability was exploited at the time, it was marked as "High" priority, indicating it was either actively exploited or carried a significant risk of exploitation.

The company also stated that the flaw was patched on its cloud-hosted ScreenConnect platforms at "screenconnect.com" and "hostedrmm.com" before it was publicly disclosed to customers.

As the breach only impacted cloud-hosted ScreenConnect instances, it's possible that threat actors first breached ConnectWise's systems and stole the machine keys.

Using those keys, attackers could conduct remote code execution on the company's ScreenConnect servers and potentially access customer environments.

However, it should be noted that ConnectWise has not confirmed whether this was how customer's instances were breached.

BleepingComputer sent additional questions to ConnectWise but has not heard back at this time.