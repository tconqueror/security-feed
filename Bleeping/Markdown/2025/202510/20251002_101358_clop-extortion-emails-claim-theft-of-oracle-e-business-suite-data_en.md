# Clop extortion emails claim theft of Oracle E-Business Suite data

![Hand sifting data](https://www.bleepstatic.com/content/hl-images/2024/08/16/data-leak.jpg)

Mandiant and Google are tracking a new extortion campaign where executives at multiple companies received emails claiming that sensitive data was stolen from their Oracle E-Business Suite systems

According to Genevieve Stark, Head of Cybercrime and Information Operations Intelligence Analysis at GTIG, the campaign began in late September.

"This activity began on or before September 29, 2025, but Mandiant's experts are still in the early stages of multiple investigations, and have not yet substantiated the claims made by this group," Stark said.

Charles Carmakal, CTO of Mandiant – Google Cloud, stated that the extortion emails are being sent from a large number of compromised email accounts.

"We are currently observing a high-volume email campaign being launched from hundreds of compromised accounts and our initial analysis confirms that at least one of these accounts has been previously associated with activity from FIN11, a long-running financially motivated threat group known for deploying ransomware and engaging in extortion," Carmakal explained.

Mandiant and GTIG report that the emails contain contact addresses known to be listed on the Clop ransomware gang's data leak site, indicating a possible link to the extortion group.

However, Carmakal says that while the tactics are similar to Clop's previous extortion campaigns and the email addresses indicate a potential link, there is not enough evidence to determine if data has actually been stolen.

Mandiant and GTIG recommend that organizations receiving these emails investigate their environments for unusual access or compromise in their Oracle E-Business Suite platforms.

BleepingComputer contacted the Clop ransomware gang to confirm if they are behind the extortion emails, but has not received a response at this time.

We have also contacted Oracle to determine if they are aware of any recent zero-day exploitation that may have led to the theft of data.

If you have any information regarding this incident or any other undisclosed attacks, you can contact us confidentially via Signal at 646-961-3731 or at tips@bleepingcomputer.com.

## Who is the Clop extortion gang?

The Clop ransomware operation, also tracked as TA505, Cl0p, and FIN11, launched in March 2019 when it began targeting enterprise networks with a variant of the CryptoMix ransomware.

Like other ransomware gangs, Clop members breach corporate networks, steal data, and then deploy ransomware to encrypt systems.

The stolen data and encrypted files are then used as leverage to force companies to pay a ransom demand in exchange for a decryptor and to prevent the leaking of the stolen data.

While the group is still known to deploy ransomware, since 2020, they have shifted to exploiting zero-day vulnerabilities in secure file transfer platforms to steal data.

Some of their most notable attacks include:

* **2020:** [Exploiting a zero-day in the Accellion FTA platform](https://www.bleepingcomputer.com/tag/accellion/), affecting nearly 100 organizations.
* **2021:** [Exploiting a zero-day in SolarWinds Serv-U FTP](https://www.bleepingcomputer.com/news/security/clop-gang-exploiting-solarwinds-serv-u-flaw-in-ransomware-attacks/) software.
* **2023:** Exploiting a [zero-day in the GoAnywhere MFT platform](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), breaching over 100 companies.
* **[2023 MOVEit Transfer attack](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-moveit-extortion-attacks/):** The threat actor's most extensive campaign to date, where a zero-day exploit allowed [data theft from 2,773 organizations worldwide](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).

The most recent campaign associated with Clop was in October 2024, when the threat actors [exploited two Cleo file transfer zero-days](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-cleo-data-theft-attacks/) (CVE-2024-50623 and CVE-2024-55956) to steal data and extort companies.

The U.S. State Department currently offers a [$10 million reward](https://www.bleepingcomputer.com/news/security/us-govt-offers-10-million-bounty-for-info-on-clop-ransomware/) through its Rewards for Justice program for information linking Clop's ransomware activities to a foreign government.