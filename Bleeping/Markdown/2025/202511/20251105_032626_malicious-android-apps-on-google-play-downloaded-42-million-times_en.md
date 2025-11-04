# Malicious Android apps on Google Play downloaded 42 million times

![Malicious Android apps on Google Play downloaded 42 million times](https://www.bleepstatic.com/content/hl-images/2024/05/03/Android-2.jpg)

Hundreds of malicious Android apps on Google Play were downloaded more than 40 million times between June 2024 and May 2025, notes a report from cloud security company Zscaler.

During the same period, the company observed a 67% year-over-year growth in malware targeting mobile devices, with spyware and banking trojans being a prevalent risk.

Telemetry data shows that threat actors are shifting from traditional card fraud to exploiting mobile payments using phishing, smishing, SIM-swapping, and payment scams.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

The transition to attacks based on social engineering is explained by the improved security standards, such as chip-and-PIN technology, and the wide adoption of mobile payments.

"To carry out these attacks, cybercriminals deploy phishing trojans and malicious apps designed to steal financial information and login credentials," Zscaler says.

According to the company, banking malware has grown significantly over the past three years, reaching 4.89 million transactions in 2025\. However, the growth rate was just 3% over the observed period, down from 29% the previous year.

![Blocked banking trojan transactions ](https://www.bleepstatic.com/images/news/u/1220909/2025/November/transactions.jpg)

**Blocked banking trojan transactions**  
_Source: Zscaler_

Compared to last year, when Zscaler discovered [200 malware apps on Google Play](https://www.bleepingcomputer.com/news/security/over-200-malicious-apps-on-google-play-downloaded-millions-of-times/), the company now reports finding 239 malicious applications in the official Android store that collectively counted 42 million downloads.

Another notable trend recorded during the same period is the rise of adware as the most prominent threat in the Android ecosystem, now accounting for roughly 69% of all detections, almost double from last year.

The Joker info-stealer, which led with 38% last year, has now dropped to second place with 23%.

Spyware also recorded a significant rise of 220% year-over-year (YoY), with SpyNote, SpyLoan, and BadBazaar families, used for surveillance, extortion, and identity theft, being the main driving forces.

In terms of geographic impact, India, the United States, and Canada received 55% of all attacks. Zscaler also saw massive spikes in attacks targeting Italy and Israel, ranging from 800% to 4000% YoY increase.

**Top ten most impacted countries**  
_Source: Zscaler_

## Highlighted malware

Zscaler highlights in its yearly report three malware families, which had a notable impact on Android users. The first is Anatsa, a banking trojan that [sneaks periodically into Google Play](https://www.bleepingcomputer.com/news/security/android-malware-anatsa-infiltrates-google-play-to-target-us-banks/) via productivity/utilities apps and gets even [hundreds of thousands of downloads](https://www.bleepingcomputer.com/news/security/malicious-android-apps-with-19m-installs-removed-from-google-play/) each time.

Anatsa has been constantly evolving since its discovery in 2020\. The latest variant can steal data from over 831 financial organizations, cryptocurrency platforms, and new regions like Germany and South Korea.

The second is [Android Void (Vo1d)](https://www.bleepingcomputer.com/news/security/new-vo1d-malware-infects-13-million-android-streaming-boxes/), a backdoor malware targeting Android TV boxes, which has infected at least 1.6 million devices running outdated Android Open Source Project (AOSP) versions, primarily in India and Brazil.

The third is Xnotice, a new Android remote access trojan (RAT) that targets job seekers in the oil & gas industry, especially in Iran and Arabic-speaking regions.

**Xnotice attacks overview**  
_Source: Zscaler_

Xnotice spreads through apps masquerading as job application or exam registration tools, which are distributed through fake employment portals.

The malware targets banking credentials through overlays, multi-factor authentication (MFA) codes, SMS messages, and can also take screenshots.

To defend against Android malware threats, even from Google Play, users are advised to apply security updates, only trust reputable publishers, reject/disable Accessibility permissions, avoid downloading non-essential apps, and regularly run Play Protect scans.

Zscaler's report also includes trends related to IoT devices, where routers were still the most targeted this year. Hackers exploited command injection vulnerabilities to add routers to botnets or to convert them into proxies for malware delivery.

Most IoT attacks occurred in the U.S., followed by Hong Kong, Germany, India, and China as emerging hotbeds, an indication of attackers targeting devices across a wider geography.

The cybersecurity company recommends organizations implement zero-trust technology for critical networks and harden IoT and cellular gateways by monitoring for anomalies and adding protections at the firmware level.

Additionally, defenses for mobile endpoints should include checking SIM-level traffic for irregularities, protection against phishing attacks, and strict application control policies.