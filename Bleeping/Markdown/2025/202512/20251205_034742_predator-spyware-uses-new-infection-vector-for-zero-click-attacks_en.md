# Predator spyware uses new infection vector for zero-click attacks

![Predator spyware uses new infection vector for zero-click attacks](https://www.bleepstatic.com/content/hl-images/2025/12/04/hacked.jpg)

The Predator spyware from surveillance company Intellexa has been using a zero-click infection mechanism dubbed “Aladdin,” which compromised specific targets by simply viewing a malicious advertisement.

This powerful and previously unknown infection vector is meticulously hidden behind shell companies spread across multiple countries, now uncovered in a new joint investigation by [Inside Story](https://insidestory.gr/article/intellexa-leaks-nea-thymata-toy-predator-para-tis-amerikanikes-kyroseis?token=VvhXd6gD6X), [Haaretz](https://www.haaretz.com/israel-news/security-aviation/2025-12-03/ty-article-magazine/.premium/israeli-spyware-firm-intellexa-owned-by-ex-intel-officer-still-active-amid-us-sanctions/0000019a-e3e8-db35-afbf-ebfcb8bb0000), and [WAV Research Collective](https://www.inside-it.ch/intellexa-leaks-beruechtigte-spionagefirma-weiterhin-aktiv-20251203).

The investigation is based on 'Intellexa Leaks' - a collection of leaked internal company documents and marketing material, and is corroborated by technical research from forensic and security experts at Amnesty International, Google, and Recorded Future.

![Leaked marketing material](https://www.bleepstatic.com/images/news/u/1220909/2025/December/capabilities.jpg)

**Leaked Intellexa marketing material**  
_Source: Amnesty International_

### Ad-based spyware delivery

First deployed in 2024 and believed to still be operational and actively developed, Aladdin leverages the commercial mobile advertising system to deliver malware.

The mechanism forces weaponized ads onto specific targets identified by their public IP address and other identifiers, instructing the platforms via the Demand Side Platform (DSP) to serve it on any website participating in the ad network.

“This malicious ad could be served on any website that displays ads, such as a trusted news website or mobile app, and would appear like any other ad that the target is likely to see,” [explains Amnesty International’s Security Lab](https://securitylab.amnesty.org/latest/2025/12/intellexa-leaks-predator-spyware-operations-exposed/).

“Internal company materials explain that simply viewing the advertisement is enough to trigger the infection on the target’s device, without any need to click on the advertisement itself.”

![Overview of Aladdin](https://www.bleepstatic.com/images/news/u/1220909/2025/December/aladdin.jpg)

**Overview of Aladdin**  
_Source: Amnesty International_

Although no details are available on how the infection works, Google mentions that the ads trigger redirections to Intellexa’s exploit delivery servers.

The ads are funneled through a complex network of advertising firms spread across multiple countries, including Ireland, Germany, Switzerland, Greece, Cyprus, the UAE, and Hungary.

Recorded Future dug deeper into the advertising network, connecting the dots between key people, firms, and infrastructure, and naming some of those companies [in its report](https://www.recordedfuture.com/research/intellexas-global-corporate-web).

Defending against those malicious ads is complex, but blocking ads on the browser would be a good starting point.

Another potential defense measure would be to set the browser to hide the public IP from trackers.

However, the leaked documents show that Intellexa can still obtain the information from domestic mobile operators in their client’s country.

**Countries confirmed to host Predator activity**  
_Source: Recorded Future_

## Samsung Exynos and zero-day exploits

Another key finding in the leak is confirmation of the existence of another delivery vector called 'Triton', which can target devices with Samsung Exynos with baseband exploits, forcing [2G downgrades](https://www.bleepingcomputer.com/news/google/android-14-to-let-you-block-connections-to-unencrypted-cellular-networks/) to lay the ground for infection.

Amnesty International’s analysts are unsure whether this vector is still used and note that there are two other, possibly similar delivery mechanisms, codenamed 'Thor' and 'Oberon', believed to involve radio communications or physical access attacks.

Google’s researchers [name](https://cloud.google.com/blog/topics/threat-intelligence/intellexa-zero-day-exploits-continue) Intellexa as one of the most prolific commercial spyware vendors in terms of zero-day exploitation, responsible for 15 out of the 70 cases of zero-day exploitation TAG discovered and documented since 2021.

Google says Intellexa develops its own exploits and also purchases exploit chains from external entities to cover the full spectrum of required targeting.

Despite sanctions and ongoing investigations against Intellexa in Greece, the spyware operator is as active as ever, according to Amnesty International.

As Predator evolves into becoming stealthier and harder to trace, users are recommended to consider enabling extra protection on their mobile devices, like [Advanced Protection](https://www.bleepingcomputer.com/news/security/android-16-expands-advanced-protection-with-device-level-security/) on Android and [Lockdown Mode](https://www.bleepingcomputer.com/news/apple/apple-s-new-lockdown-mode-defends-against-government-spyware/) on iOS.