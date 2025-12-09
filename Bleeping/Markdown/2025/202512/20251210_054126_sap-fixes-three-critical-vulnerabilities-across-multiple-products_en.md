# SAP fixes three critical vulnerabilities across multiple products

![SAP](https://www.bleepstatic.com/content/hl-images/2025/05/14/SAP.jpg)

SAP has released its December security updates addressing 14 vulnerabilities across a range of products, including three critical-severity flaws.

The most severe (CVSS score: 9.9) of all the issues is [CVE-2025-42880](https://www.cve.org/CVERecord?id=CVE-2025-42880), a code injection problem impacting SAP Solution Manager ST 720.

"Due to missing input sanitation, SAP Solution Manager allows an authenticated attacker to insert malicious code when calling a remote-enabled function module," reads the flaw's description.

"This could provide the attacker with full control of the system, hence leading to high impact on confidentiality, integrity, and availability of the system."

SAP Solution Manager is the vendor's central lifecycle management and monitoring platform used by enterprises for system monitoring, technical configuration, incident and service desk, documentation hub, and test management.

The next most severe flaw SAP fixed this month concerns multiple Apache Tomcat vulnerabilities impacting SAP Commerce Cloud components in versions HY\_COM 2205, COM\_CLOUD 2211, and COM\_CLOUD 2211-JDK21.

The flaws are tracked in SAP Commerce Cloud under a single identifier, [CVE-2025-55754](https://www.cve.org/CVERecord?id=CVE-2025-55754), given a CVSS severity rating of 9.6.

SAP Commerce Cloud is an enterprise-grade e-commerce platform backing large-scale online stores with product catalogs, pricing, promotions, checkout, order management, customer accounts, and ERP/CRM integration. It is generally used by large retailers and global brands.

The third critical (CVSS score: 9.1) flaw fixed this month is [CVE-2025-42928](https://www.cve.org/CVERecord?id=CVE-2025-42928), a deserialization vulnerability impacting SAP jConnect, which, under certain conditions, could allow a high-privileged user to achieve remote code execution on the target via specially crafted input.

SAP jConnect is a JDBC driver used by developers and database administrators to connect Java applications to SAP ASE and SAP SQL Anywhere databases.

SAP's [December 2025](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/december-2025.html) bulletin also lists fixes for five high-severity flaws and six medium-severity issues, including memory corruption, missing authentication and authorization checks, cross-site scripting, and information disclosure.

SAP solutions are deeply embedded in enterprise environments and manage sensitive, high-value workloads, making them a valuable target for attackers.

Earlier this year, SecurityBridge researchers [observed in-the-wild attacks](https://www.bleepingcomputer.com/news/security/critical-sap-s-4hana-vulnerability-now-exploited-in-attacks/) abusing a code-injection flaw (CVE-2025-42957) impacting SAP S/4HANA, Business One, and NetWeaver deployments.

SAP has not marked any of the 14 flaws as actively exploited in the wild, but administrators should deploy the fixes without delay.