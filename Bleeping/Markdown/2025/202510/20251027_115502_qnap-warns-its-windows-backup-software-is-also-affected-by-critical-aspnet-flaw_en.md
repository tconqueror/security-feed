# QNAP warns of critical ASP.NET flaw in its Windows backup software

![QNAP](https://www.bleepstatic.com/content/hl-images/2025/01/23/QNAP.jpg)

QNAP warned customers to patch a critical ASP.NET Core vulnerability that also impacts the company's NetBak PC Agent, a Windows utility for backing up data to a QNAP network-attached storage (NAS) device.

Tracked as [CVE-2025-55315](https://nvd.nist.gov/vuln/detail/CVE-2025-55315), this security bypass flaw was found in the Kestrel ASP.NET Core web server and enables attackers with low privileges to hijack other users' credentials or bypass front-end security controls via [HTTP request smuggling](https://cwe.mitre.org/data/definitions/444.html).

"NetBak PC Agent installs and depends on Microsoft ASP.NET Core components during setup. Therefore, computers running NetBak PC Agent may contain an affected version of ASP.NET Core if the system has not been updated," [QNAP said](https://www.qnap.com/en/security-advisory/qsa-25-44).

"QNAP strongly recommends users ensure their Windows systems have the latest Microsoft ASP.NET Core updates installed."

To secure their systems against potential attacks, QNAP users are advised to either reinstall the NetBak PC Agent app to get the latest ASP.NET Core runtime components or manually update ASP.NET Core on their PCs by downloading and installing the latest ASP.NET Core Runtime (Hosting Bundle) from the [.NET 8.0 download page](https://dotnet.microsoft.com/en-us/download/dotnet/8.0).

As .NET security technical program manager Barry Dorrans [explained two weeks ago](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-highest-severity-aspnet-core-flaw-ever/), when Microsoft patched this vulnerability (which was flagged with the "highest ever" severity rating received by an ASP.NET Core security flaw), the impact of CVE-2025-55315 attacks depends on the targeted ASP.NET application.

Successful exploitation could allow the attackers to log in as another user (for privilege escalation), bypass cross-site request forgery (CSRF) checks, or perform injection attacks.

"If successfully exploited, an authenticated attacker could send specially crafted HTTP requests to the web server, resulting in unauthorized access to sensitive data, modification of server files, or limited denial-of-service conditions," QNAP added.

In January, QNAP also released security updates to patch half a dozen rsync vulnerabilities in its HBS 3 Hybrid Backup Sync 25.1.x, the company's [data backup and disaster recovery solution,](http://www.qnap.com/en/software/hybrid-backup-sync) that could allow remote attackers to execute maliciously crafted code on unpatched Network Attached Storage (NAS) devices.