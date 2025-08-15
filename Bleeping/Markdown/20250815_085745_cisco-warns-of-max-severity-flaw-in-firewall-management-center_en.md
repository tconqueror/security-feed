# Cisco warns of max severity flaw in Firewall Management Center

![Cisco warns of max severity flaw in Firewall Management Center](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco_headpic.jpg)

Cisco is warning about a critical remote code execution (RCE) vulnerability in the RADIUS subsystem of its Secure Firewall Management Center (FMC) software.

Cisco FMC is a management platform for the vendor’s Secure Firewall products, which provides a centralized web or SSH-based interface to allow administrators to configure, monitor, and update Cisco firewalls.

RADIUS in FMC is an optional external authentication method that permits connecting to a Remote Authentication Dial-In User Service server instead of local accounts.

This configuration is commonly used in enterprise and government networks where administrators want centralized login control and accounting for network device access.

The recently disclosed vulnerability is tracked as CVE-2025-20265 and received the maximum severity score of 10 out of 10.

It can be exploited to allow an unauthenticated remote attacker to send specially crafted input when entering credentials during the RADIUS authentication step.

An adversary could thus achieve arbitrary shell command execution with elevated privileges.

“A vulnerability in the RADIUS subsystem implementation of Cisco Secure Firewall Management Center (FMC) Software could allow an unauthenticated, remote attacker to inject arbitrary shell commands that are executed by the device,” [warns Cisco in the security bulletin](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-fmc-radius-rce-TNBKf79).

“This vulnerability is due to a lack of proper handling of user input during the authentication phase,” the vendor says. CVE-2025-20265 impacts FMC versions 7.0.7 and 7.7.0 when the RADIUS authentication is enabled for the web-based management interface, SSH management, or both.

Cisco has released free software updates that address the issue. The fix was released through regular channels to customers with a valid service contract.

If the patch cannot be installed, Cisco's recommended mitigation is to disable RADIUS authentication and replace it with a different method (e.g. local user accounts, external LDAP, or SAML single sign-on).

Cisco notes that this mitigation worked in testing, but customers must verify its applicability and the impact it has in their environments.

The vulnerability was discovered internally by Cisco’s security researcher Brandon Sakai, and the vendor is not aware of the vulnerability being exploited in the wild.

Along with CVE-2025-20265, Cisco also released fixes for 13 high-severity flaws across various products, none of them marked as actively exploited:

* [CVE-2025-20217](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ftd-dos-SvKhtjgt) – Secure Firewall Threat Defense Snort 3 denial of service.
* [CVE-2025-20222](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-fp2k-IPsec-dos-tjwgdZCO) – ASA & Secure FTD (Firepower 2100) IPv6 over IPsec denial of service.
* [CVE-2025-20148](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-fmc-html-inj-MqjrZrny) – Secure Firewall Management Center HTML injection.
* [CVE-2025-20244](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-vpnwebs-dos-hjBhmBsX) – ASA & Secure FTD Remote Access VPN web server denial of service.
* [CVE-2025-20133, CVE-2025-20243](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-vpn-dos-mfPekA6e) – ASA & Secure FTD Remote Access SSL VPN denial of service.
* [CVE-2025-20134](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-ssltls-dos-eHw76vZe) – ASA & Secure FTD SSL/TLS certificate denial of service.
* [CVE-2025-20136](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-nat-dns-dos-bqhynHTM) – ASA & Secure FTD NAT DNS inspection denial of service.
* [CVE-2025-20251](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-http-file-hUyX2jL4) – ASA & Secure FTD VPN web server denial of service.
* [CVE-2025-20224, CVE-2025-20225](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asa-ftd-ios-dos-DOESHWHy) – IOS, IOS XE, ASA & Secure FTD IKEv2 denial of service.
* [CVE-2025-20263](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asa-buffer-overflow-PyRUhWBC) – ASA & Secure FTD web services denial of service.
* [CVE-2025-20127](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-3100%5F4200%5Ftlsdos-2yNSCd54) – ASA & Secure FTD (Firepower 3100/4200) TLS 1.3 cipher denial of service.

The vendor says that there are no workarounds for any of the above security issues except for CVE-2025-20127, where the recommendation is to remove the TLS 1.3 cipher.

For all other issues the vendor recommends installing the latest updates available.