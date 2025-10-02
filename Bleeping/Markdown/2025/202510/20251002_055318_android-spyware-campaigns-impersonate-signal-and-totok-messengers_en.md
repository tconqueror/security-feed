# Android spyware campaigns impersonate Signal and ToTok messengers

![Android spyware campaigns impersonate Signal and ToTok messengers](https://www.bleepstatic.com/content/hl-images/2024/01/12/android-eyes.jpg)

Two new spyware campaigns that researchers call ProSpy and ToSpy lured Android users with fake upgrades or plugins for the Signal and ToTok messaging apps to steal sensitive data.

To give the malicious files a sense of legitimacy, the threat actor distributed them through websites that impersonated the two communication platforms.

Signal is a popular end-to-end encrypted messenger with more than 100 million downloads on Google Play.

ToTok is developed by the UAE-based artificial intelligence company G42 and was kicked out from the Apple and Google app stores in 2019 after allegations of being a spying tool for the UAE government.

Currently, ToTok is available for download from its official website and third-party app stores.

### Stealth and persistence

Researchers at cybersecurity company ESET discovered the ProSpy campaign in June but they believe that the activity may have started since at least 2024\. Based on their analysis, the malicious campaigns are targeting users in the United Arab Emirates.

During the investigation, they discovered "two previously undocumented spyware families" that pretend to be a Signal Encryption Plugin and a Pro variant of the ToTok app, none of which exist.

The operator of the spyware campaign distributed the malicious APK files through web pages that impersonated the official Signal website (_https://signal.ct\[.\]ws_ and _https://encryption-plug-in-signal.com-ae\[.\]net/_) and the Samsung Galaxy Store (_store.latestversion\[.\]ai_ and _https://store.appupdate\[.\]ai_).

![Fake Signal plugin website](https://www.bleepstatic.com/images/news/u/1220909/2025/October/signal-site.jpg)

**Fake Signal plugin website**  
_Source: ESET_

BleepingComputer tried accessing the fraudulent website but most of them were offline and one redirected to the official ToTok website.

When executed, the ProSpy malware samples request access to the contact list, SMS, and files, which are the typical permissions for messenger apps.

Once active on the device, the malware exfiltrates the following data:

* device information (hardware, operating system, IP address)
* stored SMS texts, the contact list
* files (audio, documents, images, videos)
* ToTok backup files
* list of the installed applications

To stay hidden, the Signal Encryption Plugin uses the 'Play Services' icon and label on the home screen. Furthermore, when tapping the icon the info screen of a legitimate Google Play Service app will open.

The diagram below explains how a ProSpy compromise works. The threat made an effort to avoid raising user suspicion by redirecting them to the official download site when the legitimate app was missing on the device.

![The ProSpy execution flow](https://www.bleepstatic.com/images/news/u/1220909/2025/October/prospy.jpg)

**The ProSpy execution flow**  
_Source: ESET_

### ToSpy campaign may have originated in 2022

According to the researches, the ToSpy campaign is still continuing, based on the active status of the command-and-control (C2) infrastructure.

ESET notes that this activity may date as far back as 2022, as they found multiple indicators pointing to that period: a developer certificate created on May 24, 2022, a domain used for distribution and C2 registered on May 18 that year, and samples uploaded to the VirusTotal scanning platform on June 30.

**Fake Galaxy Store page**  
_Source: ESET_

The fake ToTok app distributed in this campaign prompts victims to grant contact and storage access permissions, and collects the associated data, focusing on documents, images, video, and ToTok chat backups (.ttkmbackup files).

ESET's report notes that all exfiltrated data is first encrypted using the AES symmetric encryption algorithm in CBC mode.

For stealth, ToSpy launches the real ToTok app when opened, if it's available on the device.

If the app is not present, the malware tries to open the Huawei AppGallery (either the legitimate app or the default web browser) so the user can get the official ToTok app.

**The ToSpy execution flow**  
_Source: ESET_

Both spyware families use three persistence mechanisms on infected devices:

* Abuse of the ‘AlarmManager’ Android system API to restart automatically if killed.
* Use a foreground service with persistent notifications so the system treats it as a high-priority process.
* Registers to receive BOOT\_COMPLETED broadcast events so it can restart the spyware upon device reboot without user interaction.

ESET has shared a comprehensive list of [indicators of compromise](https://github.com/eset/malware-ioc/tree/master/prospytospy) (IoCs) associated with the ProSpy and ToSpy campaigns, but attribution remains inconclusive.

Android users are recommended to download apps only from official or trusted repositories, or directly from the publisher's webisite. They should keep the Play Protect service active on their device to disable already known threats.