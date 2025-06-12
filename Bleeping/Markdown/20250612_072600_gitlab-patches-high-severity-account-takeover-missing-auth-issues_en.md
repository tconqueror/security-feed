# GitLab patches high severity account takeover, missing auth issues

![GitLab](https://www.bleepstatic.com/content/hl-images/2024/05/01/GitLab.jpg)

GitLab has released security updates to address multiple vulnerabilities in the company's DevSecOps platform, including ones enabling attackers to take over accounts and inject malicious jobs in future pipelines.

The company released GitLab Community and Enterprise versions 18.0.2, 17.11.4, and 17.10.8 to address these security flaws and urged all admins to upgrade immediately.

"These versions contain important bug and security fixes, and we strongly recommend that all self-managed GitLab installations be upgraded to one of these versions immediately," the company [warned](https://about.gitlab.com/releases/2025/06/11/patch-release-gitlab-18-0-2-released/#cve-2025-5121---missing-authorization-issue-impacts-gitlab-ultimate-ee). "GitLab.com is already running the patched version. GitLab Dedicated customers do not need to take action."

On Wednesday, GitLab patched an HTML injection issue tracked as [CVE-2025-4278](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-4278) that can let remote attackers take over accounts by injecting malicious code into the search page.

It also released patches for a missing authorization issue ([CVE-2025-5121](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-5121)) that impacts GitLab Ultimate EE and allows remote threat actors to inject malicious CI/CD jobs into any project's future CI/CD pipelines.

GitLab pipelines are a Continuous Integration/Continuous Deployment (CI/CD) system feature that lets users sequentially build, test, or deploy code changes or automatically run processes and tasks in parallel.

However, successful exploitation requires attackers to have authenticated access to GitLab instances with a GitLab Ultimate license.

The company also patched a cross-site scripting vulnerability ([CVE-2025-2254](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-2254)) that could let successful attackers act in the context of a legitimate user and a denial of service (DoS) flaw ([CVE-2025-0673](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-0673)) that can allow malicious actors to trigger infinite redirect loops, causing memory exhaustion and denying access to legitimate users.

GitLab repositories are often targeted in attacks because of the sensitive information and data they contain, as proven by recent breaches reported by multinational car-rental company [Europcar Mobility Group](https://www.bleepingcomputer.com/news/security/europcar-gitlab-breach-exposes-data-of-up-to-200-000-customers/) and education giant [Pearson](https://www.bleepingcomputer.com/news/security/education-giant-pearson-hit-by-cyberattack-exposing-customer-data/), which had their GitLab repos compromised since the start of the year.

GitLab's DevSecOps platform has over 30 million registered users and is utilized by more than 50% of Fortune 100 companies, including Goldman Sachs, Airbus, T-Mobile, Lockheed Martin, Nvidia, and UBS.