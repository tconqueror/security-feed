# Ivanti fixes EPMM zero-days chained in code execution attacks

![Ivanti](https://www.bleepstatic.com/content/hl-images/2024/09/19/ivanti.jpg)

Ivanti warned customers today to patch their Ivanti Endpoint Manager Mobile (EPMM) software against two security vulnerabilities chained in attacks to gain remote code execution.

"Ivanti has released updates for Endpoint Manager Mobile (EPMM) which addresses one medium and one high severity vulnerability," [the company said](https://forums.ivanti.com/s/article/Security-Advisory-Ivanti-Endpoint-Manager-Mobile-EPMM?language=en%5FUS).

"When chained together, successful exploitation could lead to unauthenticated remote code execution. We are aware of a very limited number of customers whose solution has been exploited at the time of disclosure."

The first security flaw ([CVE-2025-4427](https://nvd.nist.gov/vuln/detail/CVE-2025-4427)) is an authentication bypass in EPMM's API component, allowing attackers to access protected resources on vulnerable devices. The second (tracked as [CVE-2025-4428](https://nvd.nist.gov/vuln/detail/CVE-2025-4428)) is a remote code execution vulnerability that allows threat actors to execute arbitrary code on targeted systems via maliciously crafted API requests.

Ivanti says customers can mitigate the two zero-day flaws by installing Ivanti Endpoint Manager Mobile 11.12.0.5, 12.3.0.2, 12.4.0.2, or 12.5.0.1.

The company added that, while it's still investigating these attacks and can't provide indicators of compromise, customers should reach out to the support team for further guidance.

While Ivanti said the two vulnerabilities are "associated" with two open-source libraries used by EPMM, it didn't share their names in the advisory. A spokesperson directed BleepingComputer to today's advisory for further information.

"The issue only affects the on-prem EPMM product. It is not present in Ivanti Neurons for MDM, Ivanti's cloud-based unified endpoint management solution, Ivanti Sentry, or any other Ivanti products," [Ivanti added](https://www.ivanti.com/blog/epmm-security-update) in a separate advisory. "We urge all customers using the on-prem EPMM product to promptly install the patch."

The Shadowserver threat monitoring platform currently tracks [hundreds of Ivanti EPMM instances](https://dashboard.shadowserver.org/statistics/iot-devices/map/?date%5Frange=1&vendor=ivanti&model=epmm&data%5Fset=count&scale=log) exposed online, most in Germany (992) and the United States (418).

![Ivanti EPMM instances exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/Ivanti_EPMM_instances_exposed_online.jpg)

_Ivanti EPMM instances exposed online (Shadowserver)_

​Today, Ivanti also released security updates to [address a critical authentication bypass vulnerability](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-critical-neurons-for-itsm-auth-bypass-flaw/) (CVE-2025-22462) impacting its Neurons for ITSM IT service management solution that can let unauthenticated attackers gain administrative access.

It also urged customers to patch a default credentials flaw (CVE-2025-22460) in its Cloud Services Appliance (CSA) that lets local authenticated attackers escalate privileges on vulnerable systems.

In recent years, multiple other security vulnerabilities [have been](https://www.bleepingcomputer.com/news/security/ivanti-connect-secure-zero-days-now-under-mass-exploitation/) exploited [in zero-day attacks](https://www.bleepingcomputer.com/news/security/newest-ivanti-ssrf-zero-day-now-under-mass-exploitation/) targeting Ivanti's [VPN appliances](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-connect-secure-zero-days-exploited-in-attacks/) and [ICS, IPS, and ZTA gateways](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-new-connect-secure-zero-day-exploited-in-attacks/).

The FBI and CISA also warned in a joint advisory issued in January that threat actors are still exploiting months-old [Ivanti Cloud Service Appliances (CSA) security vulnerabilities](https://www.bleepingcomputer.com/news/security/cisa-hackers-still-exploiting-older-ivanti-bugs-to-breach-networks/) to breach vulnerable networks.