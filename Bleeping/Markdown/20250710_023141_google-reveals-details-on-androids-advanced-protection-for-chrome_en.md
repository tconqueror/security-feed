# Google reveals details on Android’s Advanced Protection for Chrome

![Google reveals details on Android’s Advanced Protection for Chrome](https://www.bleepstatic.com/content/hl-images/2023/11/28/Google_Chrome.jpg)

Google is sharing more information on how Chrome operates when Android mobile users enable Advanced Protection, highlighting strong security improvements.

The tech giant [recently extended](https://www.bleepingcomputer.com/news/security/android-16-expands-advanced-protection-with-device-level-security/) its Advanced Protection Program to the device level with the release of Android 16, aimed at offering a robust, holistic security posture for high-risk individuals likely to be targeted by sophisticated spyware attacks.

Starting Android 16, Advanced Protection can be activated from the settings, strengthening security measures across the board, including on Google apps such as Chrome, Messages, and Phone.

For Chrome specifically, these measures became available with version 137 for Android, but Google hadn’t shared details about their added value and how they worked.

In a [new blog post](https://security.googleblog.com/2025/07/advancing-protection-in-chrome-on.html), the Chrome Security Team explains that activating Advanced Protection triggers the following in Chrome:

* **Enforcing Secure Connections** – forces Chrome to attempt HTTPS for all sites (public and private) and warns users before connecting to any site over the insecure HTTP; this protects against attackers who may intercept or alter data over unencrypted connections.
* **Full Site Isolation** – isolates each website into its own process, preventing one site from accessing data from another, even in the event of a renderer exploit. On Android with more than 4GB of RAM the feature is active by default, otherwise it can be enabled under Advanced Protection
* **JavaScript Optimization and Security** – Advanced Protection disables high-level JavaScript optimizing compilers in Chrome’s V8 engine to reduce the browser’s attack surface. These optimizers improve performance but have historically been linked to many exploited bugs. It is estimated that disabling them could have mitigated roughly half of such cases, with no significant performance hit on most sites.

HTTPS and JS security features were already available as options under Chrome’s Privacy and Security menu since version 133, so users can independently enable them even without toggling Advanced Protection to on.

It is also noted that site isolation still triggers even without Advanced Protection when users attempt to log in or submit a form on a site, which are considered high-risk scenarios by default.

To enable Advanced Protection on Android, go to Settings > Security & Privacy > Advanced Protection > toggle switch to the “on” position.

![Activating Advanced Protection on Android 16](https://www.bleepstatic.com/images/news/u/1220909/2025/July/setting.jpg)

**Activating Advanced Protection on Android 16**  
_Source: BleepingComputer_

Google also recommends that high-risk individuals join the Advanced Protection Program with a Google account for stronger multi-factor authentication and automatic enforcement of security settings across devices.