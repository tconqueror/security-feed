# Brother printer bug in 689 models exposes default admin passwords

![Brother printer](https://www.bleepstatic.com/content/hl-images/2025/06/26/brother-printer.jpg)

A total of 689 printer models from Brother, along with 53 other models from Fujifilm, Toshiba, and Konica Minolta, come with a default administrator password that remote attackers can generate. Even worse, there is no way to fix the flaw via firmware in existing printers.

The flaw, tracked under [CVE-2024-51978](https://nvd.nist.gov/vuln/detail/CVE-2024-51978), is part of a set of eight vulnerabilities [discovered by Rapid7 researchers](https://www.rapid7.com/blog/post/multiple-brother-devices-multiple-vulnerabilities-fixed/) during a lengthy examination of Brother hardware.

| CVE            | Description                                                                            | Affected Service                                 | CVSS           |
| -------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------ | -------------- |
| CVE-2024-51977 | An unauthenticated attacker can leak sensitive information.                            | HTTP (Port 80), HTTPS (Port 443), IPP (Port 631) | 5.3 (Medium)   |
| CVE-2024-51978 | An unauthenticated attacker can generate the device's default administrator password.  | HTTP (Port 80), HTTPS (Port 443), IPP (Port 631) | 9.8 (Critical) |
| CVE-2024-51979 | An authenticated attacker can trigger a stack based buffer overflow.                   | HTTP (Port 80), HTTPS (Port 443), IPP (Port 631) | 7.2 (High)     |
| CVE-2024-51980 | An unauthenticated attacker can force the device to open a TCP connection.             | Web Services over HTTP (Port 80)                 | 5.3 (Medium)   |
| CVE-2024-51981 | An unauthenticated attacker can force the device to perform an arbitrary HTTP request. | Web Services over HTTP (Port 80)                 | 5.3 (Medium)   |
| CVE-2024-51982 | An unauthenticated attacker can crash the device.                                      | PJL (Port 9100)                                  | 7.5 (High)     |
| CVE-2024-51983 | An unauthenticated attacker can crash the device.                                      | Web Services over HTTP (Port 80)                 | 7.5 (High)     |
| CVE-2024-51984 | An authenticated attacker can disclose the password of a configured external service.  | LDAP, FTP                                        | 6.8 (Medium)   |

This crucial vulnerability can be chained with other vulnerabilities discovered by Rapid7 to determine the admin password, take control of devices, perform remote code execution, crash them, or pivot within the networks they're connected to.

Not all of the flaws affect every one of the 689 Brother printer models, but other manufacturers, including Fujifilm (46 models), Konica Minolta (6), Ricoh (5), and Toshiba (2), are impacted as well.

![Number of impacted models for each of the eight flaws](https://www.bleepstatic.com/images/news/u/1220909/2025/June/impact.jpg)

**Number of impacted models for each of the eight flaws**  
_Source: Rapid7_

## Insecure password generation

The default password in the impacted printers is generated during manufacturing using a custom algorithm based on the device's serial number.

According to a [detailed technical analysis](https://assets.contentstack.io/v3/assets/blte4f029e766e6b253/blt6495b3c6adf2867f/685aa980a26c5e2b1026969c/vulnerability-disclosure-whitepaper.pdf) by Rapid7, the password generation algorithm follows an easily reversible process:

1. Take the first 16 characters of the serial number.
2. Append 8 bytes derived from a static "salt" table.
3. Hash the result with SHA256.
4. Base64-encode the hash.
5. Take the first eight characters and substitute some letters with special characters.

Attackers can leak the serial number of the target printer using various methods or by exploiting [CVE-2024-51977](https://nvd.nist.gov/vuln/detail/CVE-2024-51977). They can then use the algorithm to generate the default admin password and log in as admin.

From there, they may reconfigure the printer, access stored scans, read address books, exploit [CVE-2024-51979](https://nvd.nist.gov/vuln/detail/CVE-2024-51979) for remote code execution, or exploit [CVE-2024-51984](https://nvd.nist.gov/vuln/detail/CVE-2024-51984) to harvest credentials.

Rapid7 began its disclosure process in May 2024 and was aided by JPCERT/CC in coordinating disclosures to other manufacturers.

Although all flaws have been fixed in firmware updates made available by impacted manufacturers, the case with CVE-2024-51978 is complicated in terms of risk management.

The vulnerability is rooted in the password generation logic used in hardware manufacturing, and hence, any devices made before its discovery will have predictable passwords unless users change them.

"Brother has indicated that this vulnerability cannot be fully remediated in firmware, and has required a change to the manufacturing process of all affected models," explains Rapid7 regarding CVE-2024-51978.

Users of existing Brother printers listed in the impacted models should consider their devices vulnerable and immediately change the default admin password, followed by applying the firmware updates.

In general, it is recommended to restrict access to the printer's admin interfaces over unsecured protocols and external networks.

Security bulletins with instructions on what users should do are available for [Brother](https://support.brother.com/g/b/faqend.aspx?c=us&lang=en&prod=group2&faqid=faq00100846%5F000), [Konica Minolta](https://www.konicaminolta.com/global-en/security/advisory/pdf/km-2025-0001.pdf), [Fujifilm](https://www.fujifilm.com/fbglobal/eng/company/news/notice/2025/0625%5Fannounce.html), [Ricoh](https://www.ricoh.com/products/security/vulnerabilities/vul?id=ricoh-2025-000007), and [Toshiba](https://www.toshibatec.com/information/20250625%5F02.html).