# New Android Pixnapping attack steals MFA codes pixel-by-pixel

![New Android Pixnapping attack steals MFA codes pixel-by-pixel](https://www.bleepstatic.com/content/hl-images/2025/03/04/Android_cracks.jpg)

A new side-channel attack called Pixnapping enables a malicious Android app with no permissions to extract sensitive data by stealing pixels displayed by applications or websites, and reconstructing them to derive the content.

The content may include sensitive private data like chat messages from secure communication apps like Signal, emails on Gmail, or two-factor authentication codes from Google Authenticator.

The attack, devised and demonstrated by a team of seven American university researchers, works on fully patched modern Android devices and can steal 2FA codes in less than 30 seconds.

Google attempted to fix the problem ([CVE-2025-48561](https://nvd.nist.gov/vuln/detail/CVE-2025-48561)) in the [September Android update](https://www.bleepingcomputer.com/news/security/google-fixes-actively-exploited-android-flaws-in-september-update/). However, researchers were able to bypass the mitigation and an effective solution is expected in the December 2025 Android security update.

## How Pixnapping works

The attack starts with a malicious app abusing Android’s intents system to launch the target app or webpage, so its window is submitted to the system’s composition process (SurfaceFlinger), which is responsible for combining multiple windows when they are visible at the same time.

In the next step, the malicious app maps the target pixels (for instance, the pixels forming the digit of a 2FA code) and determines through multiple graphical operations if they are white or non-white.

Isolating each pixel is possible by opening what the researchers call a 'masking activity', which sits in the foreground, hiding the target app. Then the attacker makes the cover window "all opaque white pixels except for the pixel at the attacker-chosen location which is set to be transparent."

During the Pixnapping attack, the isolated pixels are enlarged, leveraging a "quirk" in the way SurfaceFlinger implements blur that produces a stretch-like effect.

![Blurred region stretched to fill a larger patch](https://www.bleepstatic.com/images/news/u/1220909/2025/October/blur.jpg)

**Blurred 1x1 sub-region stretched into a larger colored patch**  
_Source: pixnapping.com_

After recovering all the victim pixels, an OCR-style technique is used to differentiate each character or digit.

"Conceptually, it is as if the malicious app was taking a screenshot of screen contents it should not have access to," the researchers [explain](https://www.pixnapping.com/).

To steal the data, the researchers used the [GPU.zip side-channel attack](https://www.bleepingcomputer.com/news/security/modern-gpus-vulnerable-to-new-gpuzip-side-channel-attack/), which exploits graphical data compression in modern GPUs to leak visual information.

Although the data leakage rate is relatively low, ranging from 0.6 to 2.1 pixels per second, optimizations demonstrated by the researchers show that 2FA codes or other sensitive data can be exfiltrated in less than 30 seconds.

## Impact on Android

The researchers demonstrated Pixnapping on Google Pixel 6, 7, 8, and 9 devices, as well as Samsung Galaxy S25, running Android versions 13 through 16, and all of them were vulnerable to the new side-channel attack.

Since the underlying mechanisms that make Pixnapping effective are found on older Android versions, likely, most Android devices and older OS versions are also vulnerable.

The researchers analyzed nearly 100,000 Play Store apps, finding hundreds of thousands of invocable actions through Android intents, indicating that the attack is broadly applicable.

The technical paper presents the following examples of data theft:

* **Google Maps:** Timeline entries occupy \~54,264–60,060 pixels; unoptimized recovery of an entry takes \~20–27 hours across devices.
* **Venmo:** activities (profile, balance, transactions, statements) are openable via implicit intents; account-balance regions are \~7,473–11,352 pixels and leak in \~3–5 hours unoptimized.
* **Google Messages (SMS):** explicit/implicit intents can open conversations. Target regions are \~35,500–44,574 pixels; unoptimized recovery takes \~11–20 hours. Attack distinguishes sent vs received by testing blue vs non-blue or gray vs non-gray pixels.
* **Signal (private messages):** implicit intents can open conversations. Target regions are \~95,760–100,320 pixels; unoptimized recovery takes \~25–42 hours, and the attack worked even with [Signal’s Screen Security](https://www.bleepingcomputer.com/news/security/signal-now-blocks-microsoft-recall-screenshots-on-windows-11/) enabled.

Both Google and Samsung have committed to fixing the flaws before the end of the year, but no GPU chip vendor has announced patching plans for the GPU.zip side-channel attack.

While the original exploit method was mitigated in September, Google received an updated attack that demonstrated a bypass for the original fix. Google has developed a more thorough patch to be released with the Android security updates for December.

Google says that leveraging this data leak technique requires specific data about the targeted device, which, as the researchers noted, leads to a low success rate. Current verifications found no malicious apps on Google Play leveraging the Pixnapping vulnerability.