# Max severity Cisco ISE bug allows pre-auth command execution, patch now

![Max severity Cisco ISE bug allows pre-auth command execution, patch now](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco-headpic.jpg)

A critical vulnerability (CVE-2025-20337) in Cisco's Identity Services Engine (ISE) could be exploited to let an unauthenticated attacker store malicious files, execute arbitrary code, or gain root privileges on vulnerable devices.

The security issue received the maximum severity rating, 10 out of 10, and is caused by insufficient user-supplied input validation checks.

It was discovered by Kentaro Kawane, a researcher at the Japanese cybersecurity service GMO Cybersecurity by Ierae, and reported Trend Micro's Zero Day Initiative (ZDI).

A remote unauthenticated attacker could leverage it by submitting a specially crafted API request.

The vulnerability was added via an [update to the security bulletin](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-unauth-rce-ZAd2GnJ6) for CVE-2025-20281 and CVE-2025-20282, two [similar RCE vulnerabilities](https://www.bleepingcomputer.com/news/security/cisco-warns-of-max-severity-rce-flaws-in-identity-services-engine/) that also received the maximum severity score, that impact ISE and ISE-PIC versions 3.4 and 3.3.

"These vulnerabilities affect Cisco ISE and ISE-PIC releases 3.3 and 3.4, regardless of device configuration," the vendor notes for CVE-2025-20281 and CVE-2025-20337, adding that "these vulnerabilities do not affect Cisco ISE and ISE-PIC Release 3.2 or earlier."

Any of the three security issues can be exploited independently.

Cisco also warns that customers who applied the patches for CVE-2025-20281 and CVE-2025-20282 are not covered from CVE-2025-20337, and need to upgrade to ISE 3.3 Patch 7 or ISE 3.4 Patch 2.

The product versions below are the only ones currently confirmed to address all three maximum severity vulnerabilities. Workarounds or other mitigations are not available.

![Table](https://www.bleepstatic.com/images/news/u/1220909/2025/July/table.png)

Although no exploitation of any of the three vulnerabilities has been observed in the wild as of yet, it is recommended that system administrators take immediate action to mitigate the risks.

Also yesterday, Cisco released four more bulletins covering other vulnerabilities across its products, summarized as follows:

* [CVE-2025-20274](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cuis-file-upload-UhNEtStm): High-severity arbitrary file upload vulnerability impacting Cisco Unified Intelligence Center, including Unified CCX bundles. Authenticated users with Report Designer privileges can upload malicious files and potentially execute them as root. Fixed in versions 12.5(1) SU ES05 and 12.6(2) ES05.
* [CVE-2025-20272](http://Base%204.3%20CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:U/C:L/I:N/A:N/E:X/RL:X/RC:X): Medium-severity blind SQL injection vulnerability in Cisco Prime Infrastructure and EPNM. Low-privileged users can exploit REST APIs to extract unauthorized database content. Resolved in Prime Infrastructure 3.10.6 SU2 and EPNM versions 8.0.1 and 8.1.1.
* [CVE-2025-20283, CVE-2025-20284, CVE-2025-20285](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-multi-3VpsXOxO): Medium-severity authenticated RCE and IP access restriction bypass vulnerabilities in Cisco ISE and ISE-PIC. High-privileged users can execute commands as root or log in from unauthorized IPs. Affects versions 3.3 and 3.4; fixed in 3.3 Patch 7 and 3.4 Patch 2.
* [CVE-2025-20288](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cuis-ssrf-JSuDjeV): Medium-severity SSRF vulnerability in Cisco Unified Intelligence Center, exploitable without authentication. Allows attackers to send arbitrary internal requests via the affected system. Impacts versions 12.5 and 12.6, including Unified CCX bundles. Fixed in 12.5(1) SU ES05 and 12.6(2) ES05.