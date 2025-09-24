# Unpatched flaw in OnePlus phones lets rogue apps text messages

![Unpatched flaw in OnePlus phones lets rogue apps text messages](https://www.bleepstatic.com/content/hl-images/2025/09/24/OnePlus.png)

A vulnerability in multiple versions of OxygenOS, the Android-based operating system from OnePlus, allows any installed app to access SMS data and metadata without requiring permission or user interaction.

OnePlus, a subsidiary of Oppo, is a Shenzhen-based consumer electronics maker known for developing high-end smartphones at competitive pricing. While other major Chinese brands like Huawei and Xiaomi aren’t available in the U.S., OnePlus devices are officially available in the country.

The flaw, tracked as CVE-2025-10184, and [discovered by Rapid7 researchers](https://www.rapid7.com/blog/post/cve-2025-10184-oneplus-oxygenos-telephony-provider-permission-bypass-not-fixed/), is currently unpatched and exploitable. The Chinese OEM failed to respond to Rapid7’s disclosures to this day, and the cybersecurity company published the technical details along with a proof-of-concept (PoC) exploit.

## Source of the problem

The problem arises from OnePlus changing the stock Android Telephony package to introduce additional exported content providers like PushMessageProvider, PushShopProvider, and ServiceNumberProvider.

The manifest for these providers does not declare a write permission for ‘READ\_SMS,’ leaving it open to any app by default, even those that don’t have SMS permissions.

![Extra providers OnePlus added on its Telephony package](https://www.bleepstatic.com/images/news/u/1220909/2025/September/providers.jpg)

**Extra providers OnePlus added on its Telephony package**  
_Source: Rapid7_

To make matters worse, client-supplied inputs aren’t sanitized, allowing “blind SQL injection” that could reconstruct SMS content from the device database, bruteforcing it one character at a time.

“By using an algorithm to repeat this process for each character in each row returned by the sub query, it’s possible to exfiltrate the database content, using the return value from the update method as an indicator of true/false,” describes Rapid7 in the [report](http://www.rapid7.com/blog/post/cve-2025-10184-oneplus-oxygenos-telephony-provider-permission-bypass-not-fixed/).

So, while the read permission for SMS is correctly set, the write permission isn’t, allowing the inference of SMS content when certain prerequisites are met: 

1. Exposed table must already contain at least one row, so update() can return a non-zero “rows changed” result.
2. The provider must allow insert() so an attacker can create a dummy row to operate on if the table is empty.
3. The sms table must be in the same SQLite database file because the injected subquery must be able to reference it.

![PoC exploit to infer SMS content](https://www.bleepstatic.com/images/news/u/1220909/2025/September/poc.jpg)

**PoC exploit to infer SMS content**  
_Source: Rapid7_

## Impact and response

The issue impacts all versions of OxygenOS from 12 to the latest one, which is 15, which is the latest, built on top of Android 15.

Rapid7 researchers tested and confirmed vulnerability on OnePlus 8T and 10 Pro, running various OxygenOS versions and Telephony package numbers, but noted that their list is almost definitely non-exhaustive.

“While the build numbers above \[on the table\] are specific to the test devices, as the issue affects a core component of Android, we expect this vulnerability to affect other OnePlus devices running the above versions of OxygenOS, i.e., it does not seem to be a hardware-specific issue,” explained Rapid7.

| **Device / Model**         | **Package version** | **OxygenOS version** | **Build Number**         |
| -------------------------- | ------------------- | -------------------- | ------------------------ |
| OnePlus 8T / KB2003        | 3.4.135             | 12                   | KB2003\_11\_C.3          |
| OnePlus 10 Pro 5G / NE2213 | 14.10.30            | 14                   | NE2213\_14.0.0.700(EX01) |
| OnePlus 10 Pro 5G / NE2213 | 15.30.5             | 15                   | NE2213\_15.0.0.502(EX01) |
| OnePlus 10 Pro 5G / NE2213 | 15.30.10            | 15                   | NE2213\_15.0.0.700(EX01) |
| OnePlus 10 Pro 5G / NE2213 | 15.40.              | 15                   | NE2213\_15.0.0.901(EX01) |

The researchers tried to contact OnePlus to share their findings on May 1 and followed up on alternative email addresses multiple times until August 16.

After receiving no response to seven separate communication attempts, the security firm publicly disclosed the details for CVE-2025-10184.

Shortly after publication of Rapid7's report, OnePlus acknowledged the disclosure and said they have launched an investigation into the problem.

BleepingComputer has contacted OnePlus to request a comment, but we are still awaiting a response.

Until a patch is made available, it is recommended to keep the number of installed apps on your OnePlus device to a minimum, only trust reputable publishers, and switch from SMS-based two-factor authentication to OTP apps like Google Authenticator.

Since SMS isn’t properly isolated on OnePlus devices, sensitive communications should only occur on end-to-end encrypted apps.