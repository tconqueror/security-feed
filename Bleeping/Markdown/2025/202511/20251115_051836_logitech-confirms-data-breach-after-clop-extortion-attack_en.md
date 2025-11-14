# Logitech confirms data breach after Clop extortion attack

![Logitech](https://www.bleepstatic.com/content/hl-images/2025/11/14/logitech.jpg)

Hardware accessory giant Logitech has confirmed it suffered a data breach in a cyberattack claimed by the Clop extortion gang, which conducted Oracle E-Business Suite data theft attacks in July.

Logitech International S.A. is a Swiss multinational electronics company that sells hardware and software solutions, including computer peripherals, gaming, video collaboration, music, and smart home products.

Today, Logitech filed a [Form 8-K ](https://www.sec.gov/Archives/edgar/data/1032975/000103297525000085/logi-20251114.htm)with the U.S. Securities and Exchange Commission, confirming that data was stolen in a breach.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Logitech International S.A. ("Logitech") recently experienced a cybersecurity incident relating to the exfiltration of data. The cybersecurity incident has not impacted Logitech's products, business operations or manufacturing," disclosed Logitech.

"Upon detecting the incident, Logitech promptly took steps to investigate and respond to the incident with the assistance of leading external cybersecurity firms."

Logitech says the data likely includes limited information about employees and consumers, as well as data relating to customers and suppliers, but the company does not believe hackers gained access to sensitive information such as national ID numbers or credit card information, as that data was not stored in the breached systems.

Logitech says that the breach occurred through a third-party zero-day vulnerability that was patched as soon as a fix was available.

This statement comes after the Clop extortion gang added Logitech to its data-leak extortion site last week, leaking almost 1.8 TB of data allegedly stolen from the company.

While the company does not name the software vendor, the breach was likely caused by an Oracle zero-day vulnerability exploited by the Clop extortion gang in July data-theft attacks.

Last month, Mandiant and Google began tracking a [new extortion campaign](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/) in which numerous companies received emails from the Clop ransomware operation claiming that sensitive data had been stolen from their Oracle E-Business Suite systems. 

These emails warned that the stolen data would be leaked if a ransom demand was not paid.

![Clop extortion email sent to Oracle customers](https://www.bleepstatic.com/images/news/security/c/clop/oracle-e-business-suite-extortion/clop-oracle-extortion-email.jpg)

**Clop extortion email sent to Oracle customers**

Soon after, [Oracle confirmed a new E-Business Suite zero-day](https://www.bleepingcomputer.com/news/security/oracle-patches-ebs-zero-day-exploited-in-clop-data-theft-attacks/), tracked as CVE-2025-61882, and issued an emergency update to fix the flaw.

The Clop extortion gang has a [long history of exploiting zero-day flaws](https://www.bleepingcomputer.com/tag/clop/) in massive data theft attacks, including:

* **2020:** Exploited a [zero-day in the Accellion FTA platform](https://www.bleepingcomputer.com/tag/accellion/), affecting nearly 100 organizations.
* **2021:** Exploited a [zero-day in SolarWinds Serv-U FTP](https://www.bleepingcomputer.com/news/security/clop-gang-exploiting-solarwinds-serv-u-flaw-in-ransomware-attacks/) software.
* **2023:** Exploited a [zero-day in the GoAnywhere MFT platform](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), breaching over 100 companies.
* **2023:** Exploited a [zero-day in MOVEit Transfer](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-moveit-extortion-attacks/), which was Clop's most extensive campaign to date, where the attackers [stole data from 2,773 organizations worldwide](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).
* **2024:** Exploited [two Cleo file transfer zero-days (CVE-2024-50623 and CVE-2024-55956)](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-cleo-data-theft-attacks/) to steal data and extort companies.

Other organizations impacted by the 2025 Oracle E-Business Suite data theft attacks include [Harvard](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/), [Envoy Air](https://www.bleepingcomputer.com/news/security/american-airlines-subsidiary-envoy-confirms-oracle-data-theft-attack/), and [The Washington Post](https://www.bleepingcomputer.com/news/security/washington-post-data-breach-impacts-nearly-10k-employees-contractors/).

BleepingComputer contacted Logitech earlier this month and again today with questions regarding the breach and will update the story if we receive a response.