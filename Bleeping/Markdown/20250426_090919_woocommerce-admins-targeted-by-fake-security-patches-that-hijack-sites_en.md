# WooCommerce admins targeted by fake security patches that hijack sites

![WordPress](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

A large-scale phishing campaign targets WooCommerce users with a fake security alert urging them to download a "critical patch" that adds a Wordpress backdoor to the site.

Recipients that take the bait and download the update are actually installing a malicious plugin that creates a hidden admin account on their website, downloads web shell payloads, and maintains persistent access.

The campaign, which was [discovered by Patchstack](https://patchstack.com/articles/fake-security-vulnerability-phishing-campaign-targets-woocommerce-users/) researchers, appears to be a continuation of a similar operation in [late 2023](https://patchstack.com/articles/fake-cve-phishing-campaign-tricks-wordpress-users-to-install-malware/) that targeted WordPress users with a fake patch for a made-up vulnerability.

Patchstack says both campaigns used an unusual set of web shells, identical payload hiding methods, and similar email content.

## Fake security alert

The emails targeting WordPress admins spoof the popular WooCommerce e-commerce plugin, using the address 'help@security-woocommerce\[.\]com.'

Recipients are informed that their websites were targeted by hackers attempting to exploit an 'unauthenticated administrative access' vulnerability.

To protect their online stores and data, recipients are advised to download a patch using the embedded button, with step-by-step instructions on how to install it included in the message.

"We are contacting you regarding a critical security vulnerability found in WooCommerce platform on April 14, 2025," reads the phishing emails.

"Warning: Our latest security scan, carried out on April 21, 2025, has confirmed that this critical vulnerability directly impacts your website."

"We strongly advise you to take urgent measures to secure your store and protect your data," continues the email to add a sense of urgency.

![Phishing email](https://www.bleepstatic.com/images/news/u/1220909/2025/April/email(1).jpg)

**Phishing email targeting WooCommerce users**  
_Source: Patchstack_

Clicking on the 'Download Patch' button takes victims to a website that spoofs WooCommerce, using a very deceptive 'woocommėrce\[.\]com' domain that is only one character different from the official, woocommerce.com.

The malicious domain employs a homograph attack technique where the Lithuanian character "ė" (U+0117) is used instead of an "e," making it easy to miss.

![Malicious website mimicking the WooCommerce platform](https://www.bleepstatic.com/images/news/u/1220909/2025/April/site(1).jpg)

**Malicious website mimicking the WooCommerce platform**  
_Source: Patchstack_

## Post-infection activity

After the victim installs the fake security fix ("authbypass-update-31297-id.zip"), it creates a randomly named cronjob that runs every minute, attempting to create a new admin-level user.

Next, the plugin registers the infected site via an HTTP GET request to 'woocommerce-services\[.\]com/wpapi,' and fetches a second-stage obfuscated payload.

This, in turn, installs multiple PHP-based web shells under 'wp-content/uploads/,' including P.A.S.-Form, p0wny, and WSO.

Patchstack comments that these web shells allow full control of the site and could be used for ad injection, redirecting users to malicious destinations, enlisting the server to DDoS botnets, stealing payment card information, or executing ransomware to encrypt the site and extort the owner.

To evade detection, the plugin removes itself from the visible plugin list and also hides the malicious administrator account it created.

Patchstack advises website owners to scrutinize admin accounts for 8-character random names, unusual cronjobs, a folder named 'authbypass-update,' and outgoing requests to woocommerce-services\[.\]com, woocommerce-api\[.\]com, or woocommerce-help\[.\]com.

However, the security firm notes that threat actors typically change all these indicators once they're exposed via public research, so make sure you don't rely on narrow-scope scans.