# Trend Micro fixes critical vulnerabilities in multiple products

![Trend Micro fixes critical vulnerabilities in multiple products](https://www.bleepstatic.com/content/hl-images/2022/04/01/Trend_Micro__headpic.jpg)

Trend Micro has released security updates to address multiple critical-severity remote code execution and authentication bypass vulnerabilities that impact its Apex Central and Endpoint Encryption (TMEE) PolicyServer products.

The security vendor underlines that it has seen no evidence of active exploitation in the wild for any of them. However, immediate application of the security updates is recommended to address the risks.

Trend Micro Endpoint Encryption PolicyServer is a central management server for Trend Micro Endpoint Encryption (TMEE), providing full disk encryption and removable media encryption for Windows-based endpoints.

The product is used in enterprise environments in regulated industries where compliance with data protection standards is critical.

With the latest update, Trend Micro addressed the following high-severity and critical flaws:

* [**CVE-2025-49212**](https://www.zerodayinitiative.com/advisories/ZDI-25-369/) **\-** A pre-authentication remote code execution flaw caused by insecure deserialization in the PolicyValueTableSerializationBinder class. Remote attackers can exploit it to execute arbitrary code as SYSTEM without requiring login
* [**CVE-2025-49213**](https://www.zerodayinitiative.com/advisories/ZDI-25-370/)**\-**A pre-authentication remote code execution vulnerability in the PolicyServerWindowsService class, stemming from deserialization of untrusted data. Attackers can run arbitrary code as SYSTEM with no authentication required
* **[CVE-2025-49216](https://www.zerodayinitiative.com/advisories/ZDI-25-373/)** **\-** An authentication bypass flaw in the DbAppDomain service due to a broken auth implementation. Remote attackers can fully bypass login and perform admin-level actions without credentials
* [**CVE-2025-49217**](https://www.zerodayinitiative.com/advisories/ZDI-25-374/) _\-_ A pre-authentication RCE vulnerability in the ValidateToken method, triggered by unsafe deserialization. While slightly harder to exploit, it still allows unauthenticated attackers to run code as SYSTEM

It should be noted that while Trend Micro's [security bulletin](https://success.trendmicro.com/en-US/solution/KA-0019928) for Endpoint Encryption PolicyServer lists all four vulnerabilities above as critical, ZDI's advisory assessed CVE-2025-49217 as being a high-severity vulnerability.

Additional issues addressed by the latest version of Endpoint Encryption PolicyServer include four more high-severity vulnerabilities (e.g., SQL injection and privileges escalation issues).

All of the vulnerabilities were addressed in version 6.0.0.4013 (Patch 1 Update 6). The flaws impact all versions up to the latest, and there are no mitigations or workarounds for them.

---

A second [set of problems](https://success.trendmicro.com/en-US/solution/KA-0019926) that Trend Micro addressed impacts Apex Central, a centralized security management console used for monitoring, configuring, and managing multiple Trend Micro products and security agents across an organization.

Both issues are critical-severity, pre-authentication remote code execution flaws:

* [**CVE-2025-49219**](https://www.zerodayinitiative.com/advisories/ZDI-25-366/) – A pre-authentication RCE flaw in the GetReportDetailView method of Apex Central caused by insecure deserialization. Exploiting this allows unauthenticated attackers to execute code in the context of NETWORK SERVICE. (CVSS 9.8)
* [**CVE-2025-49220**](https://www.zerodayinitiative.com/advisories/ZDI-25-367/) – A pre-auth RCE in Apex Central in the ConvertFromJson method. Improper input validation during deserialization lets attackers execute arbitrary code remotely without authentication. (CVSS 9.8)

The issues were fixed in Patch B7007 for Apex Central 2019 (on premise), while they are automatically applied on backend for Apex Central as a Service.