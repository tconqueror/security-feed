# ConnectWise fixes Automate bug allowing AiTM update attacks

![ConnectWise fixes Automate bug allowing AiTM update attacks](https://www.bleepstatic.com/content/hl-images/2025/05/29/connectwise-logo.jpg)

ConnectWise released a security update to address vulnerabilities, one of them with critical severity, in Automate product that could expose sensitive communications to interception and modification.

ConnectWise Automate is a remote monitoring and management (RMM) platform used by managed service providers (MSPs), IT service companies, and internal IT departments in large enterprises.

In typical deployments, it acts as a central management hub with high priviliges to control thousands of client machines.

The most severe flaw the vendor fixed is tracked as [CVE-2025-11492](https://nvd.nist.gov/vuln/detail/CVE-2025-11492). With a severity rating of 9.6, the vulnerability allows cleartext transmission of sensitive information.

Specifically, agents could be configured to communicate over the insecure HTTP instead of the encrypted HTTPS, which could be exploited in adversary-in-the-middle (AitM) attacks to intercept or modify the traffic, including commands, credentials, and update payloads.

“In on-prem environments, agents could be configured to use HTTP or rely on encryption, that could allow a network-based adversary to view or modify traffic or substitute malicious updates,” [ConnectWise explains](https://www.connectwise.com/company/trust/security-bulletins/connectwise-automate-2025.9-security-fix).

The second vulnerability is identified as [CVE-2025-11493](https://nvd.nist.gov/vuln/detail/CVE-2025-11493) (8.8 severity score) and consists in a lack of integrity verification (checksum or digital signature) for update packages along with their dependencies and integrations.

By combining the two security issues, an attacker could push malicious files (e.g. malware, updates) as legitimate ones by impersonating a valid ConnectWise server.

ConnectWise marks the security update as a moderate priority. The company has addressed both problems for cloud-based instances, which have been updated to the latest Automate release, 2025.9.

The vendor's recommendation for administrators of on-premise deployments is to take action and install the new release as soon as possible (within days).

The security bulletin does not mention active exploitation, but warns that the vulnerabilities "have higher risk of being targeted by exploits in the wild."

Threat actors have leveraged critical-severity flaws in [ConnectWise products](https://www.bleepingcomputer.com/news/security/screenconnect-critical-bug-now-under-attack-as-exploit-code-emerges/) in the past. Earlier this year, nation-state actors [breached the company’s environment](https://www.bleepingcomputer.com/news/security/connectwise-breached-in-cyberattack-linked-to-nation-state-hackers/) directly, with the attack impacting a number of ScreenConnect customers downstreram.

The incident forced the vendor to [rotate all digital code signing certificates](https://www.bleepingcomputer.com/news/security/connectwise-rotating-code-signing-certificates-over-security-concerns/) with which it verified executables for a range of products, to mitigate the risk of misuse.