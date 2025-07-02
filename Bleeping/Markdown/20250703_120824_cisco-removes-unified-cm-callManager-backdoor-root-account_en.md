# Cisco warns that Unified CM has hardcoded root SSH credentials

![Cisco](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco-headpic.jpg)

Cisco has removed a backdoor account from its Unified Communications Manager (Unified CM), which would have allowed remote attackers to log in to unpatched devices with root privileges.

Cisco Unified Communications Manager (CUCM), formerly known as Cisco CallManager, serves as the central control system for Cisco's IP telephony systems, handling call routing, device management, and telephony features.

The vulnerability (tracked as [CVE-2025-20309](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cucm-ssh-m4UBdpE7)) was rated as maximum severity, and it is caused by static user credentials for the root account, which were intended for use during development and testing.

According to a Cisco security advisory released on Wednesday, CVE-2025-20309 affects Cisco Unified CM and Unified CM SME Engineering Special (ES) releases 15.0.1.13010-1 through 15.0.1.13017-1, regardless of the device configuration.

The company added that there are no workarounds that address the vulnerability. Admins can only fix the flaw and remove the backdoor account by upgrading vulnerable devices to Cisco Unified CM and Unified CM SME 15SU3 (July 2025) or by applying the CSCwp27755 patch file [available here](https://software.cisco.com/download/home/286331940/type/286319173/release/COP-Files).

"A vulnerability in Cisco Unified Communications Manager (Unified CM) and Cisco Unified Communications Manager Session Management Edition (Unified CM SME) could allow an unauthenticated, remote attacker to log in to an affected device using the root account, which has default, static credentials that cannot be changed or deleted," Cisco [explained](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cucm-ssh-m4UBdpE7).

Following successful exploitation, attackers could gain access to the vulnerable systems and execute arbitrary commands with root privileges.

While the Cisco Product Security Incident Response Team (PSIRT) is not yet aware of proof-of-concept code available online or exploitation in attacks, the company has released indicators of compromise to help identify impacted devices.

As Cisco stated, exploitation of CVE-2025-20309 would result in a log entry to /var/log/active/syslog/secure for the root user with root permissions. Since logging of this event is enabled by default, admins can retrieve the logs to look for exploitation attempts by running the following command from the command line: `file get activelog syslog/secure`.

This is far from the first backdoor account Cisco had to remove from its products in recent years, with previous hardcoded credentials found in its [IOS XE](https://www.bleepingcomputer.com/news/security/cisco-removes-backdoor-account-from-ios-xe-software/), [Wide Area Application Services (WAAS)](https://www.bleepingcomputer.com/news/security/cisco-removes-backdoor-account-fourth-in-the-last-four-months/), [Digital Network Architecture (DNA) Center](https://www.bleepingcomputer.com/news/security/hardcoded-password-found-in-cisco-enterprise-software-again/), and [Emergency Responder](https://www.bleepingcomputer.com/news/security/cisco-fixes-hard-coded-root-credentials-in-emergency-responder/) software.

More recently, Cisco [warned admins in April](https://www.bleepingcomputer.com/news/security/cisco-warns-of-cslu-backdoor-admin-account-used-in-attacks/) to patch a critical Cisco Smart Licensing Utility (CSLU) vulnerability that exposes a built-in backdoor admin account used in attacks. One month later, the company [removed a hardcoded JSON Web Token (JWT)](https://www.bleepingcomputer.com/news/security/cisco-fixes-max-severity-ios-xe-flaw-letting-attackers-hijack-devices/) that allows unauthenticated remote attackers to take over IOS XE devices.