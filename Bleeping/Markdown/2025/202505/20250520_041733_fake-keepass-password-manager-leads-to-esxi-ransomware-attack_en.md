# Fake KeePass password manager leads to ESXi ransomware attack

![Hacker with a KeePass logo](https://www.bleepstatic.com/content/hl-images/2023/10/19/background.jpg)

Threat actors have been distributing trojanized versions of the KeePass password manager for at least eight months to install Cobalt Strike beacons, steal credentials, and ultimately, deploy ransomware on the breached network.

WithSecure's Threat Intelligence team discovered the campaign after they were brought in to investigate a ransomware attack. The researchers found that the attack started with a malicious KeePass installer promoted through Bing advertisements that promoted fake software sites.

As KeePass is open source, the threat actors altered the source code to build a trojanized version, dubbed KeeLoader, that contains all the normal password management functionality. However, it includes modifications that install a Cobalt Strike beacon and export the KeePass password database as cleartext, which is then stolen through the beacon.

WithSecure says that the Cobalt Strike watermarks used in this campaign are linked to an initial access broker (IAB) that is believed to be associated with Black Basta ransomware attacks in the past.

A Cobalt Strike watermark is a unique identifier embedded into a beacon that is tied to the license used to generate the payload.

"This watermark is commonly noted in the context of beacons and domains related to Black Basta ransomware. It is likely used by threat actors operating as Initial Access Brokers working closely with Black Basta," explains [WithSecure](https://labs.withsecure.com/content/dam/labs/docs/W%5FIntel%5FResearch%5FKeePass%5FTrojanised%5FMalware%5FCampaign.pdf).

"We are not aware of any other incidents (ransomware or otherwise) using this Cobalt Strike beacon watermark – this does not mean it has not occurred."

The researchers have found multiple variants of KeeLoader have been discovered, signed with legitimate certificates, and spread through typo-squatting domains like keeppaswrd\[.\]com, keegass\[.\]com, and KeePass\[.\]me.

BleepingComputer has confirmed that the keeppaswrd\[.\]com website is still active and continues to distribute the trojanized KeePass installer \[[VirusTotal](https://www.virustotal.com/gui/file/0000cff6a3c7f7eebc0edc3d1e42e454ebb675e57d6fc1fd968952694b1b44b3)\].

![Fake KeePass site pushing trojanized installer](https://www.bleepstatic.com/images/news/malware/k/keepass/keepass-iab/keepass-malware-site.jpg)

**Fake KeePass site pushing trojanized installer**  
_Source: BleepingComputer_

In addition to dropping Cobalt Strike beacons, the trojanized KeePass program included password-stealing functionality that allowed the threat actors to steal any credentials that were inputted into the program.

"KeeLoader was not just modified to the extent it could act as a malware loader. Its functionality was extended to facilitate the exfiltration of KeePass database data," reads the WithSecure report.

"When KeePass database data was opened; account, login name, password, website, and comments information is also exported in CSV format under %localappdata% as .kp. This random integer value is between 100-999."

![Dumping KeePass credentials](https://www.bleepstatic.com/images/news/malware/k/keepass/keepass-iab/dumping-keepass-credentials.jpg)

**Dumping KeePass credentials**  
_Source: WithSecure_

Ultimately, the attack investigated by WithSecure led to the company's VMware ESXi servers being encrypted with ransomware.

Further investigation into the campaign found an extensive infrastructure created to distribute malicious programs disguised as legitimate tools and phishing pages designed to steal credentials.

The aenys\[.\]com domain was used to host additional subdomains that impersonated well-known companies and services, such as WinSCP, PumpFun, Phantom Wallet, Sallie Mae, Woodforest Bank, and DEX Screener.

Each of these was used to distribute different malware variants or steal credentials. 

WithSecure attributes this activity with moderate confidence to UNC4696, a threat actor group previously linked to [Nitrogen Loader campaigns](https://www.bleepingcomputer.com/news/security/new-nitrogen-malware-pushed-via-google-ads-for-ransomware-attacks/). Previous Nitrogen campaigns were linked to the BlackCat/ALPHV ransomware.

Users are always advised to download software, especially highly sensitive ones like password managers, from legitimate sites and avoid any sites linked in advertisements.

Even if an advertisement displays the correct URL for a software service, it should still be avoided, as [threat actors have repeatedly proven](https://www.bleepingcomputer.com/news/security/convincing-youtube-google-ads-lead-to-windows-support-scams/) that they can [circumvent ad policies](https://www.bleepingcomputer.com/news/security/google-ads-push-fake-google-authenticator-site-installing-malware/) to [display the legitimate URL](https://www.bleepingcomputer.com/news/security/arc-browsers-windows-launch-targeted-by-google-ads-malvertising/) while linking to imposter sites.