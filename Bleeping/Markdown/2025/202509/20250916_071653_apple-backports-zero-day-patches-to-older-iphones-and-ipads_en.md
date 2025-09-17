# Apple backports zero-day patches to older iPhones and iPads

![Apple](https://www.bleepstatic.com/content/hl-images/2023/09/11/apple_triangle.jpg)

​Apple has released security updates to backport patches released last month to older iPhones and iPads, addressing a zero-day bug that was exploited in "extremely sophisticated" attacks.

This security flaw is the same one Apple [has patched](https://www.bleepingcomputer.com/news/apple/apple-emergency-updates-fix-new-actively-exploited-zero-day/) for devices running iOS 18.6.2 and iPadOS 18.6.2, iPadOS 17.7.10, and macOS (Sequoia 15.6.1, Sonoma 14.7.8, and Ventura 13.7.8) on August 20.

Tracked as [CVE-2025-43300](https://nvd.nist.gov/vuln/detail/CVE-2025-43300), this vulnerability was discovered by Apple security researchers and is caused by an [out-of-bounds write weakness ](https://cwe.mitre.org/data/definitions/787.html)in the Image I/O framework, which enables apps to read and write image file formats.

An out-of-bounds write occurs when attackers supply maliciously crafted input to a program that causes it to write data outside the allocated memory buffer, potentially triggering crashes, corrupting data, or even allowing remote code execution.

Apple has now addressed this zero-day flaw in iOS 15.8.5 / 16.7.12, as well as iPadOS 15.8.5 / 16.7.12, with improved bounds checks.

"Processing a malicious image file may result in memory corruption. An out-of-bounds write issue was addressed with improved bounds checking," the company said in [Monday](http://support.apple.com/en-us/125142) [advisories](https://support.apple.com/en-us/125141).

"Apple is aware of a report that this issue may have been exploited in an extremely sophisticated attack against specific targeted individuals."

The list of devices impacted by this vulnerability is quite extensive, with the bug affecting a wide range of older models, including:

* iPhone 6s (all models), iPhone 7 (all models), iPhone SE (1st generation), iPhone 8, iPhone 8 Plus, and iPhone X,
* iPad Air 2, iPad mini (4th generation), iPad 5th generation, iPad Pro 9.7-inch, iPad Pro 12.9-inch 1st generation, and iPod touch (7th generation)

In late August, WhatsApp patched a [zero-click vulnerability](https://www.bleepingcomputer.com/news/security/whatsapp-patches-vulnerability-exploited-in-zero-day-attacks/) (CVE-2025-55177) in its iOS and macOS messaging clients, which was chained with Apple's CVE-2025-43300 zero-day in targeted attacks that the company described as "extremely sophisticated."

While Apple and WhatsApp have yet to release any details regarding the attacks chaining the two vulnerabilities, Donncha Ó Cearbhaill, the head of Amnesty International's Security Lab, [said](https://x.com/DonnchaC/status/1961444710620303653) that WhatsApp warned some of its users that their devices were targeted in an advanced spyware campaign.

Last week, Samsung also [patched a remote code execution vulnerability](https://www.bleepingcomputer.com/news/security/samsung-patches-actively-exploited-zero-day-reported-by-whatsapp/) chained with the CVE-2025-55177 WhatsApp flaw in zero-day attacks targeting its Android devices.

With this vulnerability, Apple fixed six zero-days that were exploited in the wild in 2025: the [first in January](https://www.bleepingcomputer.com/news/security/apple-fixes-this-years-first-actively-exploited-zero-day-bug/) (CVE-2025-24085), [the second in February](https://www.bleepingcomputer.com/news/apple/apple-fixes-zero-day-exploited-in-extremely-sophisticated-attacks/) (CVE-2025-24200), a [third in March](https://www.bleepingcomputer.com/news/apple/apple-fixes-webkit-zero-day-exploited-in-extremely-sophisticated-attacks/) (CVE-2025-24201), and [two more in April](https://www.bleepingcomputer.com/news/security/apple-fixes-two-zero-days-exploited-in-targeted-iphone-attacks/)(CVE-2025-31200 and CVE-2025-31201).