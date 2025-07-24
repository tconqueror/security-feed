# Hackers breach Toptal GitHub account, publish malicious npm packages

![NPM](https://www.bleepstatic.com/content/hl-images/2025/05/08/npm.jpg)

Hackers compromised Toptal's GitHub organization account and used their access to publish ten malicious packages on the Node Package Manager (NPM) index.

The packages included data-stealing code that collected GitHub authentication tokens and then wiped the victims' systems.

Toptal is a freelance talent marketplace that connects companies with software developers, designers, and finance experts. The company also maintains internal developer tools and design systems, most notably Picasso, which they make available through GitHub and NPM.

Attackers hijacked Toptal's GitHub organization on July 20, and almost immediately made public all 73 of the repositories available, exposing private projects and source code.

![Tweet](https://www.bleepstatic.com/images/news/u/1220909/2025/July/tweet(2).png)

In the days that followed, the attackers modified the source code of Picasso on GitHub to include malware and published 10 malicious packages on NPM as Toptal, making them appear as legitimate updates.

The malicious packages and modified versions are:

* @toptal/picasso-tailwind (v3.1.0)
* @toptal/picasso-charts (v59.1.4)
* @toptal/picasso-shared (v15.1.0)
* @toptal/picasso-provider (v5.1.1)
* @toptal/picasso-select (v4.2.2)
* @toptal/picasso-quote (v2.1.7)
* @toptal/picasso-forms (v73.3.2)
* @xene/core (v0.4.1)
* @toptal/picasso-utils (v3.2.0)
* @toptal/picasso-typography (v4.1.4)

The malicious packages were downloaded roughly 5,000 times before being detected, likely infecting developers with malware.

The hackers injected the malicious code into 'package.json' files to add two functions: steal data ('preinstall' script) and wipe hosts ('postinstall' script).

The first extracts the victim's CLI authentication token and sends it to an attacker-controlled webhook URL, granting them unauthorized access to the target's GitHub account.

After exfiltrating the data, the second script attempts to delete the entire filesystem with 'sudo rm -rf --no-preserve-root /' on Linux systems, or recursively and silently delete files on Windows.

According to code security platform [Socket](https://socket.dev/blog/toptal-s-github-organization-hijacked-10-malicious-packages-published), Toptal deprecated the malicious packages on July 23 and reverted to safe versions, but issued no public statement to alert users who had downloaded the malicious releases to the risks.

Although the initial compromise method remains unknown, Socket lists multiple possibilities ranging from insider threats to phishing attacks targeting Toptal developers.

BleepingComputer has contacted Toptal for a statement, but we are still waiting for their response.

If you have installed any of the malicious packages, you are advised to revert to a previous stable version as soon as possible.