# SAP fixes hardcoded credentials flaw in SQL Anywhere Monitor

![SAP fixes hardcoded credentials flaw in SQL Anywhere Monitor](https://www.bleepstatic.com/content/hl-images/2022/02/09/SAP.jpg)

SAP has released its November security updates that address multiple security vulnerabilities, including a maximum severity flaw in the non-GUI variant of the SQL Anywhere Monitor and a critical code injection issue in the Solution Manager platform.

The security problem in SQL Anywhere Monitor is tracked as CVE-2025-42890 and consists of hardcoded credentials. Because of the elevated risk, the vulnerability received the maximum severity score of 10.0.

"SQL Anywhere Monitor (Non-GUI) baked credentials into the code, exposing the resources or functionality to unintended users and providing attackers with the possibility of arbitrary code execution," reads the [description](https://nvd.nist.gov/vuln/detail/CVE-2025-42890) for the flaw.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Depending on how they are used, an attacker who obtains the credentials can use them to acceess administrative functions.

SQL Anywhere Monitor is a database monitoring and alert tool, part of the SQL Anywhere suite, typically used by organizations managing distributed or remote databases.

The non-GUI monitor component is typically deployed on unattended appliances where it runs without frequent human oversight.

The second critical vulnerability, identified as CVE-2025-42887, has a severity score of 9.9 and affects the SAP Solution Manager, a platform for application lifecycle management.

“Due to missing input sanitation, SAP Solution Manager allows an authenticated attacker to insert malicious code when calling a remote-enabled function module,” [reads the entry](https://nvd.nist.gov/vuln/detail/CVE-2025-42887) in the National Vulnerability Database.

“This could provide the attacker with full control of the system hence leading to high impact on confidentiality, integrity and availability of the system.”

SAP Solution Manager is a centralized management and monitoring platform for SAP environments, typically used by large enterprises that operate complex networks encompassing ERP, CRM, and analytics solutions.

In the context of the [November 2025 security updates](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/november-2025.html) pack, SAP also released fixes for one high-severity flaw (CVE-2025-42940) and 14 other medium-severity vulnerabilities.

Also, the German software giant released updates for CVE-2025-42944, a critical flaw in NetWeaver that was initially [addressed last month](https://www.bleepingcomputer.com/news/security/sap-fixes-maximum-severity-netweaver-command-execution-flaw/).

SAP products, widely deployed across large enterprises and entrusted with mission-critical data, are frequent targets for threat actors seeking high-value access.

Earlier this year, SecurityBridge researchers reported [active exploitation](https://www.bleepingcomputer.com/news/security/critical-sap-s-4hana-vulnerability-now-exploited-in-attacks/) of a critical code-injection vulnerability, tracked as CVE-2025-42957, affecting SAP S/4HANA, Business One, and NetWeaver systems.

No active exploitation has been detected for the two critical flaws that SAP fixed today, but system administrators are advised to apply the available updates as soon as possible and follow the vendor’s mitigation recommendations for [CVE-2025-42890](https://me.sap.com/notes/3666261) and [CVE-2025-42887](https://me.sap.com/notes/3668705) (accessible only to account holders).