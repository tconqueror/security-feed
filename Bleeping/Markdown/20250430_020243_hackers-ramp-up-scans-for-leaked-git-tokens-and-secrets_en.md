# Hackers ramp up scans for leaked Git tokens and secrets

![Hacker screens](https://www.bleepstatic.com/content/hl-images/2023/09/12/hacker-staring.jpg)

Threat actors are intensifying internet-wide scanning for Git configuration files that can reveal sensitive secrets and authentication tokens used to compromise cloud services and source code repositories.

In a new report from threat monitoring firm GreyNoise, researchers have recorded a massive spike in searches for exposed Git configs between April 20-21, 2025.

"GreyNoise observed nearly 4,800 unique IP addresses daily from April 20-21, marking a substantial increase compared to typical levels," [explained GreyNoise in the report](https://www.greynoise.io/blog/spike-git-configuration-crawling-risk-codebase-exposure).

"Although activity was globally distributed, Singapore ranked as both the top source and destination for sessions during this period, followed by the U.S. and Germany as the next most common destinations."

![IPs participating in the mass-scanning activity](https://www.bleepstatic.com/images/news/u/1220909/2025/April/diagram(1).jpg)

**IPs participating in the mass-scanning activity**  
_Source: GreyNoise_

Git configuration files are configuration files for Git projects that can include branch information, remote repository URLs, hooks and automation scripts, and most importantly, account credentials and access tokens.

Developers or companies deploy web applications without correctly excluding .git/ directories from public access, inadvertently exposing these files to anyone.

Scanning for those files is a standard reconnaissance activity that provides numerous opportunities for threat actors.

In October 2024, [Sysdig reported](https://www.bleepingcomputer.com/news/security/hackers-steal-15-000-cloud-credentials-from-exposed-git-config-files/) about a large-scale operation named "EmeraldWhale" which scanned for exposed Git config files, snatching 15,000 cloud account credentials from thousands of private repositories.

Stealing credentials, API keys, SSH private keys, or even accessing internal-only URLs allows the threat actors to access confidential data, craft tailored attacks, and hijack privileged accounts.

This is the exact method that the threat actors used to [breach Internet Archive's](https://www.bleepingcomputer.com/news/security/internet-archive-hacked-data-breach-impacts-31-million-users/) "The Wayback Machine" in October 2024, and then [maintain their foothold](https://www.bleepingcomputer.com/news/security/internet-archive-breached-again-through-stolen-access-tokens/) despite the owner's efforts to thwart the attacks.

GreyNoise reports that the recent activity is mostly targeted at Singapore, the United States, Spain, Germany, the UK, and India.

The malicious activity culminates in waves, with four notable cases since late 2024 being recorded in November, December, March, and April. The most recent one was the highest volume attack wave the researchers logged.

![Git config file scan waves](https://www.bleepstatic.com/images/news/u/1220909/2025/April/april-spike.jpg)

**Git config file scanning waves**  
_Source: GreyNoise_

To mitigate the risks that arise from these scans, it is recommended to block access to .git/ directories, configure web servers to prevent access to hidden files, monitor server logs for suspicious .git/config access, and rotate potentially exposed credentials.

If web server access logs show unauthorized access to Git configs, any credentials stored within them should be rotated immediately.