# Massive Rainbow Six Siege breach gives players billions of credits

![Rainbow Six Siege](https://www.bleepstatic.com/content/hl-images/2025/12/28/rainbow-6-siege.jpg)

Ubisoft's Rainbow Six Siege (R6) suffered a breach that allowed hackers to abuse internal systems to ban and unban players, manipulate in-game moderation feeds, and grant massive amounts of in-game currency and cosmetic items to accounts worldwide.

According to multiple [player reports](https://x.com/kinggeorge/status/2004902566434668686) and in-game screenshots shared online, the attackers were able to:

* Ban/unban Rainbow Six Siege players
* Display fake ban messages on the ban ticker.
* Grant all players approximately 2 billion R6 Credits and Renown
* Unlock every cosmetic item in the game, including developer-only skins

R6 Credits are a premium in-game currency sold for real money on Ubisoft's store. Based on Ubisoft's pricing, 15,000 R6 Credits cost $99.99, placing the value of 2 billion credits at roughly $13.33 million worth of in-game currency distributed for free.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

At 9:10 AM on Saturday, the official Rainbow Six Siege account on X [confirmed the incident](https://x.com/Rainbow6Game/status/2004917731829948808), stating that Ubisoft was aware of an issue affecting the game and that teams were working to resolve it.

Shortly afterward, Ubisoft intentionally shut down Rainbow Six Siege and its in-game Marketplace, stating they were still working on the issue.

"Siege and the Marketplace have been intentionally shut down while the team focuses on resolving the issue," [reads a post on X](http://x.com/rainbow6game/status/2004943312390926740).

In a final update, Ubisoft clarified that players would not be punished for spending the granted credits, but that it would be rolling back all transactions made since 11:00 AM UTC.

The company also stated that Ubisoft did not generate the messages seen in the ban ticker and that the ticker had been disabled previously.

![Fake ban messages on the Rainbow Six Siege ban ticker](https://www.bleepstatic.com/images/news/security/attacks/r/rainbow-six/r6-ban-hack.jpg)

**Fake ban messages on the Rainbow Six Siege ban ticker**  
_Source: [@ViTo\_DEE91](https://x.com/ViTo%5FDEE91/status/2004910559884628290)_

Ubisoft said it was continuing to work toward fully restoring the game, but the servers remain down at this time.

At this time, Ubisoft has not released a formal statement regarding the incident and has not responded to emails from BleepingComputer requesting details on how the breach occurred.

If you have any information regarding this incident or any other undisclosed attacks, you can contact us confidentially via Signal at 646-961-3731 or at tips@bleepingcomputer.com.

## Rumors of a larger breach

Unverified claims state that a much larger breach occurred within Ubisoft's infrastructure.

According to security research group [VX-Underground](https://x.com/vxunderground/status/2005008887234048091), threat actors claimed to have breached Ubisoft's servers using a recently disclosed MongoDB vulnerability dubbed "MongoBleed."

Tracked as CVE-2025-14847, the flaw allows unauthenticated remote attackers to leak the memory of exposed MongoDB instances, exposing credentials and authentication keys. A public PoC exploit has already been released that searches for secrets in exposed MongoDB servers.

VX-Underground reports that multiple unrelated threat groups may have targeted Ubisoft:

* One group claims to have exploited a Rainbow Six Siege service to manipulate bans and in-game inventory without accessing user data.
* A second group allegedly exploited a MongoDB instance using MongoBleed to pivot into Ubisoft's internal Git repositories, claiming to steal a large archive of internal source code from the 1990s to the present.
* A third group claims to have stolen Ubisoft user data via MongoBleed and is attempting to extort the company into paying a ransom.
* A fourth group disputes some of these claims, stating that the second group had access to Ubisoft's source code for a while.

BleepingComputer has not been able to independently verify any of these claims, including whether MongoBleed was exploited, whether internal source code was accessed, or whether customer data was stolen.

At this time, we only know that Ubisoft has confirmed the in-game abuse in Rainbow Six Siege, and there is no public evidence of a larger breach.

BleepingComputer will update this story if Ubisoft provides additional details or if we learn more about these other claims.