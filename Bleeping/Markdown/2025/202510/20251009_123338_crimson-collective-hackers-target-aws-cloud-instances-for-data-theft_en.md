# Crimson Collective hackers target AWS cloud instances for data theft

![Crimson Collective hackers target AWS cloud instances for data theft](https://www.bleepstatic.com/content/hl-images/2025/09/08/hacker.jpg)

The 'Crimson Collective' threat group has been targeting AWS (Amazon Web Services) cloud environments for the past weeks, to steal data and extort companies.

The hackers claimed responsibility for the recent [Red Hat attack](https://www.bleepingcomputer.com/news/security/red-hat-confirms-security-incident-after-hackers-breach-gitlab-instance/), saying that they exfiltrated 570 GB of data from thousands of private GitLab repositories, and pressured the software company to pay a ransom.

Following the disclosure of the incident, Crimson Collective [partnered](https://www.bleepingcomputer.com/news/security/red-hat-data-breach-escalates-as-shinyhunters-joins-extortion/) with Scattered Lapsus$ Hunters to increase the extortion pressure on Red Hat.

An analysis from researchers at Rapid7 provides more information about Crimson Collective’s activity, which involves compromising long-term AWS access keys and identity and access management (IAM) accounts for privilege escalation.

The attackers use the open-source tool TruffleHog to discover exposed AWS credentials. After gaining access, they create new IAM users and login profiles via API calls and generate new access keys.

Next comes privilege escalation by attaching the ‘AdministratorAccess’ policy onto newly created users, granting Crimson Collective full AWS control.

![The observed attack flow](https://www.bleepstatic.com/images/news/u/1220909/2025/October/attackflow.jpg)

**The observed attack flow**  
_Source: Rapid7_

The threat actors take advantage of this level of access to enumerate users, instances, buckets, locations, database clusters, and applications, to plan the data collection and exfiltration phase.

They modify the RDS (Relational Database Service) master passwords to gain database access, create snapshots, and then export them to S3 (Simple Storage Service) for exfiltration via API calls.

Rapid7 also observed snapshots of EBS (Elastic Block Store) volumes, followed by the launching of new EC2 (Elastic Compute Cloud) instances. The EBS volumes were then attached under permissive security groups to facilitate data transfer.

After completing this step, Crimson Collective sends victims an extortion note via AWS Simple Email Service (SES) within the breached cloud environment, as well as to external email accounts.

![The Crimson Collective ransom note](https://www.bleepstatic.com/images/news/u/1220909/2025/October/ransom.jpg)

**The Crimson Collective ransom note**  
_Source: Rapid7_

The researchers note that Crimson Collective utilized multiple IP addresses in its data theft operations and reused some IP addresses across incidents, making tracking easier.

AWS told BleepingComputer that customers should "use short-term, least-privileged credentials and implement restrictive IAM policies."

"In the event a customer suspects their credentials may have been exposed, they can start by following the steps listed in this [post](https://repost.aws/knowledge-center/potential-account-compromise)," the cloud services supplier said. If customers have any questions about the security of their accounts, they are advised to contact [AWS support](http://support.console.aws.amazon.com/support/home).

In January 2025, [Halcyon reported](https://www.bleepingcomputer.com/news/security/ransomware-abuses-amazon-aws-feature-to-encrypt-s3-buckets/) about ransomware attacks targeting AWS environments by a threat actor named “Codefinger,” who, contrary to Crimson Collective, encrypted the targeted S3 buckets.

**Update \[13:37 ET\]**: _Article updated with a statement from AWS._

To mitigate these attacks and prevent catastrophic breaches from leaked AWS secrets, it is recommended to scan your environment for unknown exposure using open-source tools like the [S3crets Scanner](https://www.bleepingcomputer.com/news/security/new-open-source-tool-scans-public-aws-s3-buckets-for-secrets/), or others.

Rapid7 noted that Crimson Collective’s size and composition remain unknown; however, the threat group’s activity and extortion tactics should not be ignored.