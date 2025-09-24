# SolarWinds Releases Hotfix for Critical CVE-2025-26399 Remote Code Execution Flaw

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhFO1p2qWLIaLkEjXvBexuWL8MRzvAn8rhnkmU8V%5F%5FGge5ajRgr8Hz1rgLcSPqi5igX4xCZ5%5FNMO8XjmonjH2PXyDK7ADHR3zlRfwUDZxrQDoIV5LkcVG7LseBYfLT5rkBM8bC1kyWcB5%5F2ndJ3Ijt-1LYzjr5D9lIIx2xM%5F4JtRQfPsI8mFvhzUtFYxnGi/s728-rw-e365/solar.jpg)

SolarWinds has released hot fixes to address a critical security flaw impacting its Web Help Desk software that, if successfully exploited, could allow attackers to execute arbitrary commands on susceptible systems.

The vulnerability, tracked as **CVE-2025-26399** (CVSS score: 9.8), has been described as an instance of deserialization of untrusted data that could result in code execution. It affects SolarWinds Web Help Desk 12.8.7 and all previous versions.

"SolarWinds Web Help Desk was found to be susceptible to an unauthenticated AjaxProxy deserialization remote code execution vulnerability that, if exploited, would allow an attacker to run commands on the host machine," SolarWinds [said](https://www.solarwinds.com/trust-center/security-advisories/cve-2025-26399) in an advisory released on September 17, 2025.

[](https://thehackernews.uk/exec-guide-d)

An anonymous researcher working with the Trend Micro Zero Day Initiative (ZDI) has been credited with discovering and reporting the flaw.

SolarWinds said CVE-2025-26399 is a patch bypass for CVE-2024-28988 (CVSS score: 9.8), which, in turn, is a bypass for [CVE-2024-28986](https://thehackernews.com/2024/08/solarwinds-releases-patch-for-critical.html) (CVSS score: 9.8) that was originally addressed by the company back in August 2024.

"This vulnerability allows remote attackers to execute arbitrary code on affected installations of SolarWinds Web Help Desk. Authentication is not required to exploit this vulnerability," according to a [ZDI advisory](https://www.zerodayinitiative.com/advisories/ZDI-25-407/) for CVE-2024-28988.

"The specific flaw exists within the AjaxProxy. The issue results from the lack of proper validation of user-supplied data, which can result in deserialization of untrusted data. An attacker can leverage this vulnerability to execute code in the context of SYSTEM."

While there is no evidence of the vulnerability being exploited in the wild, users are advised to update their instances to [SolarWinds Web Help Desk 12.8.7 HF1](https://documentation.solarwinds.com/en/success%5Fcenter/whd/content/release%5Fnotes/whd%5F12-8-7-hotfix-1%5Frelease%5Fnotes.htm) for optimal protection.

That said, it's worth emphasizing that the original bug CVE-2024-28986 was added to the Known Exploited Vulnerabilities (KEV) catalog by the U.S. Cybersecurity and Infrastructure Security Agency (CISA) shortly after public disclosure. There is currently no information publicly available on the nature of the attacks weaponizing the bug.

[](https://thehackernews.uk/cis-security-suite)

"SolarWinds is a name that needs no introduction in IT and cybersecurity circles. The infamous 2020 supply chain attack, attributed to Russia's Foreign Intelligence Service (SVR), allowed months-long access into multiple Western government agencies and left a lasting mark on the industry," Ryan Dewhurst, head of proactive threat intelligence at watchTowr, said in a statement.

"Fast forward to 2024: an unauthenticated remote deserialization vulnerability (CVE-2024-28986) was patched... then patched again (CVE-2024-28988). And now, here we are with yet another patch (CVE-2025-26399) addressing the very same flaw.

"Third time's the charm? The original bug was actively exploited in the wild, and while we're not yet aware of active exploitation of this latest patch bypass, history suggests it's only a matter of time."