# Adobe issues emergency fixes for AEM Forms zero-days after PoCs released

![Adobe](https://www.bleepstatic.com/content/hl-images/2023/09/12/adobe.jpg)

Adobe released emergency updates for two zero-day flaws in Adobe Experience Manager (AEM) Forms on JEE after a PoC exploit chain was disclosed that can be used for unauthenticated, remote code execution on vulnerable instances.

The flaws are tracked as CVE-2025-54253 and CVE-2025-54254:

* **CVE-2025-54253:** Misconfiguration allowing arbitrary code execution. Rated "Critical" with a CVSS score of 8.6.
* **CVE-2025-54254:** Improper Restriction of XML External Entity Reference (XXE) allowing arbitrary file system read. Rated "Critical" with a maximum-severity 10.0 CVSS score.

Adobe has [fixed the flaws](https://helpx.adobe.com/security/products/aem-forms/apsb25-82.html) in the latest versions as [described in this advisory](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/troubleshooting/mitigating-xxe-and-configuration-vulnerabilities-for-experience-manager-forms-jee).

The vulnerabilities were discovered by Shubham Shah and Adam Kues of Searchlight Cyber, who disclosed them to Adobe on April 28, 2025, along with a third issue, CVE-2025-49533.

Adobe initially patched CVE-2025-49533 on August 5, leaving the other two flaws unfixed for over 90 days.

After warning Adobe of their disclosure timeline, the researchers published a [technical write-up](https://slcyber.io/assetnote-security-research-center/struts-devmode-in-2025-critical-pre-auth-vulnerabilities-in-adobe-experience-manager-forms/) on July 29 detailing how the vulnerabilities work and how they can be exploited.

According to the researchers, CVE-2025-49533 is a Java deserialization flaw in the FormServer module that allows unauthenticated remote code execution (RCE). A servlet processes user-supplied data by decoding and deserializing it without validation, letting attackers send malicious payloads to execute commands on the server.

The XXE vulnerability, tracked as CVE-2025-54254, affects a web service that handles SOAP authentication. By submitting a specially crafted XML payload, attackers can trick the service into exposing local files, such as win.ini, without authentication.

Finally, the CVE-2025-54253 flaw is caused by an authentication bypass in /adminui module in combination with a misconfigured developer setting.

The researchers found that Struts2's development mode was left enabled by mistake, allowing attackers to execute OGNL expressions through debug parameters sent in HTTP requests.

As the flaws allow remote code execution on vulnerable servers, all admins are advised to install the latest updates and hotfixes as soon as possible.

If that is not possible, the researchers strongly recommend restricting access to the platform from the internet.