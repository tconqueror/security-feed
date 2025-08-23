# Hewlett Packard Enterprise warns of critical StoreOnce auth bypass

![HPE](https://www.bleepstatic.com/content/hl-images/2021/05/27/HPE-headpic.jpg)

Hewlett Packard Enterprise (HPE) has issued a security bulletin to warn about eight vulnerabilities impacting StoreOnce, its disk-based backup and deduplication solution.

Among [the flaws fixed this time](http://support.hpe.com/hpesc/public/docDisplay?docId=hpesbst04847en%5Fus&docLocale=en%5FUS) is a critical severity (CVSS v3.1 score: 9.8) authentication bypass vulnerability tracked under [CVE-2025-37093](https://nvd.nist.gov/vuln/detail/CVE-2025-37093), three remote code execution bugs, two directory traversal problems, and a server-side request forgery issue.

The flaws impact all versions of the HPE StoreOnce Software before v4.3.11, which is now the recommended upgrade version.

Here's the complete list of the eight vulnerabilities HPE fixed in version 4.3.11:

* **CVE-2025-37089** – Remote Code Execution
* **CVE-2025-37090** – Server-Side Request Forgery
* **CVE-2025-37091** – Remote Code Execution
* **CVE-2025-37092** – Remote Code Execution
* **CVE-2025-37093** – Authentication Bypass
* **CVE-2025-37094** – Directory Traversal Arbitrary File Deletion
* **CVE-2025-37095** – Directory Traversal Information Disclosure
* **CVE-2025-37096** – Remote Code Execution

Not many details were disclosed about the flaws this time.

However, Zero Day Initiative (ZDI), which discovered them, [mentions](https://www.zerodayinitiative.com/advisories/ZDI-25-316/) that CVE-2025-37093 exists within the implementation of the machineAccountCheck method, resulting from improper implementation of an authentication algorithm.

Although CVE-2025-37093 is the only vulnerability rated as critical, others still carry significant risks even if they are typically categorized lower in the severity rating.

The ZDI explains that the authentication bypass problem is the key to unlocking the potential in all other flaws, so their risk isn't isolated.

The examples of CVE-2025-3794 and CVE-2025-37095, two medium-severity file deletion and information disclosure flaws, show that exploitation is practically easier than what's reflected in the score.

"This vulnerability allows remote attackers to disclose sensitive information on affected installations of Hewlett Packard Enterprise StoreOnce VSA," [explains ZDI](https://www.zerodayinitiative.com/advisories/ZDI-25-317/).

"Although authentication is required to exploit this vulnerability, the existing authentication mechanism can be bypassed."

Notably, the flaws were discovered and reported to HPE in October 2024, with seven full months having passed until fixes finally became available to customers. Still, there are no reports of active exploitation.

HPE StoreOnce is typically used for backup and recovery in large enterprises, data centers, cloud service providers, and generally, organizations handling big data or large virtualized environments.

StoreOnce integrates with backup software like HPE Data Protector, Veeam, Commvault, and Veritas NetBackup, ensuring business continuity and effective backup management.

That being said, administrators of potentially impacted environments must take immediate action and apply the available security updates to close the gaps.

HPE has listed no mitigations or workarounds for the eight flaws in the bulletin, so upgrading is the recommended solution.