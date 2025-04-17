# CTM360 Tracks Global Surge in SMS-Based Reward and Toll Scams

![CTM360 report](https://www.bleepstatic.com/content/posts/2025/04/16/ctm360-header.jpg)

[CTM360](http://www.ctm360.com) has observed a notable surge in two SMS-based phishing campaigns: PointyPhish (reward scams) and TollShark (toll payment scams).

PointyPhish is linked to over 3,000 domains and phishing sites, preying on urgency by claiming expiring reward points to trick customers into fraudulent sites that steal payment details

Similarly, TollShark involves over 2,000 domains and phishing sites, exploiting fears of unpaid tolls to capture sensitive information from unsuspecting individuals.  

CTM360 detected thousands of these phishing sites across multiple countries, indicating that this isn’t just a localized issue — it’s a coordinated, global effort. The widespread nature of these attacks shows a clear intent to target individuals at scale, with the goal of stealing sensitive financial data.

The impact is far-reaching, affecting not just one region but thousands of customers of various brands worldwide.

At the core of these campaigns is Darcula Suite, a powerful Phishing-as-a-Service (PhaaS) platform. Built on React and Docker, Darcula enables cybercriminals to launch phishing sites in under 10 minutes.

It supports multi-channel SMS delivery (including iMessage and RCS), making the websites harder to detect and easier to scale globally.

## **Two Different Campaigns, One Common Tactic**

1. **PointyPhish –** Sends fake SMS alerts about expiring reward points to banking, airline, and retail store customers, leading to phishing pages that steal full credit/debit card details.
1. **TollShark –** Poses as road toll authorities, warning of unpaid bills and fines. Victims are directed to fake payment pages that collect personal and financial data.

Both attacks are simple in structure: they begin with SMS distribution, create urgency, impersonate a trusted brand, and lead customers into giving up payment details.

![Toll Shark phishing texts](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/ctm360-phishing.jpg)

## [Read our new PlayPraetor report to explore behaviors, detection insights](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

CTM360 has now identified a much larger extent of the ongoing PlayPraetor campaign.

What started with 6,000+ URLs linked to a specific banking attack has now grown to 16,000+ impersonation sites across multiple malware variants. This research is ongoing, with further discoveries expected in the coming days.

[Read the Report](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

## How It Works – Step by Step

![Scam stages](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/scam-stages.png)

CTM360’s threat analysts mapped out the entire attack lifecycle using the CTM360 Scam Navigator and analyzed each step in detail.

1. **SMS distribution:**  
 Messages create urgency, either a toll is unpaid, or points are about to expire.
2. **Fake landing pages:**  
 Victims are redirected to phishing sites mimicking real brands.
3. **Engagement & bait:**  
 Victims are asked to redeem points or pay tolls to avoid penalties.
4. **Data collection:**  
 Personal data is harvested under the guise of verification.
5. **Payment data theft:**  
 Victims are tricked into entering card info, which is logged instantly.

## Inside Darcula: A Glimpse Into PhaaS

Darcula isn’t just a phishing kit — it’s a full PhaaS platform for scams. While tracking these campaigns, CTM360 uncovered an exposed admin panel used by attackers managing Darcula Suite.

This offers a rare window into how these phishing operations are run:

* **Centralized campaign management:** Multiple attacker accounts running parallel campaigns.
* **Live victim logging:** IP addresses, device info, user agents, and form data are captured in real-time.
* **Subscription-based access:** Attackers operate on a tiered model with account-based controls.
* **SMS configuration tools:** Built-in tools to manage target regions and message templates.

## Read the full PointyPhish & TollShark Report

For a deeper look into the campaigns. including screenshots, domain samples and insights into how the scams are structured and operate on a global scale, read the full report at **<https://www.ctm360.com/reports/pointyphish-tollshark>**.

_Sponsored and written by [CTM360](https://www.ctm360.com?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=article&utm%5Fcampaign=ctm360%5Fbleepingcomputer)._