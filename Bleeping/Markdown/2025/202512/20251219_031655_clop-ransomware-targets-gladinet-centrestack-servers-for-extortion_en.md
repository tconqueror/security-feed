# Clop ransomware targets Gladinet CentreStack servers for extortion

![Hacker](https://www.bleepstatic.com/content/hl-images/2024/08/28/hacker.jpg)

The Clop ransomware gang is targeting Internet-exposed Gladinet CentreStack file servers in a new data theft extortion campaign.

[Gladinet CentreStack](https://www.bleepingcomputer.com/tag/gladinet-centrestack/) enables businesses to securely share files hosted on on-premises file servers through web browsers, mobile apps, and mapped drives without requiring a VPN. According to Gladinet, CentreStack "is used by thousands of businesses from over 49 countries."

Since April, Gladinet has released security updates to address several other security flaws that were exploited [in attacks](https://www.bleepingcomputer.com/news/security/hackers-exploit-gladinet-centrestack-cryptographic-flaw-in-rce-attacks/), some [of them](https://www.bleepingcomputer.com/news/security/hackers-exploiting-zero-day-in-gladinet-file-sharing-software/) as [zero-days](https://www.bleepingcomputer.com/news/security/centrestack-rce-exploited-as-zero-day-to-breach-file-sharing-servers/).

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

The Clop cybercrime gang is now scanning for and breaching CentreStack servers exposed online, with Curated Intel telling BleepingComputer that ransom notes are left on compromised servers.

However, there is currently no information on the vulnerability Clop is exploiting to hack into CentreStack servers. It is unclear whether this is a zero-day flaw or a previously addressed bug that the owners of the hacked systems have yet to patch.

"Incident Responders from the Curated Intelligence community have encountered a new CLOP extortion campaign targeting Internet-facing CentreStack file servers," [warned](http://www.linkedin.com/posts/curatedintelligence%5Fpsa-incident-responders-from-the-curated-activity-7407480091133231104-C6hv/) threat intel group Curated Intelligence on Thursday.

"From recent port scan data, there appears to be at least 200+ unique IPs running the "CentreStack - Login" HTTP Title, making them potential targets of CLOP who is exploiting an unknown CVE (n-day or zero-day) in these systems."

## Clop's data theft attacks

Clop has a long history of targeting secure file transfer products. In the past, the extortion gang has been behind other data theft campaigns targeting [Accellion FTA](https://www.bleepingcomputer.com/tag/accellion/), [GoAnywhere MFT](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), [Cleo](https://www.bleepingcomputer.com/news/security/new-cleo-zero-day-rce-flaw-exploited-in-data-theft-attacks/), and [MOVEit Transfer](https://www.bleepingcomputer.com/news/security/new-moveit-transfer-zero-day-mass-exploited-in-data-theft-attacks/) file-sharing servers, the latter of which affected [over 2,770 organizations worldwide](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).

Most recently, it [exploited an Oracle EBS zero-day flaw](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) (CVE-2025-61882) to steal sensitive files from many organizations since [early August 2025](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/).

The list of Oracle customers impacted includes [Harvard University](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/), [The Washington Post](https://www.bleepingcomputer.com/news/security/washington-post-data-breach-impacts-nearly-10k-employees-contractors/), [GlobalLogic](https://www.bleepingcomputer.com/news/security/globallogic-warns-10-000-employees-of-data-theft-after-oracle-breach/), [the University of Pennsylvania](https://www.bleepingcomputer.com/news/security/university-of-pennsylvania-confirms-data-theft-after-oracle-ebs-hack/), [Logitech](https://www.bleepingcomputer.com/news/security/logitech-confirms-data-breach-after-clop-extortion-attack/), and [the American Airlines subsidiary Envoy Air](https://www.bleepingcomputer.com/news/security/american-airlines-subsidiary-envoy-confirms-oracle-data-theft-attack/).

After breaching their systems and exfiltrating sensitive documents, Clop published the stolen data on its dark web leak site and made it available for download via Torrent.

The U.S. Department of State is [offering a $10 million reward](https://www.bleepingcomputer.com/news/security/us-govt-offers-10-million-bounty-for-info-on-clop-ransomware/) for any information that could link this cybercrime gang's attacks to a foreign government.

A Gladinet spokesperson was not immediately available for comment when contacted by BleepingComputer earlier today