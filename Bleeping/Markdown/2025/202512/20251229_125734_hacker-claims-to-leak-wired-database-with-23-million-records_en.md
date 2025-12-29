# Hacker claims to leak WIRED database with 2.3 million records

![Hand sifting through leaked data](https://www.bleepstatic.com/content/hl-images/2022/10/28/hand-sifting-data.jpg)

A hacker claims to have breached Condé Nast and leaked an alleged WIRED database containing more than 2.3 million subscriber records, while also warning that they plan to release up to 40 million additional records for other Condé Nast properties.

On December 20, a threat actor using the name "Lovely" leaked the database on a hacking forum, offering access for approximately $2.30 in the site's credits system. In the post, Lovely accused Condé Nast of ignoring vulnerability reports and claimed the company failed to take security seriously.

"Condé Nast does not care about the security of their users' data. It took us an entire month to convince them to fix the vulnerabilities on their websites," reads a post on a hacking forum.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

"We will leak more of their users' data (40+ million) over the next few weeks. Enjoy!"

![Forum post leaking WIRED data on a hacking forum](https://www.bleepstatic.com/images/news/security/d/data-breaches/w/wired/lovely-post.jpg)

**Forum post leaking WIRED data on a hacking forum**  
_Source: BleepingComputer_

The same person later leaked the data on other hacking forums, where users also had to spend forum credits to reveal the password to the archive containing the data.

Lovely also shared record counts for other Condé Nast properties they claim to have stolen data, including, based on the abbreviations used, The New Yorker, Epicurious, SELF, Vogue, Allure, Vanity Fair, Glamour, Men's Journal, Architectural Digest, Golf Digest, Teen Vogue, Style.com, and Condé Nast Traveler.

While Condé Nast has not yet confirmed it was breached, BleepingComputer analyzed the leaked database and was able to validate twenty of the records as legitimate WIRED subscribers.

The dataset contains 2,366,576 total records and 2,366,574 unique email addresses, with timestamps ranging from April 26, 1996, to September 9, 2025.

Each record includes a subscriber's unique internal ID, an email address, and optional data, such as first and last name, phone number, physical address, gender, and birthday. Many of these fields are empty.

The records also include account creation and update timestamps, last session information, and WIRED-specific fields such as a display username and WIRED account creation and update dates. 

**Example record from leaked data**  
_Source: BleepingComputer_

While many of the records fields are empty, some include additional personal details.

Approximately 284,196 records (12.01%) include both a first and last name, 194,361 records (8.21%) include a physical address, 67,223 records (2.84%) include a birthday, and 32,438 records (1.37%) include a phone number.

A much smaller subset includes more complete profiles, with 1,529 records (0.06%) containing a full name, birthday, phone number, address, and gender.

Alon Gal, co-founder and CTO of Hudson Rock, also verified the records using infostealer logs containing previously compromised credentials.

"Our researchers identified legitimate subscriber credentials for wired.com within global infostealer infection logs," reads an article on [Infostealers.com](https://www.infostealers.com/article/wired-database-leaked-40-million-record-threat-looms-for-conde-nast/).

"By matching these compromised credentials against the records in the leaked database, we have definitively confirmed the authenticity of the dataset without any interaction with the victim organization."

The leaked database has since been added to [Have I Been Pwned](https://haveibeenpwned.com/), allowing users to check whether their email addresses were exposed by the data leak.

## Claiming to be a security researcher

Before the leak, Lovely reportedly claimed to be a security researcher who contacted Dissent Doe of DataBreaches.net for help in responsibly disclosing vulnerabilities to Condé Nast.

According to [DataBreaches.net](https://databreaches.net/2025/12/25/conde-nast-gets-hacked-and-databreaches-gets-played-christmas-lump-of-coal-edition/), the individual contacted them in late November seeking help reaching Condé Nast's security team regarding vulnerabilities that allegedly allowed attackers to view and modify user account information.

The person initially said they had downloaded only a small number of records to provide proof to Condé Nast, including records verified as belonging to DataBreaches.net and a WIRED employee.

However, after receiving no response from Condé Nast, the person later told Dissent Doe they had downloaded the entire database and were threatening to leak it.

Dissent Doe concluded that she had been misled and described the incident as a case where they had been played by a threat actor who downloaded and leaked stolen data rather than pursuing responsible disclosure. 

"As for 'Lovely,' they played me. Condé Nast should never pay them a dime, and no one else should ever, as their word clearly cannot be trusted," admitted DataBreaches.net.

BleepingComputer contacted Condé Nast with questions about the incident, but has not received a response at this time.