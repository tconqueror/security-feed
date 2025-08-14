# Booking.com phishing campaign uses sneaky 'ん' character to trick you

![booking.com](https://www.bleepstatic.com/content/hl-images/2025/03/13/booking-com-header.jpg)

Threat actors are leveraging a Unicode character to make phishing links appear like legitimate Booking.com links in a new campaign distributing malware.

The attack makes use of the Japanese hiragana character, ん, which can, on some systems, appear as a forward slash and make a phishing URL appear realistic to a person at a casual glance.

BleepingComputer has further come across an Intuit phishing campaign using a lookalike domain using the letter L instead of 'i' in Intuit.

## Booking.com phishing links using Japanese homoglyphs

The attack, first spotted by security researcher [JAMESWT](https://x.com/JAMESWT%5FWT), abuses the Japanese hiragana character “ん” (Unicode U+3093), which closely resembles the Latin letter sequence '/n' or '/\~', at a quick glance in some fonts. This visual similarity enables scammers to create URLs that appear to belong to the genuine Booking.com domain, but direct users to a malicious site.

Below is a copy of the phishing email [shared by](https://x.com/JAMESWT%5FWT/status/1955060839569870991) the security researcher:

![Copy of phishing email shared by security researcher JamesWt](https://www.bleepstatic.com/images/news/u/1164866/2025/Aug/booking.com-phishing/email.jpeg)

**Copy of phishing email shared by security researcher JamesWT**

The text in the email, _https://admin.booking.com/hotel/hoteladmin/..._ itself is deceptive. While it may look like a Booking.com address, the hyperlink points to:

`https://account.booking.comんdetailんrestric-access.www-account-booking.com/en/`

![Phishing page as it appears in a web browser](https://www.bleepstatic.com/images/news/u/1164866/2025/Aug/booking.com-phishing/booking-bleeping-url.jpg)

**Phishing page as it appears in a web browser**

When rendered in a web browser's address bar, the 'ん' characters can trick users into thinking they are navigating through a subdirectory of booking.com.

In reality, the actual registered domain is _www-account-booking\[.\]com_, a malicious lookalike, and everything before that is just a deceptive subdomain string.

Victims who click through are eventually redirected to:

`www-account-booking[.]com/c.php?a=0`

This in turn delivers a malicious MSI installer from a CDN link, _https://updatessoftware.b-cdn\[.\]net/john/pr/04.08/IYTDTGTF.msi_

Samples of the malicious site are available on abuse.ch's [MalwareBazaar](https://bazaar.abuse.ch/browse/tag/www-account-booking--com/), with any.run [analysis](https://app.any.run/tasks/35618d39-0189-4eec-87f0-ce918ecf95f4) showing the infection chain. The MSI file is used to drop further payloads, potentially including infostealers or remote access trojans.

This phishing tactic exploits homoglyphs. A homoglyph is a character that looks similar to another character but belongs to a different character set or alphabet. These visually similar characters can be exploited in phishing attacks or to create misleading content. For example, Cyrillic character "О" (U+041E) may appear identical to the Latin letter "O" (U+004F) to a human, but they are different characters.

Given their visual similarities, homoglyphs have been leveraged [time and time again](https://www.bleepingcomputer.com/news/security/hackers-abuse-lookalike-domains-and-favicons-for-credit-card-theft/) by threat actors in [homograph attacks](https://www.bleepingcomputer.com/news/security/chrome-firefox-and-opera-vulnerable-to-undetectable-phishing-attack/) and phishing emails. Defenders and software developers have also, over the last few years, [rolled out security measures](https://wiki.mozilla.org/IDN%5FDisplay%5FAlgorithm) that make it easy for users to distinguish between distinct homoglyphs.

Luckily, in tests by BleepingComputer, the hiranga character ん wouldn't render as easily on web browsers of either Android or iPhone models (at least when the standard Latin character set and English language keyboard were use), making the trick much easier for threat actors to pull off on desktops.

This isn't the first time threat actors have targeted Booking.com customers either.

In March this year, Microsoft warned of phishing campaigns [impersonating Booking.com and using ClickFix](https://www.bleepingcomputer.com/news/security/clickfix-attack-delivers-infostealers-rats-in-fake-bookingcom-emails/) social engineering attacks to infect hospitality workers with malware.

In 2023, Akamai revealed how hackers were redirecting hotel guests to [fake Booking.com sites](https://www.bleepingcomputer.com/news/security/hotel-hackers-redirect-guests-to-fake-bookingcom-to-steal-cards/) to steal credit card information.

## 'Lntuit' not Intuit

BleepingComputer's [Sergiu Gatlan](https://www.bleepingcomputer.com/author/sergiu-gatlan/) spotted a separate phishing campaign involving users being targeted with Intuit-themed emails.

These emails appear to come from and take you to _intuit.com_ addresses, but instead use domains starting with _Lntuit—_which, in lowercase, can resemble "intuit" in certain fonts. A simple yet effective technique.

**Intuit phishing email from 'Lntuit.com' viewed on Mailspring for macOS** (Sergiu Gatlan)

The unusually narrow layout of this email in desktop clients suggests it was primarily designed for mobile viewing, with attackers banking on mobile users clicking the "Verify my email" phishing link without closely inspecting it.

The button takes users to: `https://intfdsl[.]us/sa5h17/`

**How Intuit phishing email appears on mobile** (Sergiu Gatlan)

Interestingly, the illicit link, when accessed directly i.e. not from the target user's email account appears to redirect the user back to the legitimate Intuit.com login page at _https://accounts.intuit.com/app/sign-in_.

These incidents are a reminder that attackers will continue to find creative ways to abuse typography for social engineering.

To protect yourself, always hover over links before clicking to reveal the true target.

Users should always check the actual domain at the rightmost end of the address before the first single / — this is the real registered domain. Granted, the use of visually deceptive Unicode characters like 'ん' create additional hurdles, and demonstrate that visual URL inspection alone isn't foolproof.

Keeping endpoint security software up to date adds another layer of defense against attacks since modern phishing kits often deliver malware directly, after a phishing link is clicked.