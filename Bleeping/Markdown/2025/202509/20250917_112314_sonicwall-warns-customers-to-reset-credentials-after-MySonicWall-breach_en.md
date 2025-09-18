# SonicWall warns customers to reset credentials after breach

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/02/14/SonicWall.jpg)

SonicWall warned customers today to reset credentials after their firewall configuration backup files were exposed in a security breach that impacted MySonicWall accounts.

After detecting the incident, SonicWall has cut off the attackers' access to its systems and has been collaborating with cybersecurity and law enforcement agencies to investigate the attack's impact.

"As part of our commitment to transparency, we are notifying you of an incident that exposed firewall configuration backup files stored in certain MySonicWall accounts," [the cybersecurity company said](https://www.sonicwall.com/support/knowledge-base/mysonicwall-cloud-backup-file-incident/250915160910330) on Wednesday. "Access to the exposed firewall configuration files contain information that could make exploitation of firewalls significantly easier for threat actors."

The consequences of the incident could be dire, as these exposed backups might give threat actors access to sensitive information, such as credentials and tokens, for any or all services running on SonicWall devices on their networks.

SonicWall [has also published](http://www.sonicwall.com/support/knowledge-base/essential-credential-reset/250909151701590) detailed [guidance](https://www.sonicwall.com/support/knowledge-base/remediation-playbook/250916130050523) to [help administrators](https://www.sonicwall.com/support/knowledge-base/remediation-through-updated-preferences-file/250916134841513) minimize the risk of an exposed firewall configuration being exploited to access their networks, reconfigure potentially compromised secrets and passwords, and detect possible threat activity within their network.

"The following checklist provides a structured approach to ensure all relevant passwords, keys, and secrets are updated consistently. Performing these steps helps maintain security and protect the integrity of your SonicWall environment. The critical items are listed first. All other credentials should be updated at your convenience," the company cautioned. 

"Please note that the passwords, shared secrets, and encryption keys configured in SonicOS may also need to be updated elsewhere, such as with the ISP, Dynamic DNS provider, email provider, remote IPSec VPN peer, or LDAP/RADIUS server, just to name a few."

This guidance advises administrators to disable or restrict access to services on the device from the WAN before resetting credentials. Then they need to reset all credentials, api keys, and authentication tokens used by users, VPN accounts, and services.

A complete list of the services that need to be reset due to the stolen configuration files is listed in this [Essential Credential Reset](https://www.sonicwall.com/support/knowledge-base/essential-credential-reset/250909151701590) support bulletin.

A SonicWall spokesperson has told BleepingComputer that the incident affects fewer than 5% of SonicWall firewalls and that the attackers targeted the API service for cloud backup in brute-force attacks.

"Our investigation determined that less than 5% of our firewall install base had backup firewall preference files stored in the cloud for these devices accessed by threat actors. While the files contained encrypted passwords, they also included information that could make it easier for attackers to potentially exploit firewalls," the spokesperson said.

"We are not presently aware of these files being leaked online by threat actors. This was not a ransomware or similar event for SonicWall, rather this was a series of account-by-account brute force attacks aimed at gaining access to the preference files stored in backup for potential further use by threat actors."

In August, [SonicWall dismissed reports](https://www.bleepingcomputer.com/news/security/sonicwall-finds-no-sslvpn-zero-day-links-ransomware-attacks-to-2024-flaw/) that the Akira ransomware gang was breaching Gen 7 firewalls with SSLVPN enabled [using a potential zero-day exploit](https://www.bleepingcomputer.com/news/security/surge-of-akira-ransomware-attacks-hits-sonicwall-firewall-devices/), stating that it was actually linked to CVE-2024-40766, a critical SSLVPN access control flaw in SonicOS that was patched in November 2024.

Last week, [the company's theory was confirmed](https://www.bleepingcomputer.com/news/security/akira-ransomware-exploiting-critical-sonicwall-sslvpn-bug-again/) when the Australian Cyber Security Center (ACSC) and cybersecurity firm Rapid7 confirmed that the Akira ransomware gang is now exploiting the CVE-2024-40766 vulnerability to compromise unpatched SonicWall devices.

_Update September 17, 14:33 EDT: Added SonicWall statement._