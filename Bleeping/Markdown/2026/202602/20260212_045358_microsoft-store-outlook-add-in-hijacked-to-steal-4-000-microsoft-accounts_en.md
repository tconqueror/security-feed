# Microsoft Store Outlook add-in hijacked to steal 4,000 Microsoft accounts

![Microsoft Store Outlook add-in hijacked to steal 4,000 Microsoft accounts](https://www.bleepstatic.com/content/hl-images/2025/08/22/Outlook.jpg)

The AgreeTo add-in for Outlook has been hijacked and turned into a phishing kit that stole more than 4,000 Microsoft account credentials.

Originally a legitimate meeting scheduling tool for Outlook users, the module was developed by an independent publisher and has been on the Microsoft Office Add-in Store since December 2022.

Office add-ins are just URLs pointing to content loaded into Microsoft products from the developer's server. In the case of AgreeTo, the developer used a Vercel-hosted URL (outlook-one.vercel.app) but abandoned the project, despite the userbase it formed.

[![Wiz](https://www.bleepstatic.com/c/w/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=AI-Agents-101) 

However, the add-in continued to be listed on Microsoft's store, and a threat actor claimed its orphaned URL to plant a phishing kit.

![AgreeTo add-in on Microsoft Marketplace](https://www.bleepstatic.com/images/news/u/1220909/2026/February/agreeto.jpg)

**AgreeTo add-in on Microsoft Marketplace**  
_Source: Koi Security_

According to researchers at supply-chain security company Koi say that the threat actor taking over the project deployed a fake Microsoft sign-in page, a password collection page, an exfiltration script, and a redirect.

It is worth noting that once an add-in is in the Microsoft store, there is no further verification process. When submitting a module, Microsoft reviews the manifest file and signs it for approval.

AgreeTo had already been reviewed and approved, and loaded all the resources - user interface and everything the user interacts with, from the developer's server, now under the control of the threat actor.

**AgreeTo manifest**  
_Source: Koi Security_

Koi [researchers discovered](http://www.koi.ai/blog/agreetosteal-the-first-malicious-outlook-add-in-leads-to-4-000-stolen-credentials) the compromise and accessed the attacker's exfiltration channel. They found that over 4,000 Microsoft account credentials had been stolen, along with credit card numbers and banking security answers.

The add-in was present in the store until today, when Microsoft removed it. Koi researchers say that the threat actor was actively testing stolen credentials during their examination.

When users opened the malicious AgreeTo add-in in Outlook, instead of the scheduling interface, they would see a fake Microsoft login page in the program’s sidebar, which can easily be mistaken for a legitimate login prompt.

Any account credentials entered there are exfiltrated via a Telegram bot API to the attackers, while victims are then redirected to the real Microsoft login page to reduce suspicion.

**Phishing page (left) and exfiltration logic (right)**  
_Source: Koi Security_

It is noted that the add-in retained ReadWriteItem permissions, enabling it to read and modify user emails, though no such activity was confirmed.

Koi Security found that the operator behind this attack runs at least a dozen additional phishing kits targeting internet service providers, banks, and webmail providers.

While malicious add-ins aren’t new, we have previously seen such tools promoted via [spam forum comments](https://www.bleepingcomputer.com/news/security/malicious-excel-xll-add-ins-push-redline-password-stealing-malware/), [phishing emails](https://www.bleepingcomputer.com/news/security/malicious-microsoft-excel-add-ins-used-to-deliver-rat-malware/), and [malvertising](https://www.bleepingcomputer.com/news/security/fake-microsoft-office-add-in-tools-push-malware-via-sourceforge/). The case of AgreeTo stands out, though, as it is likely the first to be hosted on Microsoft’s Marketplace.

Koi Security researcher Oren Yomtov told BleepingComputer that this is the first malware found on the official Microsoft Marketplace and the first malicious Outlook add-in detected in the wild.

If you still have AgreeTo installed on Outlook, you are recommended to remove it immediately and reset your passwords. BleepingComputer has contacted Microsoft for a comment on Koi researchers’ findings, but we are still waiting for a response.