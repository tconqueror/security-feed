# Hackers target Python devs in phishing attacks using fake PyPI site

![Snake](https://www.bleepstatic.com/content/hl-images/2023/05/09/Snake.jpg)

The Python Software Foundation warned users this week that threat actors are trying to steal their credentials in phishing attacks using a fake Python Package Index (PyPI) website.

PyPI is a repository for Python packages, accessible at pypi.org, that offers a centralized platform for developers to distribute and install third-party software libraries. It hosts hundreds of thousands of packages and is the default source for Python's package management tools.

"PyPI has not been hacked, but users are being targeted by a phishing attack that attempts to trick them into logging in to a fake PyPI site. Over the past few days, users who have published projects on PyPI with their email in package metadata may have received an email titled '\[PyPI\] Email verification' from the email address noreply@pypj.org," the [PyPI admin Mike Fiedler cautioned](https://blog.pypi.org/posts/2025-07-28-pypi-phishing-attack/).

"This is not a security breach of PyPI itself, but rather a phishing attempt that exploits the trust users have in PyPI. The email instructs users to follow a link to verify their email address, which leads to a phishing site that looks like PyPI but is not the official site."

After opening the malicious website, the targeted users will be prompted to sign in, with the requests sent back to PyPI to trick the users into believing they have logged in to PyPI.

However, the attackers are instead harvesting their credentials, which will likely be used in future attacks to infect Python packages they've uploaded to PyPI with malware or to upload new malicious packages onto the platform.

![Fake pypj.org site](https://www.bleepstatic.com/images/news/u/1109292/2025/Fake-pypj_org-website.png)

_Fake pypj\[.\]org site (BleepingComputer)_

​The PyPI admins have also added a banner to PyPI's homepage, warning users of this phishing attack, and are now working to find a way to disrupt this ongoing campaign.

"We are also waiting for CDN providers and name registrars to respond to the trademark and abuse notifications we have sent them regarding the phishing site," Fiedler added.

Python developers and PyPI users who have received these phishing emails are advised not to click the embedded links and to delete the email immediately.

Those who have already entered their credentials on the pypj\[.\]org phishing site, should immediately change their PyPI password and inspect their accounts' Security History for suspicious or unexpected activity.

In February, the Python Software Foundation [introduced 'Project Archival](https://www.bleepingcomputer.com/news/security/pypi-adds-project-archiving-system-to-stop-malicious-updates/),' a new system designed to help PyPI publishers archive their projects, indicating to users that no updates are expected.

PyPI was also [forced to temporarily suspend user registration](https://www.bleepingcomputer.com/news/security/pypi-suspends-new-user-registration-to-block-malware-campaign/) and the creation of new projects in March 2024 due to a malware campaign linked to threat actors who uploaded hundreds of new malicious packages masquerading as legitimate projects.