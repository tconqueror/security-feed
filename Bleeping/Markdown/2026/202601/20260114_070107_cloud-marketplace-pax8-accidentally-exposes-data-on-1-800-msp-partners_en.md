# Cloud marketplace Pax8 accidentally exposes data on 1,800 MSP partners

![Pax8](https://www.bleepstatic.com/content/hl-images/2026/01/14/pax8-background.jpg)

Cloud marketplace and distributor Pax8 has confirmed that it mistakenly sent an email to fewer than 40 UK-based partners containing a spreadsheet with internal business information, including MSP customer and Microsoft licensing data.

Pax8 is a fast-growing cloud commerce marketplace with more than 1,700 employees, over 47,000 partners worldwide, and operations in 18 countries. The company recently surpassed $2 billion in annual revenue, with particularly strong growth in Europe.

## CSV exposes customer and licensing data

The email, titled "Potential Business Premium Upgrade Tactic to Save Money," was sent on January 13 by an EMEA-based strategic account manager and included a CSV attachment.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

According to Pax8, the file contained internal pricing and Microsoft program information affecting **approximately 1,800 partners**, primarily in the UK, with one in Canada—and was accidentally distributed to fewer than 40 UK-based recipients.

MSPs who received the message told BleepingComputer that the CSV file listed customer organization names, Microsoft SKUs, license counts, and [New Commerce Experience (NCE)](https://www.pax8.com/blog/microsoft-csp-new-commerce-experience/) renewal dates.

![Pax8 email sent to MSPs containing the spreadsheet](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/pax8-data-leak/pax8-original-email-with-csv-redacted.jpg)

**Pax8 email sent to MSPs containing the spreadsheet with customer data** (BleepingComputer)

Artifacts shared with BleepingComputer directly by multiple recipients reveal that the leaked spreadsheet contained more than 56,000 entries with fields such as:

* Partner Name and ID
* Customer Name and ID
* Vendor Name and Product Name
* Gross & Net Bookings
* Currency Total Quantity
* Territory
* Account Owner
* Provision Date
* Cancelled Book Date
* Postal Code
* Transaction Type
* Commitment Term End Date

Shortly after the email was sent, the sender attempted to recall the message and later followed up with another email asking recipients to delete the original message and attachment, acknowledging it had been sent in error:

**Pax8 recalling the accidental email** (BleepingComputer)

In the follow-up notice, Pax8 told partners that the file did not contain personally identifiable information but limited business information that [may reveal](http://status.pax8.com/incidents/ndmn6zrpnxjp) MSP pricing and Microsoft program management data. Such information, including customer portfolios and licensing footprints, would normally be visible only to the MSP managing those tenants and Pax8 itself.

Multiple recipients shared the wording from Pax8's follow up with BleepingComputer:

"Dear Partner,  
  
Earlier today, 13 January 2026, a Pax8 employee mistakenly sent an email with an attached spreadsheet to fewer than 40 UK-based partners. The attachment did not contain personally identifiable information. However, the file included limited internal business information reflective of your Pax8 pricing and some Microsoft program management.  
  
Importantly, there is no impact to Marketplace availability or security controls as a result of this incident.  
  
**What we did immediately**  
  
\* Contacted each recipient directly and requested deletion of the email and attachment  
\* Required confirmation of deletion and non-forwarding  
\* Are conducting 1:1 follow-up calls with recipients to reinforce deletion and confirm completion  
\* Launched an internal review to determine how this occurred and to prevent recurrence  
  
**What you need to do**  
  
No action is required from you.  
If you have questions, please reach out to us at trust@pax8.com.  
  
We recognize the responsibility we have to protect partner-confidential information.  
  
Sincerely,  
Pax8 Alerts"

## Threat actors reportedly seeking the dataset

BleepingComputer has also learned from industry sources that threat actors are now approaching some affected MSPs, offering to buy copies of the exposed dataset.

Such information could be valuable both to competitors and cybercriminals. For rival MSPs, the list could reveal which organizations use Pax8 as their distributor, the size of each customer's Microsoft environment, contract renewal timelines, and potentially the pricing tiers being paid—data that could be used for competitive targeting or poaching.

For threat actors, the dataset could function as a high-quality targeting list, identifying organizations running specific Microsoft products, the scale of their deployments, and which MSP manages their environment. This could enable more convincing phishing campaigns, business email compromise attempts, or extortion efforts timed around license renewals and contract negotiations.

BleepingComputer approached Pax8's media team for comment prior to publication, but messages to the listed press address repeatedly bounced. We also reached out to members of the communications team, the support desk, the trust@pax8.com inbox, and personnel familiar with the incident for additional comment.