# Pennsylvania AG confirms data breach after INC Ransom attack

![Pennsylvania Attorney General Dave Sunday](https://www.bleepstatic.com/content/hl-images/2025/11/17/Pennsylvania_Attorney_General_Dave_Sunday.jpg)

The office of Pennsylvania's attorney general has confirmed that the ransomware gang behind an August 2025 cyberattack stole files containing personal and medical information.

This comes after Attorney General Dave Sunday [confirmed in early September](https://www.bleepingcomputer.com/news/security/pennsylvania-ag-office-says-ransomware-attack-behind-recent-outage/) that the incident was a ransomware attack and his office refused to pay the ransom requested by the cybercriminals after they encrypted compromised systems.

"The OAG later learned that certain files may have been accessed without authorization. The OAG reviewed which data may have been involved and learned that certain personal information was contained in some files," [said](https://www.prnewswire.com/news-releases/media-notice-pennsylvania-office-of-attorney-general-provides-notice-of-data-incident-302615934.html) the Pennsylvania Office of the Attorney General (OAG) in a Friday press release.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"Based on the OAG's review of the data involved, for some individuals the information involved may have included name, Social Security number, and/or medical information."

On August 9th, when the breach was discovered, the threat actors [took down systems](https://www.bleepingcomputer.com/news/security/pennsylvania-attorney-generals-email-site-down-after-cyberattack/) and services on Pennsylvania OAG's network, including the office's website, employees' email accounts, and landline phone lines, in an attack with widespread and crippling impact.

While the Pennsylvania OAG has yet to share more information on how the network was breached, [cybersecurity expert Kevin Beaumont found](https://cyberplace.social/@GossiTheDog/114852498783201767) that the Pennsylvania AG's network had several public-facing Citrix NetScaler appliances vulnerable to ongoing attacks exploiting a critical vulnerability (CVE-2025-5777) known as [Citrix Bleed 2](https://www.bleepingcomputer.com/tag/citrixbleed2/).

According to Beaumont, one of the two devices [was taken down since July 29th](https://beta.shodan.io/host/207.218.103.19), while the other [has been offline since August 7th](https://beta.shodan.io/host/207.218.103.174).

## Breach claimed by INC Ransom

Although the Pennsylvania OAG didn't publicly attribute the breach to a specific ransomware operation, the INC Ransom gang claimed responsibility for the attack on September 20th, when they added it as a new entry on their dark web leak site.

At the time, the ransomware group claimed that they had stolen 5.7TB worth of files from the Pennsylvania OAG's network and said that the breach allegedly provided them with access to an FBI internal network.

![Pennsylvania OAG entry on INC Ransom website](https://www.bleepstatic.com/images/news/u/1109292/2025/Pennsylvania%20OAG%20entry%20on%20INC%20Ransom%20website.png)

_Pennsylvania OAG claimed by INC Ransom (BleepingComputer)_

​​INC Ransom surfaced as a ransomware-as-a-service (RaaS) operation in July 2023 and has since targeted organizations in the private and public sectors worldwide.

Its list of victims spans a wide range of sectors, from education and healthcare to government and entities like [Yamaha Motor Philippines](https://www.bleepingcomputer.com/news/security/yamaha-motor-confirms-ransomware-attack-on-philippines-subsidiary/), Scotland's [National Health Service](https://www.bleepingcomputer.com/news/security/inc-ransom-threatens-to-leak-3tb-of-nhs-scotland-stolen-data/) (NHS), food retail giant [Ahold Delhaize](https://www.bleepingcomputer.com/news/security/ahold-delhaize-confirms-data-theft-after-inc-ransomware-claims-attack/), and the U.S. division of [Xerox Business Solutions](https://www.bleepingcomputer.com/news/security/xerox-says-subsidiary-xbs-us-breached-after-ransomware-gang-leaks-data/) (XBS).

This is the third time that Pennsylvania state entities have been breached in a ransomware attack: [Delaware County](https://www.bleepingcomputer.com/news/security/pennsylvania-county-pays-500k-ransom-to-doppelpaymer-ransomware/) paid a $500,000 ransom following a DoppelPaymer attack in 2020 to recover encrypted systems, and a ransomware attack took down the [Pennsylvania Senate Democratic Caucus](https://www.bleepingcomputer.com/news/government/ransomware-hits-pennsylvania-senate-democrats/)' network in 2017.