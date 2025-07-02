# Forminator plugin flaw exposes WordPress sites to takeover attacks

![Forminator plugin flaw exposes WordPress sites to takeover attacks](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

The Forminator plugin for WordPress is vulnerable to an unauthenticated arbitrary file deletion flaw that could enable full site takeover attacks.

The security issue is tracked as CVE-2025-6463 and has a high-severity impact (CVSS 8.8 score). It impacts all versions of Forminator up to 1.44.2.

Forminator Forms is a plugin developed by WPMU DEV. It offers a flexible, visual drag‑and‑drop builder to help users create and embed a wide range of form-based content on WordPress sites.

According to statistics from [WordPress.org](https://wordpress.org/plugins/forminator/), the plugin is currently active on more than 600,000 websites.

The vulnerability stems from insufficient validation and sanitization of form field input and unsafe file deletion logic in the plugin’s backend code.

When a user submits a form, the ‘save_entry_fields()’ function saves all field values, including file paths, without checking if those fields are supposed to handle files.

An attacker could exploit this behavior to insert a crafted file array into any field, including text fields, mimicking an uploaded file with a custom path that points to a critical file, such as ‘/var/www/html/wp-config.php.’

When the admin deletes this or when the plugin auto-deletes old submissions (as configured), Forminator wipes the core WordPress file, forcing the website to enter a “setup” stage where it’s vulnerable to takeover.

“Deleting wp-config.php forces the site into a setup state, allowing an attacker to initiate a site takeover by connecting it to a database under their control,” [explains Wordfence](https://www.wordfence.com/blog/2025/07/600000-wordpress-sites-affected-by-arbitrary-file-deletion-vulnerability-in-forminator-wordpress-plugin/).

## Discovery and patching

CVE-2025-6463 was discovered by security researcher ‘Phat RiO – BlueRock’ who reported it to Wordfence on June 20 and received a bug bounty of $8,100.

Following internal validation of the exploit, Wordfence contacted WPMU DEV on June 23, who acknowledged the report and started working on a fix.

On June 30, the vendor released Forminator version 1.44.3, which adds a field type check and a file path validation that ensures deletions are limited to the WordPress uploads directory.

Since the release of the patch, there have been 200,000 downloads but it is unclear how many are currently vulnerable to CVE-2025-6463 exploitation.

If you use Forminator for your website, it is recommended to update it to the latest version or deactivate the plugin until you can move to a safe version.

At this time, there are no reports about active exploitation of CVE-2025-6463, but the public disclosure of the technical details combined with the ease of exploitation could lead to threat actors moving quickly to exploring its potential in attacks.