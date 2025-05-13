# Ivanti warns of critical Neurons for ITSM auth bypass flaw

![Ivanti](https://www.bleepstatic.com/content/hl-images/2023/12/20/Ivanti.jpg)

Ivanti has released security updates for its Neurons for ITSM IT service management solution that mitigate a critical authentication bypass vulnerability.

Tracked as CVE-2025-22462, the security flaw can let unauthenticated attackers gain administrative access to unpatched systems in low-complexity attacks, depending on system configuration.

As the company highlighted in a security advisory released today, organizations that followed its guidance are less exposed to attacks.

"Customers who have followed [Ivanti's guidance](https://help.ivanti.com/ht/help/en%5FUS/ISM/2024/ITSM-On-Prem-Help/Content/ConfigDB%5FGuide/Securing-IIS-Website.htm) on securing the IIS website and restricted access to a limited number of IP addresses and domain names have a reduced risk to their environment," [Ivanti said](https://forums.ivanti.com/s/article/Security-Advisory-Ivanti-Neurons-for-ITSM-on-premises-only-CVE-2025-22462?language=en%5FUS).

"Customers who have users log into the solution from outside their company network also have a reduced risk to their environment if they ensure that the solution [is configured with a DMZ.](https://help.ivanti.com/ht/help/en%5FUS/ISM/2024/ITSM-On-Prem-Help/Content/Install%5FDeploy%5Fguide/Deployment%5FEnter%5FProd%5FSecure.htm)"

Ivanti added that CVE-2025-22462 only impacts on-premises instances running versions 2023.4, 2024.2, 2024.3, and earlier, and said that it found no evidence that the vulnerability is being exploited to target customers.

| **Product Name**                       | **Affected Version(s)**    | **Resolved Version(s)**                                                                      |
| -------------------------------------- | -------------------------- | -------------------------------------------------------------------------------------------- |
| Ivanti Neurons for ITSM (on-prem only) | 2023.4, 2024.2, and 2024.3 | 2023.4 May 2025 Security Patch 2024.2 May 2025 Security Patch 2024.3 May 2025 Security Patch |

The company also urged customers today to patch a default credentials security flaw (CVE-2025-22460) in its Cloud Services Appliance (CSA) that can let local authenticated attackers escalate privileges on vulnerable systems.

While this vulnerability isn't exploited in the wild either, Ivanti warned that the patch won't be applied correctly after installing today's security updates and asked admins to reinstall from scratch or use [these mitigation steps](https://forums.ivanti.com/s/article/Securing-the-Ivanti-Cloud-Services-Application-CSA-Against-CVE-2025-22460?ui-force-components-controllers-recordGlobalValueProvider.RecordGvp.getRecord=1) to ensure their network is protected from potential attacks.

"It has been identified that if a Cloud Services Application installation is upgraded to version 5.0.5, this fix is not automatically applied as intended. This will be addressed in a future release," Ivanti said.

Last month, the company also [patched a critical Connect Secure zero-day](https://www.bleepingcomputer.com/news/security/ivanti-patches-connect-secure-zero-day-exploited-since-mid-march/) exploited by the UNC5221 China-linked espionage group in remote code execution attacks to deploy malware since at least mid-March 2025.

As CISA and the FBI warned in January, threat actors are still exploiting [Ivanti Cloud Service Appliances (CSA) security vulnerabilities](https://www.bleepingcomputer.com/news/security/cisa-hackers-still-exploiting-older-ivanti-bugs-to-breach-networks/) patched since September to breach vulnerable networks.

Over the last year, multiple other Ivanti security flaws [have been](https://www.bleepingcomputer.com/news/security/ivanti-connect-secure-zero-days-now-under-mass-exploitation/) exploited [in zero-day attacks](https://www.bleepingcomputer.com/news/security/newest-ivanti-ssrf-zero-day-now-under-mass-exploitation/) targeting the company's [VPN appliances](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-connect-secure-zero-days-exploited-in-attacks/) and [ICS, IPS, and ZTA gateways](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-new-connect-secure-zero-day-exploited-in-attacks/).