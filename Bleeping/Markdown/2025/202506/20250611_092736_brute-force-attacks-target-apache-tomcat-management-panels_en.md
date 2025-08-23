# Brute-force attacks target Apache Tomcat management panels

![Apache Tomcat](https://www.bleepstatic.com/content/hl-images/2025/06/11/Apache-Tomcat.jpeg)

A coordinated campaign of brute-force attacks using hundreds of unique IP addresses targets Apache Tomcat Manager interfaces exposed online.

Tomcat is a popular open-source web server widely used by large enterprises and SaaS providers, while Tomcat Manager is a web-based administration tool that comes bundled with the Tomcat server and helps admins manage deployed web apps via a graphical interface.

Tomcat Manager is configured by default to only allow access from localhost (127.0.0.1), with no pre-configured credentials and remote access blocked. However, when exposed online, the web app can be targeted by attackers, as cybersecurity company GreyNoise observed recently.

Starting June 5th, GreyNoise analysts discovered two coordinated campaigns targeting Apache Tomcat Manager interfaces and trying to gain access to Tomcat services over the Internet.

The first [used nearly 300 unique IP addresses](https://viz.greynoise.io/tags/tomcat-manager-login-attempt?days=1), most tagged as malicious, which were attempting to log into exposed online, and the second [employed 250 malicious IPs](https://viz.greynoise.io/tags/tomcat-manager-brute-force-attempt?days=1) to target Tomcat Manager web apps in brute force attacks, where threat actors use automated tools to test thousands or even millions of possible credentials.

"Roughly 400 unique IPs were involved in the activity observed across both tags during this period of elevated activity. Most of the activity originating from these IPs exhibited a narrow focus on Tomcat services. A significant portion of this activity originated from infrastructure hosted by DigitalOcean (ASN 14061)," [GreyNoise said](https://www.greynoise.io/blog/coordinated-brute-force-activity-targeting-apache-tomcat-manager).

"While not tied to a specific vulnerability, this behavior highlights ongoing interest in exposed Tomcat services. Broad, opportunistic activity like this often serves as an early warning of future exploitation."

![Tomcat brute force attacks](https://www.bleepstatic.com/images/news/u/1109292/2025/Tomcat_brute_force_attacks.png)

_Tomcat brute force attacks (GreyNoise)_

The cybersecurity company advised organizations with Tomcat Manager interfaces exposed online to ensure they have strong authentication and access restrictions.

Users should check security logs for any suspicious login activity and promptly block any IP addresses that could be behind a breach attempt.

While no specific security vulnerability was exploited in these attacks, Apache released security fixes in March to [patch a remote code execution (RCE) vulnerability](https://www.bleepingcomputer.com/news/security/critical-rce-flaw-in-apache-tomcat-actively-exploited-in-attacks/) in Apache Tomcat (CVE-2025-24813) actively exploited in the wild to take over vulnerable servers with a simple PUT request.

The threat actors behind the attacks reportedly used proof-of-concept (PoC) exploits released on GitHub just 30 hours after the flaw was disclosed and patched.

In December, Apache also [fixed another Tomcat RCE flaw](https://www.bleepingcomputer.com/news/security/apache-fixes-remote-code-execution-bypass-in-tomcat-web-server/) (CVE-2024-56337) that could be used to bypass the patch for a second critical RCE vulnerability (CVE-2024-50379) mitigated days earlier.