# Cisco warns of max severity RCE flaws in Identity Services Engine

![Cisco](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco_headpic.jpg)

Cisco has published a bulletin to warn about two critical, unauthenticated remote code execution (RCE) vulnerabilities affecting Cisco Identity Services Engine (ISE) and the Passive Identity Connector (ISE-PIC).

The flaws, tracked under [CVE-2025-20281](https://nvd.nist.gov/vuln/detail/CVE-2025-20281) and [CVE-2025-20282](https://nvd.nist.gov/vuln/detail/CVE-2025-20282), are rated with max severity (CVSS score: 10.0). The first impacts ISE and ISE-PIC versions 3.4 and 3.3, while the second affects only version 3.4.

The root cause of CVE-2025-20281 is an insufficient validation of user-supplied input in a specific exposed API. This allows an unauthenticated, remote attacker to send a specially crafted API request to execute arbitrary operating system commands as the root user.

The second issue, CVE-2025-20282, is caused by poor file validation in an internal API, allowing files to be written to privileged directories. The flaw allows unauthenticated, remote attackers to upload arbitrary files to the target system and execute them with root privileges.

Cisco Identity Services Engine (ISE) is a network security policy management and access control platform used by organizations to manage their network connections, serving as a network access control (NAC), identity management, and policy enforcement tool.

The product is typically used by large enterprises, government organizations, universities, and service providers, sitting at the core of the enterprise network.

The two flaws impacting it could enable complete compromise and full remote takeover of the target device without any authentication or user interaction.

Cisco [noted in the bulletin](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-unauth-rce-ZAd2GnJ6) that it is not aware of any cases of active exploitation for the two flaws, but installing the new updates should be prioritized.

Users are recommended to upgrade to 3.3 Patch 6 (ise-apply-CSCwo99449\_3.3.0.430\_patch4) and 3.4 Patch 2 (ise-apply-CSCwo99449\_3.4.0.608\_patch1) or later. No workarounds were provided to mitigate the flaws, so applying the security updates is the recommended solution.

Cisco also [published a separate bulletin](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-auth-bypass-mVfKVQAU) regarding a medium-severity authentication bypass flaw, tracked as [CVE-2025-20264](https://nvd.nist.gov/vuln/detail/CVE-2025-20264), which also impacts ISE.

The flaw is caused by the inadequate enforcement of authorization for users created via SAML SSO integration with an external identity provider. An attacker with valid SSO-authenticated credentials can send a specific sequence of commands to modify system settings or perform a system restart.

CVE-2025-20264 impacts all versions of ISE up to the 3.4 branch. Fixes were made available in 3.4 Patch 2 and 3.3 Patch 5. The vendor promised to fix the flaw for 3.2 with the release of 3.2 Patch 8, planned for November 2025.

ISE 3.1 and earlier are also impacted but are no longer supported, and users are recommended to migrate to a newer release branch.