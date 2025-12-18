# HPE warns of maximum severity RCE flaw in OneView software

[![Hewlett Packard Enterprise HPE](https://www.bleepstatic.com/content/hl-images/2025/12/18/Hewlett_Packard_Enterprise_HPE.jpg)](https://www.bleepingcomputer.com/news/security/hpe-warns-of-hardcoded-passwords-in-aruba-access-points/)

Hewlett Packard Enterprise (HPE) has patched a maximum-severity vulnerability in its HPE OneView software that enables attackers to execute arbitrary code remotely.

OneView is HPE's infrastructure management software that helps IT admins streamline operations and automate the management of servers, storage, and networking devices from a centralized interface.

This critical security flaw ([CVE-2025-37164](https://nvd.nist.gov/vuln/detail/CVE-2025-37164)) was reported by Vietnamese security researcher Nguyen Quoc Khanh (brocked200) to the company's security team.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

It affects all OneView versions released before v11.00 and can be exploited by unauthenticated threat actors in low-complexity [code injection](https://cwe.mitre.org/data/definitions/94.html) attacks to gain remote code execution on unpatched systems.

"A potential security vulnerability has been identified in Hewlett Packard Enterprise OneView Software. This vulnerability could be exploited, allowing a remote unauthenticated user to perform remote code execution," HPE warned in a [Tuesday advisory](https://support.hpe.com/hpesc/public/docDisplay?docId=hpesbgn04985en%5Fus&docLocale=en%5FUS#vulnerability-summary-1).

There are no workarounds or mitigations for CVE-2025-37164, so admins are advised to patch vulnerable systems as soon as possible.

HPE has yet to confirm whether this vulnerability has been targeted in attacks and says that affected organizations can upgrade to OneView version 11.00 or later, available [through HPE's Software Center](https://myenterpriselicense.hpe.com/cwp-ui/product-download-info/Z7550-63180/-/sw%5Ffree), to patch it.

On devices running OneView versions 5.20 through 10.20, the vulnerability can be addressed by deploying a security hotfix, which must be reapplied after upgrading from version 6.60 or later to version 7.00.00, or after any HPE Synergy Composer reimaging operations.

Separate downloads are available for the [virtual appliance security hotfix](https://myenterpriselicense.hpe.com/cwp-ui/product-details/HPE%5FOV%5FCVE%5F37164%5FZ7550-98077/-/sw%5Ffree) and the [Synergy security hotfix](https://support.hpe.com/hpesc/public/swd/detail?swCollectionId=MTX-64daeb5ed0df44a0) through dedicated support pages.

In June, HPE [patched eight vulnerabilities](https://www.bleepingcomputer.com/news/security/hewlett-packard-enterprise-warns-of-critical-storeonce-auth-bypass/) in StoreOnce, its disk-based backup and deduplication solution, including a critical-severity authentication bypass and three remote code execution flaws.

One month later, in July, it [warned of hardcoded credentials](https://www.bleepingcomputer.com/news/security/hpe-warns-of-hardcoded-passwords-in-aruba-access-points/) in Aruba Instant On Access Points that could allow attackers to access the web interface after bypassing standard device authentication.

HPE has over 61,000 employees worldwide and has reported revenues of $30.1 billion in 2024\. Its products and services are used by over 55,000 organizations worldwide, including 90% of Fortune 500 companies.