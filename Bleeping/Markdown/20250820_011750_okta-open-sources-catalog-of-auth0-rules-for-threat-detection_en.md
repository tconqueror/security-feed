# Okta open-sources catalog of Auth0 rules for threat detection

![Okta open-sources Auth0 rules catalog for threat detection](https://www.bleepstatic.com/content/hl-images/2022/02/25/Okta2.jpg)

Okta has open-sourced ready-made Sigma-based queries for Auth0 customers to detect account takeovers, misconfigurations, and suspicious behavior in event logs.

Auth0 is Okta's identity and access management (IAM) platform used by organizations for login, authentication, and user management services.

By releasing the detection rules, the company aims to help security teams quickly analyze Auth0 logs for suspicious activity that could indicate intrusion attempts, account takeovers, the creation of rogue admin accounts, SMS bombing, and token theft.

Until now, Auth0 customers had to build their own detection rules from event logs or rely on what came out-of-the-box in Auth0’s Security Center.

With the launch of Customer Detection Catalog, a curated, open-source, community-driven repository, Okta provides developers, tenant administrators, DevOps teams, SOC analysts, and threat hunters a means to upgrade their proactive threat detection.

“The Auth0 Customer Detection Catalog allows security teams to integrate custom, real-world detection logic directly into their log streaming and monitoring tools, enriching the detection capabilities of the Auth0 platform,” [reads the announcement](https://sec.okta.com/articles/2025/08/auth0-detection-catalog/).

“The catalog provides a growing collection of pre-built queries, contributed by Okta personnel and the wider security community, that surface suspicious activities like anomalous user behavior, potential account takeovers and misconfigurations.”

The [public GitHub repository](https://github.com/auth0/auth0-customer-detections) includes Sigma rules, making it broadly usable across SIEM and logging tools and allowing contributions and validations from Okta’s entire customer base.

Auth0 users can take advantage of the new Customer Detection Catalog through these steps:

1. Access the GitHub repository and clone or download the repository locally.
2. Install a Sigma converter, such as sigma-cli, to translate the provided rules into the query syntax supported by your SIEM or log analysis platform.
3. Import the converted queries into your monitoring workflow and configure them to run against Auth0 event logs.
4. Run the rules against historical logs to validate that they work as intended, and adjust filters to reduce false positives.
5. Deploy the validated detections into production, and regularly check the GitHub repository to pull any important updates submitted by Okta or the community.

Okta welcomes anyone writing new rules or refining existing ones to submit them to the repo through a GitHub pull request to help improve coverage for the whole Auth0 community.