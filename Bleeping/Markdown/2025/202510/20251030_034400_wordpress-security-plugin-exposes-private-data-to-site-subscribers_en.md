# WordPress security plugin exposes private data to site subscribers

![WordPress](https://www.bleepstatic.com/content/hl-images/2023/12/07/back-2.jpg)

The Anti-Malware Security and Brute-Force Firewall plugin for WordPress, installed on over 100,000 sites, has a vulnerability that allows subscribers to read any file on the server, potentially exposing private information.

The plugin provides malware scanning and protection against brute-force attacks, exploitation of known plugin flaws, and against database injection attempts.

Identified as CVE-2025-11705, the vulnerability was [reported to Wordfence](http://www.wordfence.com/blog/2025/10/100000-wordpress-sites-affected-by-arbitrary-file-read-vulnerability-in-anti-malware-security-and-brute-force-firewall-wordpress-plugin/) by researcher Dmitrii Ignatyev and affects versions of the plugin 4.23.81 and earlier.

The issue stems from missing capability checks in the _GOTMLS\_ajax\_scan()_ function, which processes AJAX requests using a nonce that attackers could obtain.

This oversight allows a low-privileged user, who can invoke the function, to read arbitrary files on the server, including sensitive data such as the _wp-config.php_ configuration file that stores the database name and credentials.

With access to the database, an attacker can extract password hashes, users’ emails, posts, and other private data (and keys, salts for secure authentication).

Although the severity of the vulnerability is not considered critical, because authentication is needed for exploitation, many websites allow users to subscribe and increase their access to various sections of the site, such as comments.

Sites that offer any kind of membership or subscription, allowing users to create accounts, meet the requirement, and are vulnerable to attacks exploiting CVE-2025-11705.

Wordfence has reported the issue to the vendor, Eli, along with a validated proof-of-concept exploit, through the WordPress.org Security Team, on October 14.

On October 15, the developer released version 4.23.83 of the plugin that addresses CVE-2025-11705 by adding a proper user capability check via a new ‘GOTMLS\_kill\_invalid\_user()’ function.

According to [WordPress.org stats](https://wordpress.org/plugins/gotmls/advanced/), roughly 50,000 website administrators have downloaded the latest version since its release, indicating that an equal number of sites are running a vulnerable version of the plugin.

Currently, Wordfence has not detected signs of exploitation in the wild, but applying the patch is strongly recommended, as the public disclosure of the issue may draw the attackers' attention.