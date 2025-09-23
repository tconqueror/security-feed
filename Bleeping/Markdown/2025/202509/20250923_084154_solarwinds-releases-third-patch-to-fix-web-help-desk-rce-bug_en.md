# SolarWinds releases third patch to fix Web Help Desk RCE bug

![SolarWinds](https://www.bleepstatic.com/content/hl-images/2024/02/16/solarwinds_headpic.jpg)

SolarWinds has released a hotfix for a critical a critical vulnerability in Web Help Desk that allows remote code execution (RCE) without authentication.

Tracked as CVE-2025-26399, the security issue is the company's third attempt to address an older flaw identified as CVE-2024-28986 that impacted Web Help Desk (WHD) 12.8.3 and all previous versions.

SolarWinds WHD is a help desk and ticketing suite used by medium-to-large organizations for IT support request tracking, workflow automation, asset management, and compliance assurance.

CVE-2025-26399 affects the latest WHD version 12.8.7 and is caused by unsafe deserialization handling in the AjaxProxy component. Successful exploitation allows an unauthenticated attacker to run commands on the host machine.

In a [security bulletin](http://documentation.solarwinds.com/en/success%5Fcenter/whd/content/release%5Fnotes/whd%5F12-8-7-hotfix-1%5Frelease%5Fnotes.htm), the vendor says that "this vulnerability is a patch bypass of CVE-2024-28988, which in turn is a patch bypass of CVE-2024-28986."

Last August, the U.S. Cybersecurity and Infrastructure Security Agency (CISA) marked the original SolarWinds flaw as being [leveraged in attacks](https://www.bleepingcomputer.com/news/security/cisa-warns-critical-solarwinds-rce-bug-is-exploited-in-attacks/) and added it to the Known Exploited Vulnerabilities (KEV) catalog.

The new security problem was reported to SolarWinds through the Trend Micro Zero Day Initiative (ZDI). At the time of writing there are no public reports about threat actors exploiting it.

## Hotfix available

SolarWinds has released a hotfix that addresses CVE-2025-26399, which requires installing Web Help Desk version 12.8.7\. To apply the security update, users are advised to follow these steps:

1. Stop Web Help Desk
2. Navigate to: <WebHelpDesk>/bin/webapps/helpdesk/WEB-INF/lib/ (substitute <WebHelpDesk> depending on OS)
3. Back up and then delete: c3p0.jar
4. Back up (to a separate directory): whd-core.jar, whd-web.jar, whd-persistence.jar
5. Copy the hotfix-supplied JARs into the same /lib directory, overwriting the originals: whd-core.jar, whd-web.jar, whd-persistence.jar, plus add HikariCP.jar
6. Restart Web Help Desk

The hotfix is exclusively available through the SolarWinds [Customer Portal](https://customerportal.solarwinds.com/). More information on how to upgrade WHD is [available here](https://documentation.solarwinds.com/en/success%5Fcenter/whd/content/helpdeskupgradewhd.htm).