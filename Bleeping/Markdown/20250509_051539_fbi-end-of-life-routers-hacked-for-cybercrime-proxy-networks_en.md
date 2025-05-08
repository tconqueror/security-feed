# FBI: End-of-life routers hacked for cybercrime proxy networks

![FBI](https://www.bleepstatic.com/content/hl-images/2022/12/16/FBI__headpic.jpg)

The FBI warns that threat actors are deploying malware on end-of-life (EoL) routers to convert them into proxies sold on the 5Socks and Anyproxy networks.

These devices, which were released many years back and no longer receive security updates from their vendors, are vulnerable to external attacks leveraging publicly available exploits to inject persistent malware. 

Once compromised, they are added to residential proxy botnets that route malicious traffic. In many cases, these proxies are used by cybercriminals to conduct malicious activities or cyberattacks.

"With the 5Socks and Anyproxy network, criminals are selling access to compromised routers as proxies for customers to purchase and use," [explains the FBI Flash advisory](https://www.ic3.gov/CSA/2025/250507.pdf).

"The proxies can be used by threat actors to obfuscate their identity or location."

The advisory lists the following EoL Linksys and Cisco models as common targets:

* Linksys E1200, E2500, E1000, E4200, E1500, E300, E3200, E1550
* Linksys WRT320N, WRT310N, WRT610N
* Cradlepoint E100
* Cisco M10

The FBI warns that Chinese state-sponsored actors have exploited known (n-day) vulnerabilities in these routers to [conduct covert espionage campaign](https://www.bleepingcomputer.com/news/security/state-hackers-turn-to-massive-orb-proxy-networks-to-evade-detection/)s, including operations targeting critical U.S. infrastructure.

In a [related bulletin](https://www.ic3.gov/PSA/2025/PSA250507), the agency confirms that many of these routers are infected with a variant of the "TheMoon" malware, which enables threat actors to configure them as proxies.

"End of life routers were breached by cyber actors using variants of TheMoon malware botnet," reads the FBI bulletin.

"Recently, some routers at end of life, with remote administration turned on, were identified as compromised by a new variant of TheMoon malware. This malware allows cyber actors to install proxies on unsuspecting victim routers and conduct cyber crimes anonymously."

Once compromised, the routers connect to command and control (C2) servers to receive commands to execute, such as scanning for and compromising vulnerable devices on the Internet.

The FBI says that the proxies are then used to evade detection during cryptocurrency theft, cybercrime-for-hire activities, and other illegal operations.

Common signs of compromise by a botnet include network connectivity disruptions, overheating, performance degradation, configuration changes, the appearance of rogue admin users, and unusual network traffic.

The best way to mitigate the risk of botnet infections is to replace end-of-life routers with newer, actively supported models.

If that is impossible, apply the latest firmware update for your model, sourced from the vendor's official download portal, change the default admin account credentials, and turn off remote administration panels.

The FBI has shared indicators of compromise associated with the malware installed on EoL devices.