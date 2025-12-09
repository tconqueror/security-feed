# Fortinet warns of critical FortiCloud SSO login auth bypass flaws

![Fortinet](https://www.bleepstatic.com/content/hl-images/2025/04/09/Fortinet.jpg)

Fortinet has released security updates to address two critical vulnerabilities in FortiOS, FortiWeb, FortiProxy, and FortiSwitchManager that could allow attackers to bypass FortiCloud SSO authentication.

Threat actors can exploit the two security flaws tracked as CVE-2025-59718 (FortiOS, FortiProxy, FortiSwitchManager) and CVE-2025-59719 (FortiWeb) by abusing improper verification of cryptographic signature weaknesses in vulnerable products via a maliciously crafted SAML message.

However, as Fortinet explained in an advisory published today, the vulnerable FortiCloud feature is not enabled by default when the device is not FortiCare-registered.

"Please note that the FortiCloud SSO login feature is not enabled in default factory settings," Fortinet said. "However, when an administrator registers the device to FortiCare from the device's GUI, unless the administrator disables the toggle switch 'Allow administrative login using FortiCloud SSO' in the registration page, FortiCloud SSO login is enabled upon registration."

To protect their systems against attacks exploiting these vulnerabilities, admins are advised to temporarily disable the FortiCloud login feature (if enabled) until they upgrade to a non-vulnerable version.

To disable FortiCloud login, navigate to System -> Settings and switch "Allow administrative login using FortiCloud SSO" to Off. Alternatively, you can run the following command from the command-line interface:

```
config system global
set admin-forticloud-sso-login disable
end
```

Today, the company also patched an unverified password change vulnerability ([CVE-2025-59808](https://fortiguard.fortinet.com/psirt/FG-IR-25-599)) that allows attackers "who gained access to a victim's user account to reset the account credentials without being prompted for the account's password," and another one that can let threat actors authenticate using the hash in place of the password ([CVE-2025-64471](https://fortiguard.fortinet.com/psirt/FG-IR-25-984)).

Fortinet security vulnerabilities are frequently exploited (often as zero days) in both ransomware and cyber-espionage attacks.

For instance, Fortinet [disclosed](http://www.fortinet.com/blog/psirt-blogs/importance-of-patching-an-analysis-of-the-exploitation-of-n-day-vulnerabilities) in February that the [Chinese Volt Typhoon hacking group](https://www.bleepingcomputer.com/news/security/chinese-hackers-hid-in-us-infrastructure-network-for-5-years/) backdoored a [Dutch Ministry of Defence](https://www.bleepingcomputer.com/news/security/chinese-hackers-infect-dutch-military-network-with-malware/) military network using custom Coathanger remote access trojan (RAT) malware after exploiting two FortiOS SSL VPN flaws (CVE-2023-27997 and CVE-2022-42475).

More recently, in August, Fortinet patched [a command injection vulnerability](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-fortisiem-pre-auth-rce-flaw-with-exploit-in-the-wild/) (CVE-2025-25256) with publicly available exploit code in its FortiSIEM security monitoring solution, one day after cybersecurity company GreyNoise reported a [massive spike in brute-force attacks](https://www.bleepingcomputer.com/news/security/spike-in-fortinet-vpn-brute-force-attacks-raises-zero-day-concerns/) targeting Fortinet SSL VPNs.

In November, Fortinet [warned of a FortiWeb zero-day](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/) (CVE-2025-58034) that was actively exploited in attacks, one week after [confirming](https://www.bleepingcomputer.com/news/security/fortinet-confirms-silent-patch-for-fortiweb-zero-day-exploited-in-attacks/) that it had silently patched another [massively exploited](https://x.com/CERTCyberdef/status/1989311517611733454) FortiWeb zero-day (CVE-2025-64446).