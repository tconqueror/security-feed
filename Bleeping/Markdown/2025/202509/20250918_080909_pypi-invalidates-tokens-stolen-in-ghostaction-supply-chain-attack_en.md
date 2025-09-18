# PyPI invalidates tokens stolen in GhostAction supply chain attack

![PyPi](https://www.bleepstatic.com/content/hl-images/2025/09/18/PyPi.jpg)

The Python Software Foundation team has invalidated all PyPI tokens stolen in the GhostAction supply chain attack in early September, confirming that the threat actors didn't abuse them to publish malware.

These tokens are used to publish packages on the Python Package Index (PyPI), a software repository that acts as the default source for Python's package management tools and hosts hundreds of thousands of packages.

As PyPI admin Mike Fiedler explained, a GitGuardian employee reported on September 5th that malicious GitHub Actions workflows (like FastUUID) attempted to exfiltrate PyPI tokens to a remote server. Another GitGuardian researcher emailed PyPI Security with additional findings the same day, but their message ended up in the spam folder, delaying the incident response until September 10th.

As soon as it uncovered the full scope of the supply chain attack, GitGuardian opened GitHub issues in over 570 impacted repositories and notified the security teams of GitHub, npm, and PyPI.

Many project maintainers rotated their PyPI tokens, reverted changes to actions workflows, or removed affected workflows after being notified by GitGuardian of the incident. While the PyPI team found no evidence of compromised PyPI repositories during the investigation, it invalidated all affected publishing tokens and contacted project owners to assist in securing their accounts.

However, GitGuardian estimated at the time that [over 3,3000 secrets were stolen](https://www.bleepingcomputer.com/news/security/hackers-steal-3-325-secrets-in-ghostaction-github-supply-chain-attack/) in the GhostAction campaign, including PyPI, npm, DockerHub, GitHub, and Cloudflare API tokens, as well as AWS access keys and database credentials.

"This analysis revealed compromised tokens across multiple package ecosystems, including Rust crates and npm packages," GitGuardian said. "Several companies were found to have their entire SDK portfolio compromised, with malicious workflows affecting their Python, Rust, JavaScript, and Go repositories simultaneously."

![Secrets compromised in the GhostAction campaign](https://www.bleepstatic.com/images/news/u/1220909/2025/September/secrets.jpg)

_Secrets compromised in the GhostAction campaign (GitGuardian)_

On Tuesday, Fiedler advised PyPI package maintainers who use GitHub Actions to replace long-lived tokens with short-lived [Trusted Publishers](https://docs.pypi.org/trusted-publishers/) tokens, which would defend against this type of attack. Fiedler also urged them to [log into their accounts](https://pypi.org/manage/account/) and review [their security history](https://pypi.org/manage/account/#account-events) for any suspicious activity.

"After confirming that no PyPI accounts had been compromised, on September 15th I reached out to the maintainers of the affected projects to notify them of the situation, to let them know that their tokens had been invalidated, and recommend using Trusted Publishers with GitHub Actions to help protect their projects in the future," [Fiedler said](https://blog.pypi.org/posts/2025-09-16-github-actions-token-exfiltration/).

"Attackers targeted a wide variety of repositories, many of which had PyPI tokens stored as GitHub secrets, modifying their workflows to send those tokens to external servers. While the attackers successfully exfiltrated some tokens, they do not appear to have used them on PyPI."

In August, attackers exploited a flawed GitHub Actions workflow used by the Nx repository (a very popular build system and monorepo management tool) as part of another supply chain attack ([dubbed s1ngularity)](https://www.bleepingcomputer.com/news/security/ai-powered-malware-hit-2-180-github-accounts-in-s1ngularity-attack/), which affected 2,180 accounts and 7,200 repositories.

One month earlier, the Python Software Foundation also warned users that a phishing campaign [was attempting to steal their credentials](https://www.bleepingcomputer.com/news/security/hackers-target-python-devs-in-phishing-attacks-using-fake-pypi-site/#comments) using a fake Python Package Index (PyPI) website.