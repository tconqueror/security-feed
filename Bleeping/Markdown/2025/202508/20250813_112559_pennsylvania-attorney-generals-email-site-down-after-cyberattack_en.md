# Pennsylvania attorney general's email, site down after cyberattack

![Pennsylvania Attorney General Dave Sunday](https://www.bleepstatic.com/content/hl-images/2025/08/13/Pennsylvania_Attorney_General_Dave_Sunday.jpg)

The Office of the Pennsylvania Attorney General has announced that a recent cyberattack has taken down its systems, including landline phone lines and email accounts.

As Attorney General Dave Sunday revealed on social media on Monday, the office staff is currently working to restore affected services and investigate the incident with the help of law enforcement authorities.

"The network that hosts the Office of Attorney General's systems is currently down, meaning the office's website is offline, as are office email accounts and land phone lines," [Sunday said](https://www.facebook.com/PaAttorneyGen/posts/1334533431364939).

"We are taking steps to determine the cause of the cyber incident, and working to restore services on all avenues. Office of Attorney General staff are continuing to advocate on behalf of the Commonwealth and are working with supervisors to minimize any interruptions."

Pennsylvania's attorney general has yet to attribute the attack to a specific group officially. However, the incident's widespread and crippling impact bears all the signs of a ransomware attack, even though no ransomware operation has claimed responsibility to date.

While incident responders continue to work on restoring impacted systems, the [website of Pennsylvania's Attorney General](https://www.attorneygeneral.gov/) was still offline at the time this article was published.

![Pennsylvania Attorney General site down](https://www.bleepstatic.com/images/news/u/1109292/2025/PA%20OAG%20site.png)

_Office of Pennsylvania's attorney general website (BleepingComputer)_

Although the attack vector is still unknown, [cybersecurity expert Kevin Beaumont had found,](https://cyberplace.social/@GossiTheDog/114852498783201767) one month prior, that several public-facing Citrix NetScaler appliances on the Pennsylvania AG's network were vulnerable to ongoing attacks exploiting a critical vulnerability tracked as CVE-2025-5777 (also known as [Citrix Bleed 2](https://www.bleepingcomputer.com/tag/citrixbleed2/)).

According to Shodan scans shared by Beaumont, one of the two devices [has been offline since July 29th](https://beta.shodan.io/host/207.218.103.19), while the other [was taken down on August 7th](https://beta.shodan.io/host/207.218.103.174).

On Monday, the internet security nonprofit Shadowserver Foundation [reported](https://bsky.app/profile/shadowserver.bsky.social/post/3lw6z7psrbs2u) that over 3,300 Citrix NetScaler appliances were still vulnerable to CVE-2025-5777 attacks.

The same day, the Netherlands' National Cyber Security Centre (NCSC) [warned](https://www.bleepingcomputer.com/news/security/netherlands-citrix-netscaler-flaw-cve-2025-6543-exploited-to-breach-orgs/) that attackers have exploited the flaw as a zero-day since at least early May to breach multiple critical organizations in the country.

The Openbaar Ministerie (the Netherlands' Public Prosecution Service), which only [recently](http://www.om.nl/onderwerpen/inbreuk-om-ict/nieuws/2025/08/04/om-gaat-stapsgewijs-online) restored its [email servers](http://www.om.nl/onderwerpen/inbreuk-om-ict/nieuws/2025/08/07/om-is-weer-per-mail-bereikbaar), also [disclosed a breach](https://www.om.nl/onderwerpen/inbreuk-om-ict/nieuws/2025/07/18/onderzoek-naar-aanleiding-van-signaal-ncsc) on July 18th that led to [significant operational disruptions](http://www.om.nl/onderwerpen/inbreuk-om-ict/nieuws/2025/07/21/werk-om-mogelijk-komende-weken-nog-verstoord).

CISA has added the CVE-2025-5777 Citrix vulnerability to its Known Exploited Vulnerabilities catalog, [ordering federal agencies to patch their systems](http://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-5777&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) against active exploitation within a day.