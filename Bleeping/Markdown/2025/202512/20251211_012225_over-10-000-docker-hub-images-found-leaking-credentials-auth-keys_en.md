# Over 10,000 Docker Hub images found leaking credentials, auth keys

![Over 10,000 Docker Hub images found leaking credentials, auth keys](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker.jpg)

More than 10,000 Docker Hub container images expose data that should be protected, including live credentials to production systems, CI/CD databases, or LLM model keys.

The secrets impact a little over 100 organizations, among them are a Fortune 500 company and a major national bank.

Docker Hub is the largest container registry where developers upload, host, share, and distribute ready-to-use Docker images that contain everything necessary to run an application.

Developers typically use Docker images to streamline the entire software development and deployment lifecycle. However, as [past studies have shown](https://www.bleepingcomputer.com/news/security/thousands-of-images-on-docker-hub-leak-auth-secrets-private-keys/), carelessness in creating these images can result in exposing secrets that remain valid for extended periods.

After scanning container images uploaded to Docker Hub in November, security researchers at threat intelligence company Flare found that 10,456 of them exposed one or more keys.

The most frequent secrets were access tokens for various AI models (OpenAI, HuggingFace, Anthropic, Gemini, Groq). In total, the researchers found 4,000 such keys.

When examining the scanned images, the researchers discovered that 42% of them exposed at least five sensitive values.

"These multi-secret exposures represent critical risks, as they often provide full access to cloud environments, Git repositories, CI/CD systems, payment integrations, and other core infrastructure components," Flare notes in a [report](https://flare.io/learn/resources/docker-hub-secrets-exposed/) today.

![Size of secret exposure](https://www.bleepstatic.com/images/news/u/1220909/2025/December/size.jpg)

**Size of secret exposure**  
_Source: Flare_

Analyzing 205 namespaces enabled the researchers to identify a total of 101 companies, mostly small and medium-sized businesses, with a few large enterprises being present in the dataset.

Based on the analysis, most of the organizations with exposed secrets are in the software development sector, followed by entities in the market and industrial, and AI and intelligent systems.

More than 10 finance and banking companies had their sensitive data exposed.

![Types of firms that exposed secrets on Docker Hub in November](https://www.bleepstatic.com/images/news/u/1220909/2025/December/firm-types.jpg)

**Types of firms that exposed secrets on Docker Hub in November**  
_Source: Flare_

According to the researchers, one of the most frequent errors observed was the use of .ENV files that developers use to store database credentials, cloud access keys, tokens, and various authentication data for a project.

Additionally, they found hardcoded API tokens for AI services being hardcoded in Python application files, config.json files, YAML configs, GitHub tokens, and credentials for multiple internal environments.

Some of the sensitive data was present in the manifest of Docker images, a file that provides details about the image.

Many of the leaks appear to originate from the so-called 'shadow IT' accounts, which are Docker Hub accounts that fall outside of the stricter corporate monitoring mechanisms, such as those for personal use or belonging to contractors.

Flare notes that roughly 25% of developers who accidentally exposed secrets on Docker Hub realized the mistake and removed the leaked secret from the container or manifest file within 48 hours.

However, in 75% of these cases, the leaked key was not revoked, meaning that anyone who stole it during the exposure period could still use it later to mount attacks.

**Exposed secrets exploitation diagram**  
_Source: Flare_

Flare suggests that developers avoid storing secrets in container images, stop using static, long-lived credentials, and centralize their secrets management using a dedicated vault or secrets manager.

Organizations should implement active scanning across the entire software development life cycle and revoke exposed secrets and invalidate old sessions immediately.