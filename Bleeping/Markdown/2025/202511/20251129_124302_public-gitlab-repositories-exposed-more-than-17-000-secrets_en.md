# Public GitLab repositories exposed more than 17,000 secrets

![Public GitLab repositories exposed more than 17,000 secrets](https://www.bleepstatic.com/content/hl-images/2022/04/01/GitLab.jpg)

After scanning all 5.6 million public repositories on GitLab Cloud, a security engineer discovered more than 17,000 exposed secrets across over 2,800 unique domains.

Luke Marshall used the TruffleHog open-source tool to check the code in the repositories for sensitive credentials like API keys, passwords, and tokens.

The researcher previously [scanned Bitbucket](https://trufflesecurity.com/blog/scanning-2-6-million-public-bitbucket-cloud-repositories-for-secrets), where he found 6,212 secrets spread over 2.6 million repositories. He also checked the [Common Crawl dataset](https://www.bleepingcomputer.com/news/security/nearly-12-000-api-keys-and-passwords-found-in-ai-training-dataset/) that is used to train AI models, which exposed 12,000 valid secrets.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

GitLab is a web-based Git platform used by software developers, maintainers, and DevOps teams to host code, for CI/CD operations, development collaboration, and repository management.

Marshall used a GitLab public API endpoint to enumerate every public GitLab Cloud repository, using a custom Python script to paginate through all results and sort them by project ID.

This process returned 5.6 million non-duplicate repositories, and their names were sent to an AWS Simple Queue Service (SQS).

Next, an AWS Lambda function pulled the repository name from SQS, ran TruffleHog against it, and logged the results.

“Each Lambda invocation executed a simple TruffleHog scan command with concurrency set to 1000,” [describes Marshall](https://trufflesecurity.com/blog/scanning-5-6-million-public-gitlab-repositories-for-secrets).

“This setup allowed me to complete the scan of 5,600,000 repositories in just over 24 hours.”

The total cost for the entire public GitLab Cloud repositories using the above method was $770.

The researcher found 17,430 verified live secrets, nearly three times as many as in Bitbucket, and with a 35% higher secret density (secrets per repository), too.

Historical data shows that most leaked secrets are newer than 2018\. However, Marshall also found some very older secrets dating from 2009, which are still valid today.

![Volume of exposed secrets](https://www.bleepstatic.com/images/news/u/1220909/2025/November/volume.jpg)

**Volume of exposed secrets**  
_Source: Truffle Security_

The largest number of leaked secrets, over 5,200 of them, were Google Cloud Platform (GCP) credentials, followed by MongoDB keys, Telegram bot tokens, and OpenAI keys.

The researcher also found a little over 400 GitLab keys leaked in the scanned repositories.

**Types of exposed secrets on GitLab**  
_Source: Truffle Security_

In the spirit of responsible disclosure and because the discovered secrets were associated with 2,804 unique domains, Marshall relied on automation to notify affected parties and used Claude Sonnet 3.7 with web search ability and a Python script to generate emails.

In the process, the researcher collected multiple bug bounties that amounted to $9,000.

The researcher reports that many organizations revoked their secrets in response to his notifications. However, an undisclosed number of secrets continue to be exposed on GitLab.