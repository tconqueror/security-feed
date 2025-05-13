# Android 16 expands 'Advanced Protection' with device-level security

![Android 16 enhances 'Advanced Protection' with device-level security](https://www.bleepstatic.com/content/hl-images/2024/05/15/android-holding-shield.jpg)

Google is announcing improvements for the Advanced Protection feature in Android 16 that strengthen defenses against sophisticated spyware attacks.

The Android platform has been a constant target for [spyware](https://www.bleepingcomputer.com/news/security/new-android-spyware-found-on-phone-seized-by-russian-fsb/) campaigns and sophisticated attacks using [digital forensics platforms](https://www.bleepingcomputer.com/news/security/google-fixes-android-zero-days-exploited-in-targeted-attacks/) that often rely on zero-day vulnerabilities to infect devices with minimal or no user interaction.

Google already offers the '[Advanced Protection Program](https://landing.google.com/intl/en%5Fin/advancedprotection/)' for high-risk individuals (e.g. journalists, elected official, public figures) but its current focus is on protecting the Google Account.

With Android 16, the company expands security hardening to the mobile device itself, beyond certain app-level settings.

This device-level security layer bundles Androids' strongest system-level security features and prevents disabling, maliciously or by accident, individual security features part of the Advanced Protection umbrella.

Google's Advanced Protection on Android is similar to [Apple’s Lockdown Mode](https://www.bleepingcomputer.com/news/apple/apple-s-new-lockdown-mode-defends-against-government-spyware/) and will become available on the latest version of the mobile operating system showcased today as part of Google's "The Android Show: I/O Edition."

## How Advanced Protection works

Advanced Protection is designed as an easy-to-activate device-level setting that consolidates Android’s strongest security features into a single system.

![Advanced Protection settings](https://www.bleepstatic.com/images/news/u/1220909/2025/May/1_%20Advanced%20Protection%20settings.jpg)

**Advanced Protection settings**  
_Source: Google_

Specifically, it activates verified boot and runtime integrity checks, strong sandboxing, USB port lockdown, app isolation, [automatic device reboots](https://www.bleepingcomputer.com/news/security/google-adds-android-auto-reboot-to-block-forensic-data-extractions/) when idle for 72 hours, and Google Play Protect with enhanced app scanning.

It also eliminates the ability to turn off or weaken core security settings and enforces secure settings across Google apps (Chrome, Messages, Phone) as well as third-party apps that opt into the integration.

Finally, it introduces new protections like intrusion logging and blocking auto-reconnects to insecure networks.

Intrusion logging is a new system that logs device events in a privacy-preserving, tamper-proof, cloud-stored log, which is useful for investigating compromises. The data will only be accessible by the user and protected by end-to-end encryption.

Auto-reconnection blocking concerns weak Wi-Fi networks that don’t require passwords or use WEP protection, mitigating the risk of passive surveillance or [captive portal attacks](https://www.bleepingcomputer.com/news/security/australian-charged-for-evil-twin-wifi-attack-on-plane/).

All of the security features controlled through Advanced Protection are listed in the table below. It is important to note that availability for some of them depends on the manufacturer and the type of device and will present later this year.

![Overview of all features encompassed in Advanced Protection](https://www.bleepstatic.com/images/news/u/1220909/2025/May/3_%20Advanced%20Protection%20table.jpg)

**Overview of all features encompassed in Advanced Protection**  
_Source: Google_

## More security features to land with Android 16

Apart from Advanced Protection, Android 16 is set to bring several data security and privacy enhancements through a new set of features poised to protect users from phone scammers and malware apps.

One of them is “in-call scam protections” that will block risky actions during calls from unknown numbers, like sideloading APKs, granting accessibility permissions, or disabling Play Protect.

**In-call scam protection in action**  
_Source: Google_

Another feature highlighted by Google today is the Key Verifier mechanism in the Messages app. The improvement is designed to fight tex-based fraud and impersonation by verifying the identity of the other party with public encryption keys associated with contacts.

The role of the public-key cryptography in Google Messages is to provide end-to-end encrypted messaging.

"By verifying contact keys in your Google Contacts app (through a QR code scanning or number comparison), you can have an extra layer of assurance that the person on the other end is genuine and that your conversation is private with them," Google says.

The Key Verifier feature can also protect against SIM-swap attacks where attackers pose as someone from the victim’s contacts.

**Key Verifier's QR code prompt**  
_Source: Google_

Android 16 also comes with improvements for [Scam Detection](https://www.bleepingcomputer.com/news/security/google-expands-android-ai-scam-detection-to-more-pixel-devices/) for the Messages and Phone apps by integrating artificial intelligence to identify scams related to various topics, among them toll road, billing fee, crypto, financial impersonation, gift card and prizes, and technical support.

Google also improved [Theft Protection](https://www.bleepingcomputer.com/news/google/android-to-add-new-anti-theft-and-data-protection-features/) features by turning Find My Device into Find Hub, a feature that also covers lost items and works with Bluetooth tags and with the partnership of multiple airlines.

The company announced that later this year Find Hub will integrate satellite connectivity and allow connections with friends and family even in places without a cellular signal.

The new features Google announced today for [Android 16 are available here](http://www.android.com/new-features-on-android/io-2025/).