# Google rolls out Android theft protection feature updates

![Google Pixel](https://www.bleepstatic.com/content/hl-images/2026/01/29/Google_Pixel.jpg)

​Google has introduced stronger Android authentication safeguards and enhanced recovery tools to make smartphones more challenging targets for thieves.

These updated Android theft protection features build on the company's existing anti-theft defenses introduced in [October 2024](https://security.googleblog.com/2024/10/android-theft-protection.html) to protect users before, during, and after theft attempts.

"Phone theft is more than just losing a device; it's a form of financial fraud that can leave you suddenly vulnerable to personal data and financial theft," the [Android Security Team said](https://security.googleblog.com/2026/01/android-theft-protection-feature-updates.html) on Tuesday.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

As part of these changes, the company has added granular controls for the Failed Authentication Lock feature, which automatically locks device screens after excessive failed authentication attempts, now allowing users to enable or disable it using a dedicated settings toggle.

Google has expanded Identity Check, which requires biometric authentication for specific actions performed outside trusted locations, ensuring this safeguard now covers all features and apps that use Android Biometric Prompt, automatically protecting Google Password Manager and third-party banking apps.

The company is also trying to prevent accidental lockouts (e.g., curious children attempting to unlock the device) by ensuring that repeated incorrect guesses don't count toward the retry limit, and by making it harder for thieves to guess the PIN, pattern, or password by increasing the lockout time after failed attempts.

Remote Lock, a tool that allows users to lock lost or stolen devices from any web browser at android.com/lock, was also updated to add an optional security challenge to verify device ownership before initiating a lock.

![Failed Authentication Lock toggle](https://www.bleepstatic.com/images/news/u/1109292/2026/Android%20Theft%20Protection.png)

_Failed Authentication Lock toggle (Google)_

​For new Android devices activated in Brazil, Google will also enable two of its theft-protection features by default: Theft Detection Lock, which locks the device if it detects a "snatch-and-run" theft, and Remote Lock, which lets users lock their devices remotely.

The enhanced recovery tools are available on Android 10 or later devices, while the authentication safeguards require Android 16 or later.

"We've expanded our security to protect you against an even wider range of threats. These updates are now available for Android devices running Android 16+," the Android Security Team added. "We're also enhancing our recovery tools to make them even more helpful. This update is now available for Android devices running Android 10+."

In December, [Google also expanded support](https://www.bleepingcomputer.com/news/security/google-expands-android-scam-protection-feature-to-chase-cash-app-in-us/) for its Android in-call scam protection feature to multiple banks and financial applications (including Cash App, with 57 million users, and the JPMorganChase mobile banking app, with over 50 million downloads) in the United States.

In-call scam protection was [announced in May](https://www.bleepingcomputer.com/news/security/android-16-expands-advanced-protection-with-device-level-security/) and introduced in Android 16 to warn users of potential risks when they launch a financial app and share their screen during a call with numbers not in their contact list.