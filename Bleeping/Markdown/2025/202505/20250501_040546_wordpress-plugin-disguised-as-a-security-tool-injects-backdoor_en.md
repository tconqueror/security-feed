# WordPress plugin disguised as a security tool injects backdoor

![Wordpress](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

A new malware campaign targeting WordPress sites employs a malicious plugin disguised as a security tool to trick users into installing and trusting it.

According to Wordfence researchers, the malware provides attackers with persistent access, remote code execution, and JavaScript injection. At the same time, it remains hidden from the plugin dashboard to evade detection.

Wordfence first discovered the malware during a site cleanup in late January 2025, where it found a modified 'wp-cron.php' file, which creates and programmatically activates a malicious plugin named 'WP-antymalwary-bot.php.'

Other plugin names used in the campaign include:

* addons.php
* wpconsole.php
* wp-performance-booster.php
* scr.php

If the plugin is deleted, wp-cron.php re-creates and reactivates it automatically on the next site visit.

Lacking server logs to help identify the exact infection chain, Wordfence hypothesizes the infection occurs via a compromised hosting account or FTP credentials.

Not much is known about the perpetrators, though the researchers noted that the command and control (C2) server is located in Cyprus, and there are traits similar to a [June 2024 supply chain attack](https://www.bleepingcomputer.com/news/security/plugins-on-wordpressorg-backdoored-in-supply-chain-attack/).

Once active on the server, the plugin performs a self-status check and then gives the attacker administrator access.

"The plugin provides immediate administrator access to threat actors via the emergency\_login\_all\_admins function," [explains Wordfence in its writeup](https://www.wordfence.com/blog/2025/04/interesting-wordpress-malware-disguised-as-legitimate-anti-malware-plugin/).

"This function utilizes the emergency\_login GET parameter in order to allow attackers to obtain administrator access to the dashboard."

"If the correct cleartext password is provided, the function fetches all administrator user records from the database, picks the first one, and logs the attacker in as that user."

Next, the plugin registers an unauthenticated custom REST API route that allows the insertion of arbitrary PHP code into all active theme header.php files, clearing of plugin caches, and other commands processed via a POST parameter.

An updated version of the malware can also inject base64-decoded JavaScript into the site's <head> section, likely for serving visitors ads, spam, or redirecting them to unsafe sites.

Apart from file-based indicators like the listed plugins, website owners should scrutinize their 'wp-cron.php' and 'header.php' files for unexpected additions or modifications.

Access logs containing 'emergency\_login,' 'check\_plugin,' 'urlchange,' and 'key' should also serve as red flags, warranting further investigation.