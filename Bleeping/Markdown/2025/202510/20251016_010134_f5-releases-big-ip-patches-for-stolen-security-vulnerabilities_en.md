# F5 releases BIG-IP patches for stolen security vulnerabilities

![F5](https://www.bleepstatic.com/content/hl-images/2025/10/15/F5-headpic.jpg)

Cybersecurity company F5 has released security updates to address BIG-IP vulnerabilities stolen in a breach detected on August 9, 2025.

The company disclosed in a Wednesday filing with the U.S. Securities and Exchange Commission (SEC) that [state hackers breached its systems](https://www.bleepingcomputer.com/news/security/hackers-breach-f5-to-steal-undisclosed-big-ip-flaws-source-code/) and stole source code and information on undisclosed BIG-IP security flaws.

F5 added that there's no evidence the threat actors leveraged the undisclosed vulnerabilities in attacks and said it has not yet found evidence that the flaws have been disclosed.

Today, F5 has [issued patches to address 44 vulnerabilities](https://my.f5.com/manage/s/article/K000156572) (including the ones stolen in the breach) and urged customers to update their systems as soon as possible. F5 confirmed to BleepingComputer that "today's security updates do address impact from the incident."

"Updates for BIG-IP, F5OS, BIG-IP Next for Kubernetes, BIG-IQ, and APM clients are available now. Though we have no knowledge of undisclosed critical or remote code execution vulnerabilities, we strongly advise updating your BIG-IP software as soon as possible," the company said.

"We have no evidence of modification to our software supply chain, including our source code and our build and release pipelines \[..\] and we are not aware of active exploitation of any undisclosed F5 vulnerabilities."

F5 also issued guidance to help secure F5 environments from cyberattacks, which they say includes the release of the October 2025 security updates. 

The company advised admins to enable BIG-IP event streaming to their security information and event management (SIEM) software, [configure remote syslog servers](https://my.f5.com/manage/s/article/K13080), and [monitor for login attempts](https://my.f5.com/manage/s/article/K13426) to increase visibility and receive alerts on admin logins, failed authentications, and privilege and configuration changes.

## Federal agencies ordered to deploy BIG-IP patches

On Wednesday, CISA [published the ED 26-01 emergency directive](https://www.cisa.gov/news-events/directives/ed-26-01-mitigate-vulnerabilities-f5-devices), ordering Federal Civilian Executive Branch (FCEB) agencies to secure F5 hardware and software appliances by applying the latest security updates by October 31, 2025.

The U.S. cybersecurity agency also instructed federal agencies to disconnect and decommission all public-facing F5 devices that have reached end-of-support. 

"CISA is directing Federal Civilian Executive Branch (FCEB) agencies to inventory F5 BIG-IP products, evaluate if the networked management interfaces are accessible from the public internet, and apply updates from F5," CISA said.

Successful exploitation of vulnerable BIG-IP appliances can allow attackers to steal credentials and Application Programming Interface (API) keys, move laterally within targets' networks, steal sensitive data, and establish persistence on compromised devices.

BIG-IP vulnerabilities are high-value targets for both nation-state and cybercrime threat groups, which have been exploiting them over the years to [map internal servers](https://www.bleepingcomputer.com/news/security/cisa-hackers-abuse-f5-big-ip-cookies-to-map-internal-servers/), [stealthily steal data,](https://www.bleepingcomputer.com/news/security/hackers-use-f5-big-ip-malware-to-stealthily-steal-data-for-years/) [hijack devices](https://www.bleepingcomputer.com/news/security/new-big-ip-next-central-manager-bugs-allow-device-takeover/) on victims' networks, [push data wipers](https://www.bleepingcomputer.com/news/security/fake-f5-big-ip-zero-day-warning-emails-push-data-wipers/), and [breach corporate networks](https://www.bleepingcomputer.com/news/security/iranian-hackers-are-selling-access-to-corporate-networks/)

F5 is a Fortune 500 tech giant that provides cybersecurity, cloud management, and application delivery networking (ADN) services to over 23,000 customers worldwide and to 48 of Fortune 50 companies.