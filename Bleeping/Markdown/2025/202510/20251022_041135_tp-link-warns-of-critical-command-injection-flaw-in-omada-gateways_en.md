# TP-Link warns of critical command injection flaw in Omada gateways

![TP-Link warns of critical command injection flaw in Omada gateways](https://www.bleepstatic.com/content/hl-images/2025/09/04/TPLINK_Logo_2.jpg)

TP-Link is warning of two command injection vulnerabilities in Omada gateway devices that could be exploited to execute arbitrary OS commands.

Omada gateways are marketed as full-stack solutions (router, firewall, VPN gateway) for small to medium businesses, and are constantly increasing in popularity.

Although the two security issues lead to the same result when triggered, only one of them, identified as CVE-2025-6542 with a critical severity rating of 9.3, can be exploited by a remote attacker without authentication.

The second flaw is tracked as CVE-2025-6541 and received a lower severity score of 8.6\. However, it can be exploited only if the attacker can log into the web management interface.

“An arbitrary OS command may be executed on Omada gateways by the user who can log in to the web management interface or by a remote unauthenticated attacker,” reads [TP-Link's advisory](https://support.omadanetworks.com/en/document/108455/).

“Attackers may execute arbitrary commands on the device’s underlying operating system,” the company adds.

The risk the two vulnerabilities poses is significant as it can lead to a full compromise, data theft, lateral movement, and persistence.

CVE-2025-6541 and CVE-2025-6542 impact 13 Omada gateway models in the firmware versions listed below:

| **Affected Product Model** **Affected Version** **Fixed Version** ER8411 < 1.3.3 Build 20251013 Rel.44647 \>= 1.3.3 Build 20251013 Rel.44647 ER7412-M2 < 1.1.0 Build 20251015 Rel.63594 \>= 1.1.0 Build 20251015 Rel.63594 ER707-M2 < 1.3.1 Build 20251009 Rel.67687 \>= 1.3.1 Build 20251009 Rel.67687 ER7206 < 2.2.2 Build 20250724 Rel.11109 \>= 2.2.2 Build 20250724 Rel.11109 ER605 < 2.3.1 Build 20251015 Rel.78291 \>= 2.3.1 Build 20251015 Rel.78291 ER706W < 1.2.1 Build 20250821 Rel.80909 \>= 1.2.1 Build 20250821 Rel.80909 ER706W-4G < 1.2.1 Build 20250821 Rel.82492 \>= 1.2.1 Build 20250821 Rel.82492 ER7212PC < 2.1.3 Build 20251016 Rel.82571 \>= 2.1.3 Build 20251016 Rel.82571 G36 < 1.1.4 Build 20251015 Rel.84206 \>= 1.1.4 Build 20251015 Rel.84206 G611 < 1.2.2 Build 20251017 Rel.45512 \>= 1.2.2 Build 20251017 Rel.45512 FR365 < 1.1.10 Build 20250626 Rel.81746 \>= 1.1.10 Build 20250626 Rel.81746 FR205 < 1.0.3 Build 20251016 Rel.61376 \>= 1.0.3 Build 20251016 Rel.61376 FR307-M2 < 1.2.5 Build 20251015 Rel.76743 \>= 1.2.5 Build 20251015 Rel.76743 |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

The vendor has released firmware updates that address the two problems and strongly recommends that users with impacted devices to apply the fixes and check the configurations after the upgrade to make sure that all settings remain as intended.

In a [separate bulletin](https://support.omadanetworks.com/us/document/108456/), TP-Link warned of two other severe flaws that could allow authenticated command injection and root access under certain conditions.

The first is CVE-2025-8750 (CVSS: 9.3), a command injection flaw that can be exploited by attackers holding admin passwords to access the Omada web portal.

The other one is CVE-2025-7851 (CVSS: 8.7), which could enable an attacker to obtain shell access with root privileges on the underlying OS, restricted to Omada’s privileges.

CVE-2025-7850 and CVE-2025-7851 impact all of the Omada gateway models listed in the table above. It is worth noting that the latest firmware release addresses all four vulnerabilities.