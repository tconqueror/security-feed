# Post SMTP plugin flaw exposes 200K WordPress sites to hijacking attacks

![Post SMTP plugin flaw exposes 200K WordPress sites to hijacking attacks](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

More than 200,000 WordPress websites are using a vulnerable version of the Post SMTP plugin that allows hackers to take control of the administrator account.

Post SMTP is a popular email delivery plugin for WordPress that counts more than 400,000 active installations. It’s marketed as a replacement of the default ‘_wp_mail()_’ function that is more reliable and feature-rich.

On May 23, a security researcher reported the vulnerability to WordPress security firm PatchStack. The flaw is now identified as CVE-2025-24000 and received a medium severity score of 8.8.

The security issue affects all versions of Post SMTP up to 3.2.0 and is due to a broken access control mechanism in the plugin’s REST API endpoints, which only verified if a user was logged in, without checking their permission level.

This means that low-privileged users, such as Subscribers, could access email logs containing full email content.

On vulnerable sites, a subscriber could initiate a password reset for an Administrator account, intercept the reset email via the logs, and gain control of the account.

![The vulnerable code](https://www.bleepstatic.com/images/news/u/1220909/2025/July/vuln.jpg)

**The vulnerable code**  
_Source: PatchStack_

The plugin’s developer, Saad Iqbal, was informed about the flaw and responded with a fix for Patchstack to review on May 26.

The solution was to incorporate additional privilege checks in the ‘get_logs_permission’ function that would validate a user’s permissions before giving access to sensitive API calls.

The fix was incorporated into Post SMTP version 3.3.0, which was published on June 11.

Download statistics on [WordPress.org](https://wordpress.org/plugins/post-smtp/advanced/) show that less than half of the plugin's user base (48.5%) has updated to version 3.3\. This means that more than 200,000 websites are vulnerable to CVE-2025-24000.

A notable 24.2%, corresponding to 96,800 sites, still run Post SMTP versions from the 2.x branch, which is vulnerable to additional security flaws, leaving them open to attacks.