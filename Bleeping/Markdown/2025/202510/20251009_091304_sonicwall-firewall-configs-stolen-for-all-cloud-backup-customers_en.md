# SonicWall: Firewall configs stolen for all cloud backup customers

![SonicWall: Firewall configs stolen for all cloud backup customers](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall_logo.jpeg)

SonicWall has confirmed that all customers that used the company's cloud backup service are affected by the security breach last month.

Previously, the vendor stated that the incident "exposed firewall configuration backup files stored in certain MySonicWall accounts," without sharing additional details.

MySonicWall is an online customer portal used for managing product access, licensing, registration, firmware updates, support cases, and cloud backups of firewall configurations (.EXP files).

On September 17, the company warned customers to [reset their MySonicWall account credentials](https://www.bleepingcomputer.com/news/security/sonicwall-warns-customers-to-reset-credentials-after-MySonicWall-breach/) to protect their firewall configuration backup files that could be potentially accessed by unauthorized actors who had breached its systems.

"Access to the exposed firewall configuration files contain information that could make exploitation of firewalls significantly easier for threat actors," warned SonicWall at the time, also publishing detailed [remediation guidance](https://www.sonicwall.com/support/knowledge-base/remediation-playbook/250916130050523).

At the time, SonicWall specified that roughly 5% of its firewall customers use its cloud backup service.

In an update published yesterday the vendor said that the incident impacts all customers who used its cloud backup portal to store firewall configuration files.

"SonicWall has completed its investigation, conducted in collaboration with leading IR Firm, Mandiant, into the scope of a recent cloud backup security incident," [reads the updated bulletin](https://www.sonicwall.com/support/knowledge-base/mysonicwall-cloud-backup-file-incident/250915160910330).

"The investigation confirmed that an unauthorized party accessed firewall configuration backup files for all customers who have used SonicWall's cloud backup service."

The exposed files contain AES-256-encrypted credentials and configuration data.

Users can now check if their devices are among the impacted ones by logging into MySonicWall and going to 'Product Management → Issue List.'

![SonicWall](https://www.bleepstatic.com/images/news/u/1220909/2025/October/090250918728378.jpg)

_Source: SonicWall_

If any action items are pending review there, users should follow the [Essential Credential Reset](https://www.sonicwall.com/support/knowledge-base/essential-credential-reset/250909151701590) steps, prioritizing active, internet-facing firewalls.

Although SonicWall has stated that the investigation is now complete, it would be prudent for system administrators to continue monitoring MySonicWall alerts periodically for updated lists of affected devices.