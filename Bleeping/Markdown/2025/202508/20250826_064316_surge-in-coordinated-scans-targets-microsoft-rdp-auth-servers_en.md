# Surge in coordinated scans targets Microsoft RDP auth servers

![Network scans](https://www.bleepstatic.com/content/hl-images/2022/08/17/global-pew-pew.jpg)

Internet intelligence firm GreyNoise reports that it has recorded a significant spike in scanning activity consisting of nearly 1,971 IP addresses probing Microsoft Remote Desktop Web Access and RDP Web Client authentication portals in unison, suggesting a coordinated reconnaissance campaign.

The researchers say that this is a massive change in activity, with the company usually only seeing 3–5 IP addresses a day performing this type of scanning.

GreyNoise says that the wave in scans is testing for timing flaws that could be used to verify usernames, setting up future credential-based attacks, such as brute force or password-spray attacks.

Timing flaws occur when the response time of a system or request unintentionally reveals sensitive information. In this case, a slight timing difference in how quickly RDP responds to login attempts with a valid user compared to an invalid one could allow attackers to infer if the username is correct.

GreyNoise also says that 1,851 shared the same client signature, and of those, approximately 92% were already flagged as malicious. The IP addresses predominantly originate from Brazil and targeted IP addresses in the United States, indicating it may be a single botnet or toolset conducting the scans.

![Unique IP addresses performng Microsoft RDP web client login enumeration](https://www.bleepstatic.com/images/news/security/g/greynoise/rdp-scanning/greynoise-unique-ips.jpg)

**Unique IP addresses performng Microsoft RDP web client login enumeration**  
_Source: GreyNoise_

The researchers say that the timing of the attack coincides with the US back-to-school season, when schools and universities may be bringing their RDP systems back online.

"The timing may not be accidental. August 21 sits squarely in the US back-to-school window, when universities and K-12 bring RDP-backed labs and remote access online and onboard thousands of new accounts," [explains GreyNoise's Noah Stone](https://www.greynoise.io/blog/surge-malicious-ips-probe-microsoft-remote-desktop).

"These environments often use predictable username formats (student IDs, firstname.lastname), making enumeration more effective. Combined with budget constraints and a priority on accessibility during enrollment, exposure could spike."

However, the surge in scans could also indicate that a new vulnerability may have been found, as GreyNoise has previously found that spikes in malicious traffic [commonly precede the disclosure of new vulnerabilities](https://www.bleepingcomputer.com/news/security/spikes-in-malicious-activity-precede-new-cves-in-80-percent-of-cases/).

Windows admins managing RDP portals and exposed devices should make sure their accounts are properly secured with multi-factor authentication, and if possible, place them behind VPNs.