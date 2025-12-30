# Zoom Stealer browser extensions harvest corporate meeting intelligence

![Zoom Stealer browser extensions harvest corporate meeting intelligence](https://www.bleepstatic.com/content/hl-images/2021/09/23/Chrome_flare.jpg)

A newly discovered campaign, which researchers call Zoom Stealer, is affecting 2.2 million Chrome, Firefox, and Microsoft Edge users through 18 extensions that collect online meeting-related data like URLs, IDs, topics, descriptions, and embedded passwords.

Zoom Stealer is one of three browser extension campaigns that reached more than 7.8 million users over seven years and are attributed to a single threat actor tracked as DarkSpectre.

Based on the used infrastructure, DarkSpectre is believed to be the same China-linked threat actor behind the previously documented [GhostPoster](https://www.bleepingcomputer.com/news/security/ghostposter-attacks-hide-malicious-javascript-in-firefox-addon-logos/), which targeted Firefox users, and [ShadyPanda](https://www.bleepingcomputer.com/news/security/shadypanda-browser-extensions-amass-43m-installs-in-malicious-campaign/), which delivered spyware payloads to Chrome and Edge users.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

ShadyPanda remains active through 9 extensions and an additional 85 'sleepers' that build a user base before turning malicious via updates, researchers at supply-chain security company Koi Security say. 

![Campaign discovery flow](https://www.bleepstatic.com/images/news/u/1220909/2025/December/campaigns.jpg)

**Campaign discovery flow**  
_Source: Koi Security_

Although the China connection existed before, attribution is now clearer based on hosting servers on Alibaba Cloud, ICP registrations, code artifacts containing Chinese-language strings and comments, activity patterns that match the Chinese timezone, and monetization targeting tuned to Chinese e-commerce.

### Corporate meeting intelligence

The 18 extensions in the Zoom Stealer campaign are not all meeting-related, and some of them can be used to download videos or as recording assistants: Chrome Audio Capture with 800,000 installations, and Twitter X Video Downloader. Both are still available on the Chrome Web Store at publishing time.

Koi Security researchers note that the extensions are all functional and work as advertised.

**The Chrome Audio Capture extension**  
_Source: Koi Security_

According to the researchers, all extensions in the Zoom Stealer campaign request access to 28 video-conferencing platforms (e.g., Zoom, Microsoft Teams, Google Meet, and Cisco WebEx) and collect the following data:

* Meeting URLs and IDs, including embedded passwords
* Registration status, topics, and scheduled times
* Speaker and host names, titles, biographies, and profile photos
* Company logos, graphics, and session metadata

This data is exfiltrated via WebSocket connections and streamed to the threat actors in real time. This activity is triggered when victims visit webinar registration pages, join meetings, or navigate conferencing platforms.

Koi Security says this data can be used for corporate espionage and sales intelligence, which could be used in social engineering attacks or even to sell meeting links to competitors.

"By systematically collecting meeting links, participant lists, and corporate intelligence across 2.2 million users, DarkSpectre has created a database that could power large-scale impersonation operations - providing attackers with credentials to join confidential calls, participant lists to know who to impersonate, and context to make those impersonations convincing," notes the [report from Koi Security](http://www.koi.ai/blog/darkspectre-unmasking-the-threat-actor-behind-7-8-million-infected-browsers).

Because many of these extensions operated innocuously for extended periods, users should carefully review the permissions the extensions require and limit their number to the necessary minimum.

Koi Security reported the offending extensions, but many are still present on the Chrome Web Store. The researchers published the complete list of active DarkSpectre extensions.

BleepingComputer has contacted InfinityNewTab and Google for a comment and we will update the article when we hear back.