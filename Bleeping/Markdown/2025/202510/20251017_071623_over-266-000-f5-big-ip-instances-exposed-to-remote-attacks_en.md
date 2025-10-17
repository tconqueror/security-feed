# Over 266,000 F5 BIG-IP instances exposed to remote attacks

![F5](https://www.bleepstatic.com/content/hl-images/2025/10/15/F5_02.png)

Internet security nonprofit Shadowserver Foundation has found more than 266,000 F5 BIG-IP instances exposed online after the security breach disclosed by cybersecurity company F5 this week.

The company revealed on Wednesday that [nation-state hackers breached its network](https://www.bleepingcomputer.com/news/security/hackers-breach-f5-to-steal-undisclosed-big-ip-flaws-source-code/) and stole source code and information on undisclosed BIG-IP security flaws, but found no evidence that the attackers had leaked or exploited the undisclosed vulnerabilities in attacks.

The same day, F5 also [issued patches to address 44 vulnerabilities](https://my.f5.com/manage/s/article/K000156572) (including the ones stolen in the cyberattack) and urged customers to update their devices as soon as possible.

"Updates for BIG-IP, F5OS, BIG-IP Next for Kubernetes, BIG-IQ, and APM clients are available now," the company said. "Though we have no knowledge of undisclosed critical or remote code execution vulnerabilities, we strongly advise updating your BIG-IP software as soon as possible,".

While it has yet to confirm it publicly, F5 has also linked the attack to China in private advisories shared with customers, according to a Thursday Bloomberg report,

F5 has also been sharing a threat-hunting guide with its customers that mentions [the Brickstorm malware](https://www.bleepingcomputer.com/news/security/google-brickstorm-malware-used-to-steal-us-orgs-data-for-over-a-year/), a Go-based backdoor first [spotted by Google in April 2024](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-post-exploitation-lateral-movement) during an investigation into attacks orchestrated by the UNC5291 China-nexus threat group. F5 also told customers that the threat actors were active in the company's network for at least a year.

The Shadowserver Internet watchdog group is now tracking 266,978 IP addresses with an F5 BIG-IP fingerprint, nearly half of them (over 142,000) in the United States and another 100,000 in Europe and Asia.

However, there is no information on how many of them have already been secured against attacks that could potentially exploit the BIG-IP vulnerabilities disclosed this week.

![F5 devices exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/F5%20devices%20exposed%20online.png)

_F5 devices exposed online (Shadowserver)_

​This week, CISA also [issued an emergency directive](https://www.cisa.gov/news-events/directives/ed-26-01-mitigate-vulnerabilities-f5-devices), mandating U.S. federal agencies to secure F5OS, BIG-IP TMOS, BIG-IQ, and BNK/CNF products by installing the latest F5 security patches by October 22, while for all other F5 hardware and software appliances on their networks, it extended the deadline to October 31.

CISA also ordered them to disconnect and decommission all Internet-exposed F5 devices that have reached end-of-support, as they will no longer receive patches and can be easily compromised in attacks.

"CISA is directing Federal Civilian Executive Branch (FCEB) agencies to inventory F5 BIG-IP products, evaluate if the networked management interfaces are accessible from the public internet, and apply updates from F5," the cybersecurity agency said.

In recent years, both nation-state and cybercrime threat groups have been targeting BIG-IP vulnerabilities to [map internal servers](https://www.bleepingcomputer.com/news/security/cisa-hackers-abuse-f5-big-ip-cookies-to-map-internal-servers/), [hijack devices](https://www.bleepingcomputer.com/news/security/new-big-ip-next-central-manager-bugs-allow-device-takeover/) on victims' networks, [breach corporate networks](https://www.bleepingcomputer.com/news/security/iranian-hackers-are-selling-access-to-corporate-networks/), [steal sensitive files](https://www.bleepingcomputer.com/news/security/hackers-use-f5-big-ip-malware-to-stealthily-steal-data-for-years/), and [deploy data-wiping malware](https://www.bleepingcomputer.com/news/security/fake-f5-big-ip-zero-day-warning-emails-push-data-wipers/).

Compromised F5 BIG-IP appliances can also allow threat actors to steal credentials and Application Programming Interface (API) keys, move laterally within targets' networks, and establish persistence.

F5 is a Fortune 500 tech giant that provides cybersecurity, application delivery networking (ADN), and services to over 23,000 customers worldwide, including 48 of the Fortune 50 companies.