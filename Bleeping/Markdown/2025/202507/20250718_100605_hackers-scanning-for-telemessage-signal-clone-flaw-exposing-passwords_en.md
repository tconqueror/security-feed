# Hackers scanning for TeleMessage Signal clone flaw exposing passwords

![Hackers scanning for password-exposing flaw in TeleMessage Signal clone](https://www.bleepstatic.com/content/hl-images/2025/06/23/hacker-mobile-phone.jpg)

Researchers are seeing exploitation attempts for the CVE-2025-48927 vulnerability in the TeleMessage SGNL app, which allows retrieving usernames, passwords, and other sensitive data.

TeleMessage SGNL is a Signal clone app now [owned by Smarsh](https://www.smarsh.com/press-release/smarsh-completes-acquisition-of-telemessage-extends-communications-compliance-leadership), a compliance-focused company that provides cloud-based or on-premises communication solutions to various organizations.

### Scanning for vulnerable endpoints

Threat monitoring firm GreyNoise has observed multiple attempts to exploit CVE-2025-48927, likely by different threat actors.

“As of July 16, GreyNoise has observed 11 IPs attempting to exploit CVE-2025-48927,” [reports GreyNoise](https://www.greynoise.io/blog/active-exploit-attempts-signal-based-messaging-app).

“Related reconnaissance behavior is ongoing. Our telemetry shows active scanning for Spring Boot Actuator endpoints, a potential precursor to identifying systems affected by CVE-2025-48927.”

According to GreyNoise, more than two thousand IPs have scanned for Sprint Boot Actuator endpoints over the past months, a little over 75% of them targeting the ‘/health’ endpoints specifically.

The [CVE-2025-48927](https://nvd.nist.gov/vuln/detail/cve-2025-48927) vulnerability is caused by exposing the ‘/heapdump’ endpoint from Spring Boot Actuator without authentication. TeleMessage addressed the issue but some on-prem installations are still vulnerable.

When using outdated Spring Boot configurations that do not restrict access to diagnostic endpoints, the flaw lets an attacker download a full Java heap memory dump of approximately 150MB, which may contain plaintext usernames, passwords, tokens, and other sensitive data.

To defend against these attacks, it is recommended to disable or restrict access to the /heapdump endpoint only to trusted IP ranges and limit the exposure of all Actuator endpoints as much as possible.

### Archiving Signal messages

The TeleMessage SGNL app is designed to provide encrypted communication with [built-in archival](https://www.telemessage.com/mobile-archiver/), so that all chats, calls, and attachments are automatically stored for compliance, auditing, or record-keeping.

These claims have been disputed by past research saying that end-to-end encryption isn’t maintained and sensitive data, including messages, is stored in plaintext.

This was [exposed in May 2025](https://www.bleepingcomputer.com/news/security/unofficial-signal-app-used-by-trump-officials-investigates-hack/), when a hacker accessed a diagnostic endpoint and downloaded credentials and archived content. The event triggered concerns about national security in the U.S., after revelations that the product was being used by the Customs & Border Protection and officials, including Mike Waltz.

CVE-2025-48927 was disclosed in May and CISA added it to the Known Exploited Vulnerabilities (KEV) catalog on July 1, requesting that all federal agencies apply mitigations by July 22.

The agency also listed CVE-2025-48928, a flaw in SGNL where a JSP app exposes a memory dump containing passwords sent over HTTP to unauthorized users.