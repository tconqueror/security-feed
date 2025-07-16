# SonicWall SMA devices hacked with OVERSTEP rootkit tied to ransomware

![](https://www.bleepstatic.com/content/hl-images/2022/01/24/Sonicwall.jpg)

A threat actor has been deploying a previously unseen malware called OVERSTEP that modifies the boot process of fully-patched but no longer supported SonicWall Secure Mobile Access appliances.

The backdoor is a user-mode rootkit that allows hackers to hide malicious components, maintain persistent access on the device, and steal sensitive credentials.

Researchers at Google Threat Intelligence Group (GTIG) observed the rootkit in attacks that may have relied on “an unknown, zero-day remote code execution vulnerability”.

The threat actor is tracked as UNC6148 and has been operating since at least last October, with an organization being targeted as recently as May.

Because files stolen from the victim were later published on the World Leaks ([Hunters International rebrand](https://www.bleepingcomputer.com/news/security/hunters-international-ransomware-shuts-down-after-world-leaks-rebrand/)) data-leak site, GTIG researchers believe that UNC6148 engages in data theft and extortion attacks, and may also deploy Abyss ransomware (tracked as VSOCIETY by GTIG).

### Hackers come prepared

The hackers are targeting end-of-life (EoL) SonicWall SMA 100 Series devices that provide secure remote access to enterprise resources on the local network, in the cloud, or hybrid datacenters.

It is unclear how the hackers obtained initial access, but researchers investigating UNC6148 attacks noticed that the threat actor already had local administrator credentials on the targeted appliance.

“GTIG assesses with high confidence that UNC6148 exploited a known vulnerability to steal administrator credentials prior to the targeted SMA appliance being updated to the latest firmware version (10.2.1.15-81sv)” - Google Threat Intelligence Group

Looking at the network traffic metadata, the investigators found evidence suggesting that UNC6148 had stolen the credentials for the targeted appliance in January.

Multiple n-day vulnerabilities ([CVE-2021-20038](https://nvd.nist.gov/vuln/detail/CVE-2021-20038), [CVE-2024-38475](https://nvd.nist.gov/vuln/detail/CVE-2024-38475), [CVE-2021-20035](https://nvd.nist.gov/vuln/detail/CVE-2021-20035), [CVE-2021-20039](https://nvd.nist.gov/vuln/detail/CVE-2021-20039), [CVE-2025-32819](https://nvd.nist.gov/vuln/detail/CVE-2025-32819)) could have been exploited to this effect, the oldest of them disclosed in 2021 and the most recent being from May 2025.

Of these, the hackers may have exploited CVE-2024-38475 as it provides “local administrator credentials and valid session tokens that UNC6148 could reuse.”

However, incident responders at Mandiant (a Google company) could not confirm that the attacker exploited the vulnerability.

### Reverse-shell mystery

In an attack in June, UNC6148 used the local admin credentials to connect to the targeted SMA 100 series appliance over an SSL-VPN session.

The hackers started a reverse shell, although shell access should not be possible by design on these appliances.

SonicWall’s Product Security Incident Response Team (PSIRT) tried to determine how this was possible but could not come up with an explanation, and one answer could be the exploitation of an unknown security issue.

With shell access on the appliance, the threat actor ran reconnaissance and file manipulation activities, and imported settings that included new network access control policy rules to allow the hacker’s IP addresses.

### OVERSTEP rootkit leaves no clues

After this, UNC6148 deployed the OVERSTEP rootkit through a series of commands that decoded the binary from base64 and planted it as a .ELF file.

“Following the installation, the attacker manually cleared the system logs before restarting the appliance, activating the OVERSTEP backdoor” - Google Threat Intelligence Group

OVERSTEP acts as a backdoor that establishes a reverse shell and steals passwords from the host. It also implements user-mode rootkit capabilities to keep its components hidden on the host.

The rootkit component gave the threat actor long-term persistence by loading and executing malicious code each time a dynamic executable starts.

OVERSTEP’s anti-forensic feature lets the attacker selectively delete log entries and thus cover their tracks. This capability and the lack of command history on disk denied researchers’ visibility in the threat actor’s post-compromise activities.

However, GTIG warns that OVERSTEP can steal sensitive files such as the _persist.db_ database and certificate files, which give hackers access to credentials, OTP seeds, and certificates that allow persistence.

While researchers cannot determine the true purpose of UNC6148’s attacks, they highlight “noteworthy overlaps” in this threat actor’s activity and analysis of incidents where Abyss-related ransomware was deployed.

In late 2023, Truesec researchers [investigated](https://www.truesec.com/hub/blog/web-shell-on-a-sonicwall-sma) an Abyss ransomware incident that occurred after hackers deployed a web shell on an SMA appliance, hiding mechanism, and established persistence across firmware updates.

A few months later in March 2024, InfoGuard AG incident responder Stephan Berger [published a post](https://dfir.ch/posts/microsocks%5Fsonicwall/) describing a similar compromise of an SMA device that ended with the deployment of the same Abyss malware.

Organizations with SMA appliances are recommended to check the devices for potential compromise by acquiring disk images, which should prevent interference from the rootkit.

GTIG provides a set of indicators of compromise along with the signs analysts should look for to determine if the device was hacked.