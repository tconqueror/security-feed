# Mozilla Firefox gets new anti-fingerprinting defenses

![Mozilla Firefox gets new anti-fingerprinting defenses](https://www.bleepstatic.com/content/hl-images/2024/03/22/Firefox-headpic.jpg)

Mozilla announced a major privacy upgrade in Firefox 145 that reduces even more the number of users vulnerable to digital fingerprinting.

The new protections will initially be available only in Private Browsing Mode and Enhanced Tracking Protection (ETP) Strict mode. After testing and optimization, they will be enabled by default in the Firefox web browser.

Fingerprinting is a tracking technique that allows tracking users' browsing activity and identifying them across websites and browser sessions, even when cookies are blocked or with private browsing active.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Subtle identifiers, like timezone, hardware and browser details, can be used to create a unique digital signature to identify users on the internet.

This type of data can be your browser's version, operating system, screen resolution and color depth, system language, installed fonts, time zone, GPU rendering behavior, CPU cores, touchscreen capabilities, and device memory.

Firefox’s existing anti-fingerprinting system, part of the software’s ‘Enhanced Tracking Protection’ mechanism, blocks many known tracking and fingerprinting scripts, most of which are intrinsically pervasive and not related to improving the user’s experience.

“Since 2021, Firefox has been incrementally advancing fingerprinting protections, covering the most pervasive fingerprinting techniques,” [explains Mozilla](https://blog.mozilla.org/en/firefox/fingerprinting-protections/).

“These include things like how your graphics card draws images, which fonts your computer has, and even tiny differences in how it performs math.”

These anti-fingerprinting blocks, which Mozilla marks as ‘Phase 1 Protections’ reduced trackability to roughly 35%, compared to the baseline 65% for now protections at all.

Now, ‘Phase 2’ protections are being rolled out, which block requests to discover installed fonts, hardware details, number of processor cores, multi-touch support, and dock/taskbar dimensions.

Specifically, the new protections constitute the following:

* Random noise is added to background images only when a site reads them back, not when they are just displayed.
* Only standard OS fonts are used; local fonts are blocked, except for key language fonts like Japanese, Thai, Arabic, Chinese, Korean, and Hebrew.
* Touch support is reported as 0, 1, or 5.
* The available screen resolution is the screen height minus 48 pixels.
* Processor cores are always reported as 2.

As a result of these additional measures, only 20% of users can still be uniquely fingerprinted and persistently tracked.

![Percentage of user trackability in each case](https://www.bleepstatic.com/images/news/u/1220909/2025/November/perc.png)

**Percentage of user trackability in each case**  
_Source: Mozilla_

Mozilla explained that it cannot aggressively block everything to reduce trackability further, as this would eventually lead to usability issues that break legitimate website features.

Various productivity tools rely on actual real-time and location data to provide the intended functionality, so a portal of exchange needs to be maintained, even if its size is shrinking.

Those who are facing usability problems with the new layers of protection are given the option to [disable them on specific sites](https://support.mozilla.org/en-US/kb/firefox-protection-against-fingerprinting#w%5Fhow-do-i-disable-this-protection-for-a-website).

Firefox 145 will be officially released tomorrow, but users can already download an installer for their OS from [Mozilla’s FTP server](https://ftp.mozilla.org/pub/firefox/releases/145.0/).

Note that this is the first release that doesn’t offer a 32-bit Linux version, which Mozilla deprecated due to waning user demand not making its development and testing worthwhile anymore.