# Magento supply chain attack compromises hundreds of e-stores

![Magecart](https://www.bleepstatic.com/content/hl-images/2023/10/09/magecart.jpg)

A supply chain attack involving 21 backdoored Magento extensions has compromised between 500 and 1,000 e-commerce stores, including one belonging to a $40 billion multinational.

Sansec researchers who discovered the attack report that some extensions were backdoored as far back as 2019, but the malicious code was only activated in April 2025.

"Multiple vendors were hacked in a coordinated supply chain attack, Sansec found 21 applications with the same backdoor," [explains Sansec](http://sansec.io/research/license-backdoor).

"Curiously, the malware was injected 6 years ago, but came to life this week as attackers took full control of ecommerce servers."

Sansec says the compromised extensions are from vendors Tigren, Meetanshi, and MGS:

* Tigren Ajaxsuite
* Tigren Ajaxcart
* Tigren Ajaxlogin
* Tigren Ajaxcompare
* Tigren Ajaxwishlist
* Tigren MultiCOD
* Meetanshi ImageClean
* Meetanshi CookieNotice
* Meetanshi Flatshipping
* Meetanshi FacebookChat
* Meetanshi CurrencySwitcher
* Meetanshi DeferJS
* MGS Lookbook
* MGS StoreLocator
* MGS Brand
* MGS GDPR
* MGS Portfolio
* MGS Popup
* MGS DeliveryTime
* MGS ProductTabs
* MGS Blog

Sansec has also found a compromised version of the Weltpixel GoogleTagManager extension but couldn't confirm if the point of compromise was at the vendor or the website.

In all observed cases, the extensions include a PHP backdoor added to a license check file (License.php or LicenseApi.php) used by the extension.

![Checking HTTP request for valid authentication against hardcoded keys](https://www.bleepstatic.com/images/news/security/m/magento/extension-backdoor/admin-check.png)

**Checking HTTP request for valid authentication against hardcoded keys**  
_Source: BleepingComputer_

If the check is successful, the backdoor gives access to other admin functions in the file, including one that allows a remote user to upload a new license and save it as a file.

![Running an admin function specified in the HTTP request](https://www.bleepstatic.com/images/news/security/m/magento/extension-backdoor/check-license.png)

**Running an admin function specified in the HTTP request**  
_Source: BleepingComputer_

This file is then included using the "include\_once()" PHP function, which loads the file and automatically executes any code within the uploaded license file.

**Function that executes code in the uploaded file**  
_Source: BleepingComputer_

Past versions of the backdoor didn't require authentication, but newer ones use a hardcoded key.

Sansec told BleepingComputer that this backdoor was used to upload a webshell to one of their customer's sites.

Given the ability to upload and run any PHP code, the potential repercussions of the attack include data theft, skimmer injection, arbitrary admin account creation, and more.

Sansec contacted the three vendors, warning them of the discovered backdoor. The cybersecurity firm says MGS didn't respond, Tigren denied a breach and continues to distribute backdoored extensions, and Meetanshi admitted to a server breach but not an extension compromise.

BleepingComputer independently confirmed that this backdoor is present in the MGS StoreLocator extension, which is free to download from their site. We did not confirm if the backdoor is present in the other extensions reported by Sansec.

Users of the mentioned extensions are recommended to perform complete server scans for the indicators of compromise Sansec shared in its report and, if possible, restore the site from a known-clean backup.

Sansec commented on the peculiarity of the backdoor laying dormant for six years and activating only now and promised to provide additional insight from their ongoing investigation.

BleepingComputer contacted the three vendors, but has not received a response at this time.