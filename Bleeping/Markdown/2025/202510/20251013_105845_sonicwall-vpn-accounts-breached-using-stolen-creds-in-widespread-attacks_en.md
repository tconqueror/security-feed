# SonicWall VPN accounts breached using stolen creds in widespread attacks

![SonicWall VPN accounts breached using stolen creds in widespread attacks](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall.jpeg)

Researchers warn that threat actors have compromised more than a hundred SonicWall SSLVPN accounts in a large-scale campaign using stolen, valid credentials.

Although in some cases the attackers disconnected after a short period, in others they followed up with network scans and attempts to access local Windows accounts.

Most of this activity began on October 4, as observed by managed cybersecurity platform Huntress at multiple customer environments.

“Threat actors are authenticating into multiple accounts rapidly across compromised devices," the researchers said, adding that "the speed and scale of these attacks imply that the attackers appear to control valid credentials rather than brute-forcing.”

The attacks have impacted over 100 SonicWall SSLVPN accounts across 16 environments that Huntress protects, indicating a significant and widespread campaign that was still ongoing on October 10.

In most cases, the malicious requests originated from the IP address 202.155.8\[.\]73, the [researchers said](https://www.huntress.com/blog/sonicwall-sslvpn-compromise).

After the authentication step, Huntress observed activity specific to the reconnaissance and lateral movement steps of an attack as the threat actor tried to access a large number of local Windows accounts.

Huntress underlines that they did not find evidence connecting the spate of compromises they observed to the recent SonicWall breach that [exposed the firewall configuration files](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-configs-stolen-for-all-cloud-backup-customers/) for all cloud backup customers.

Because they contain highly sensitive data, these files are encoded, and the credentials and secrets within are individually encrypted using the AES-256 algorithm.

While an attacker could decode the files, they would see the authentication passwords and keys in encrypted form, the network security company [explained](https://www.sonicwall.com/support/knowledge-base/mysonicwall-cloud-backup-file-incident/250915160910330#:~:text=Backup%20File%20Incident-,Backup%20Preference%20File%20Facts,-File%20export%20basics).

BleepingComputer has contacted SonicWall for a comment on the activity that Huntress researchers observed, but a statement wasn’t immediately available.

According to SonicWall’s security checklist, system administrators need to take the following protective steps:

* Reset and update all local user passwords and temporary access codes
* Update passwords on LDAP, RADIUS, or TACACS+ servers
* Update secrets in all IPSec site-to-site and GroupVPN policies
* Update L2TP/PPPoE/PPTP WAN interface passwords
* Reset the L2TP/PPPoE/PPTP WAN interfaces

Huntress proposes the additional measures of immediately restricting WAN management and remote access when it’s not needed, and disabling or limiting HTTP, HTTPS, SSH, and SSL VPN until all secrets are rotated.

External API keys, dynamic DNS, and SMTP/FTP credentials should also be revoked, and automation secrets pertinent to firewall and management systems should be invalidated.

All admin and remote accounts should be protected by multi-factor authentication. The service re-introduction must be performed in a staged manner to observe for suspicious activity at each step.