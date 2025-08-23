# Premium WordPress 'Motors' theme vulnerable to admin takeover attacks

![Car](https://www.bleepstatic.com/content/hl-images/2025/05/20/motors.jpg)

A critical privilege escalation vulnerability has been discovered in the premium WordPress theme Motors, which allows unauthenticated attackers to hijack administrator accounts and take complete control of websites.

Developed by StylemixThemes, Motors is one of the top-selling automotive themes for the WordPress platform. It is very popular among automotive businesses such as car dealerships, rental services, and used vehicle listing platforms.

It has over 22,300 sales on the [Envato market](https://themeforest.net/item/motors-automotive-cars-vehicle-boat-dealership-classifieds-wordpress-theme/13987211), with hundreds of user reviews and thousands of comments, indicating a highly active community around it.

The flaw, tracked as CVE-2025-4322, was publicly disclosed by Wordfence earlier today and added to the National Vulnerability Database ([NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-4322)).

It is a privilege escalation problem impacting all versions of the Motors theme up to and including 5.6.67.

"This (vulnerability) is due to the theme not properly validating a user's identity prior to updating their password," [explains Wordfence](https://www.wordfence.com/threat-intel/vulnerabilities/wordpress-themes/motors/motors-5667-unauthenticated-privilege-escalation-via-password-updateaccount-takeover).

"This makes it possible for unauthenticated attackers to change arbitrary user passwords, including those of administrators, and leverage that to gain access to their account."

By gaining admin-level access, attackers could implant malware, exfiltrate database contents and sensitive member details, or redirect visitors to dangerous sites.

[StylemixThemes](https://stylemixthemes.com/car-dealer-plugin/) released Motors version 5.6.68, which addresses CVE-2025-4322 on May 14, 2025.

WordPress themes are central to websites and cannot be temporarily disabled or easily replaced, so upgrading to the latest version as soon as possible is critical.

The vendor has a detailed [online guide](https://docs.stylemixthemes.com/motors-theme-documentation/getting-started/how-to-update-motors) on updating Motors via the WordPress panel, the Envato API, or manually via FTP.

It is important to back up your website before updating theme components to prevent potential data loss.

Although the issue doesn't impact a WordPress plugin active in millions of websites, it still constitutes a significant risk.

Given the price of $79 for a regular license and $2,000 for an extended license, Motors is more likely to be deployed in active sites or for those running businesses.