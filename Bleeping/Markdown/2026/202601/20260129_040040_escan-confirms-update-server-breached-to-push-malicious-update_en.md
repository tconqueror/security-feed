# eScan confirms update server breached to push malicious update

![Hacker shhing](https://www.bleepstatic.com/content/hl-images/2021/12/28/hacker.jpg)

MicroWorld Technologies, the maker of the eScan antivirus product, has confirmed that one of its update servers was breached and used to distribute an unauthorized update later analyzed as malicious to a small subset of customers earlier this month.

The file was delivered to customers who downloaded updates from the regional update cluster during a two-hour window on January 20, 2026.

eScan says the affected infrastructure has since been isolated and rebuilt, authentication credentials have been rotated, and remediation has been made available to impacted customers.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Security firm Morphisec separately published a technical report analyzing malicious activity observed on customer endpoints, which it associates with updates delivered from eScan's update infrastructure during the same timeframe.

Morphisec states that it detected malicious activity on January 20, 2026, and later contacted eScan. MicroWorld Technologies told BleepingComputer it disputes Morphisec's claims that it was the first to discover or report the incident.

According to eScan, the company detected the issue internally on January 20 through monitoring and customer reports, isolated the affected infrastructure within hours, and issued a security advisory on January 21\. eScan says Morphisec contacted the company later, after publishing public claims about the incident.

eScan also disputes claims that affected customers were unaware of the issue, stating that it conducted proactive notifications and direct outreach to impacted customers while remediation was being finalized.

## Update infrastructure breached

In its advisory, eScan classified the incident as an update infrastructure access incident, stating that unauthorized access to a regional update server configuration allowed an unauthorized file to be placed in the update distribution path.

"Unauthorized access to one of our regional update server configurations resulted in an incorrect file (patch configuration binary/corrupt update) being placed in the update distribution path," reads an advisory shared with BleepingComputer by MicroWorld Technologies.

"This file was distributed to customers downloading updates from the affected server cluster during a limited timeframe on January 20, 2026."

The company emphasized that the incident did not involve a vulnerability in the eScan product itself.

eScan stressed that only those whose software was updated from the specific regional cluster were impacted, while all other customers remained unaffected.

However, eScan says that those who installed the malicious update may have seen this behavior on their systems:

* Update service failure notifications
* Modified system hosts file preventing connection to eScan update servers
* eScan update configuration file modifications
* Inability to receive new security definition updates
* Update unavailability popup on client machines

BleepingComputer contacted eScan with further questions on when its systems were initially breached and will update the story if we receive a reply back.

## Update deployed to push malware

Morphisec's [security bulletin](https://www.morphisec.com/blog/critial-escan-threat-bulletin/) says that the malicious update pushed down a modified version of an eScan update component, "Reload.exe".

"Malicious updates were distributed through eScan's legitimate update infrastructure, resulting in the deployment of multi-stage malware to enterprise and consumer endpoints globally," reads Morphisec's bulletin.

While the modified Reload.exe is signed with what appears to be eScan's code-signing certificate, both Windows and VirusTotal show the signature as invalid.

According to Morphisec, the Reload.exe file \[[VirusTotal](https://www.virustotal.com/gui/file/8f2fe9dc184ba209f78d1b81f87f7d39f0d260b8d6dc1f7af9f256071d8c9fe0)\] was used to enable persistence, execute commands, modify the Windows HOSTS file to prevent remote updates, and connect to the C2 infrastructure to download further payloads.

The researchers say the following command and control servers were observed:

```
hxxps[://]vhs[.]delrosal[.]net/i
hxxps[://]tumama[.]hns[.]to
hxxps[://]blackice[.]sol-domain[.]org
hxxps[://]codegiant[.]io/dd/dd/dd[.]git/download/main/middleware[.]ts
504e1a42.host.njalla[.]net
185.241.208[.]115

```

The final payload seen deployed was a file named CONSCTLX.exe \[[VirusTotal](https://www.virustotal.com/gui/file/bec369597633eac7cc27a698288e4ae8d12bdd9b01946e73a28e1423b17252b1/content)\], which Morphisec acts as a backdoor and a persistent downloader. Morphisec says that the malicious files created scheduled tasks for persistence using names like "CorelDefrag".

eScan has created a remediation update that customers can run to perform the following actions:

* Automatically identifies and corrects incorrect modifications
* Re-enables proper eScan update functionality
* Verifies successful restoration
* Requires standard system restart

Both eScan and Morphisec recommend that customers block the above command and control servers for additional security.

In 2024, North Korean hackers were observed [exploiting the updating mechanism](https://www.bleepingcomputer.com/news/security/hackers-hijack-antivirus-updates-to-drop-guptiminer-malware/) of eScan antivirus to plant backdoors on corporate networks.