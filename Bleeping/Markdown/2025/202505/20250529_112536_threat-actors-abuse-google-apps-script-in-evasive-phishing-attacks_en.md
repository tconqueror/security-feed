# Threat actors abuse Google Apps Script in evasive phishing attacks

![Threat actors abuse Google Apps Script in evasive phishing attacks](https://www.bleepstatic.com/content/hl-images/2024/03/25/phishing.jpg)

Threat actors are abusing the ‘Google Apps Script’ development platform to host phishing pages that appear legitimate and steal login credentials.

This new trend was spotted by security researchers at Cofense, who warn that the fraudulent login window is "carefully designed to look like a legitimate login screen."

“The attack uses an email masquerading as an invoice, containing a link to a webpage that uses Google Apps Script, a development platform integrated across Google’s suite of products,” [Cofense explains](https://cofense.com/blog/behind-the-script-unmasking-phishing-attacks-using-google-apps-script).

“By hosting the phishing page within Google’s trusted environment, attackers create an illusion of authenticity. This makes it easier to trick recipients into handing over sensitive information.”

### Legitimate service abuse

Google Apps Script is a JavaScript-based cloud scripting platform from Google that allows users to automate tasks and extend the functionality of Google Workspace products like Google Sheets, Docs, Drive, Gmail, and Calendar.

These scripts run on a trusted Google domain under “script.google.com,” which is on the allowlist of most security products.

Attackers write a Google Apps Script that displays a fake login page to capture the credentials victims enter. The data is exfiltrated to the attacker’s server via a hidden request.

![Phishing page hosted on Google infrastructure](https://www.bleepstatic.com/images/news/u/1220909/2025/May/phishing-page.jpg)

**Phishing page hosted on Google infrastructure**  
_Source: Cofense_

As the platform allows anyone with an account to publish a script as a public web app, giving it a Google domain, the threat actors can easily share it with the victims via a phishing email that won’t trigger any warnings.

The phishing email contains an invoice payment or tax-related call to action for the recipient, linking to the malicious Google-hosted phishing page.

![Sample of a phishing email used in the attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/May/email(1).jpg)

**Sample of a phishing email used in the attacks**  
_Source: Cofense_

After the victim enters their username and password, they are redirected to the legitimate service that was spoofed to lower suspicion and give threat actors time to exploit the stolen data.

Google Apps Script appears to be the new focus of phishing actors that look for legitimate platforms to abuse for evasion and operational efficiency.

In this case, it also gives the attackers the flexibility to remotely adjust their script without having to resend a new link, switching to a different lure without much effort.

An effective defense measure would be to configure email security to scrutinize cloud service links and, if possible, block access to Google Apps Script URLs altogether, or at least flag them as potentially dangerous.

BleepingComputer has contacted Google to ask if they plan to implement any anti-abuse measures in response to Cofense’s findings, but we have not heard back as of publication.