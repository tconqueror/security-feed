# PyPI urges users to reset credentials after new phishing attacks

![Python](https://www.bleepstatic.com/content/hl-images/2025/09/24/Python.jpg)

The Python Software Foundation has warned victims of a new wave of phishing attacks using a fake Python Package Index (PyPI) website to reset credentials.

Accessible at pypi.org, PyPI is the default source for Python's package management tools, hosting hundreds of thousands of packages and providing developers with a centralized platform to distribute third-party software libraries.

Python Software Foundation developer Seth Larson said the phishing emails request targets to "verify their email address" for "account maintenance and security procedures," threatening them with account suspensions and redirecting to a phishing landing page at pypi-mirror\[.\]org.

"If you have already clicked on the link and provided your credentials, we recommend changing your password on PyPI immediately," [Larson said](https://blog.pypi.org/posts/2025-09-23-plenty-of-phish-in-the-sea/). "Inspect your account's Security History for anything unexpected. Report suspicious activity, such as potential phishing campaigns against PyPI, to security@pypi.org."

The threat actors aim to steal the victims' credentials, which will likely be used in subsequent attacks to compromise Python packages they've published on PyPI with malware or to publish new malicious packages.

These attacks are part of a phishing campaign that also used the pypj\[.\]org domain [in July](https://www.bleepingcomputer.com/news/security/hackers-target-python-devs-in-phishing-attacks-using-fake-pypi-site/) to trick potential victims into logging in to a fake PyPI site.

![Fake pypj[.]org site](https://www.bleepstatic.com/images/news/u/1109292/2025/Fake-pypj_org-website.png)

_Fake pypj\[.\]org site (BleepingComputer)_

Larson advised PyPI package maintainers to never click on links in emails and to use password managers that auto-fill credentials based on domain names.

To further ensure their accounts are protected against hacking attempts, they should also use phishing-resistant two-factor authentication (2FA) methods, such as hardware keys, and share suspicious emails with others before taking action.

Users can also help take down these phishing campaigns by reporting domains as malicious and contacting registrars to have the domains removed, to block attackers' attempts to trick other PyPI users.

Last week, the Python Software Foundation team also invalidated all PyPI tokens stolen in [the GhostAction supply chain attack](https://www.bleepingcomputer.com/news/security/hackers-steal-3-325-secrets-in-ghostaction-github-supply-chain-attack/) in early September, confirming that the threat actors had not abused them to publish malware.

In March 2024, PyPI also [temporarily suspended user registration](https://www.bleepingcomputer.com/news/security/pypi-suspends-new-user-registration-to-block-malware-campaign/) and new project creation after threat actors published hundreds of malicious packages disguised as legitimate ones.