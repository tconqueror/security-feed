# Hackers abuse OAuth 2.0 workflows to hijack Microsoft 365 accounts

![Hackers abuse OAuth 2.0 workflows to hijack Microsoft 365 accounts](https://www.bleepstatic.com/content/hl-images/2023/10/06/Microsoft_365.jpg)

Russian threat actors have been abusing legitimate OAuth 2.0 authentication workflows to hijack Microsoft 365 accounts of employees of organizations related to Ukraine and human rights.

The adversary is impersonating officials from European countries and contact targets through WhatsApp and Signal messaging platforms. The purpose is to convince potential victims to provide Microsoft authorization codes that give access to accounts, or to click on malicious links that collect logins and one-time access codes.

Cybersecurity company Volexity observed this activity since early March, right after a similar operation, reported in February by [Volexity](https://www.volexity.com/blog/2025/02/13/multiple-russian-threat-actors-targeting-microsoft-device-code-authentication/) and [Microsoft](https://www.bleepingcomputer.com/news/security/microsoft-hackers-steal-emails-in-device-code-phishing-attacks/), that used Device Code Authentication phishing to steal Microsoft 365 accounts.

Volexity tracks the threat actors responsible for the two campaigns as UTA0352 and UTA0355 and assesses with medium confidence that they are both Russian.

## Attack flow

In a report published today, the researchers describe the attack as starting with a message over Signal or WhatsApp. Volexity notes that in one case the communication came from a compromised Ukrainian government account.

![Email sent to targets](https://www.bleepstatic.com/images/news/u/1220909/2025/April/email.jpg)

**Email sent to targets**  
_Source: Volexity_

The attacker impersonates European political officials or Ukrainian diplomats and lures targets with invitations to private video meetings to discuss Ukraine-related affairs.

Once the communication channel established, the attacker sends an OAuth phishing URL under the pretext that it is required for joining the video call.

![Messages sent to targets](https://www.bleepstatic.com/images/news/u/1220909/2025/April/messages.jpg)

**Messages sent to targets**  
_Source: Volexity_

UTA0352 may share instructions to join the meeting in the form of a PDF file along with a malicious URL crafted to log the user into Microsoft and third-party apps that use Microsoft 365 OAuth workflows.

After the target authenticates, they are "redirected to an in-browser version of Visual Studio Code, hosted at insiders.vscode.dev," the researchers explain.

The landing page can receive login parameters from Microsoft 365, which includes OAuth and the target will see the dialog below:

**Landing page providing the OAuth 2.0 authorization code**  
_Source: Volexity_

Using social engineering, the attacker tries to trick the victim to send back the code above, under the pretense that it is needed to join the meeting.

However, the string is an authorization code valid for 60 days that can be used to obtain an access token for "all resources normally available to the user."

"It should be noted that this code also appeared as part of the URI in the address bar. The Visual Studio Code appears to have been set up to make it easier to extract and share this code, whereas most other instances would simply lead to blank pages," [Volexity](https://www.volexity.com/blog/2025/04/22/phishing-for-codes-russian-threat-actors-target-microsoft-365-oauth-workflows/)[ says](http://www.volexity.com/blog/2025/04/22/phishing-for-codes-russian-threat-actors-target-microsoft-365-oauth-workflows/).

The researchers simplified in the following diagram the attack flow targeting users by relying on a Visual Studio Code first-party application:

**Complete attack flow**  
_Source: Volexity_

The research note that there are older variations of the recent phishing attack, where the attacker used a format for the AzureAD v1.0 instead of the v2.0, the differences consisting in the URL parameters used.

The campaign in April attributed to UTA0355 is similar to that of UTA0352 but the initial communication came from a compromised Ukrainian government email account and the attacker used the "stolen OAuth authorization code to register a new device to the victim’s Microsoft Entra ID (formerly Azure Active Directory)."

Volexity researchers say that once the device registered, they had to convince the target to approve the two-factor authentication (2FA) request to be able to access the victim's email.

To achieve that, the threat actor social-engineered their way by saying that the 2FA code was necessary to "gain access to a SharePoint instance associated with the conference."

This final step gives the attacker a token to access the victim’s information and emails, but also a newly registered device to maintain unauthorized access for a longer period.

“In logs reviewed by Volexity, initial device registration was successful shortly after interacting with the attacker. Access to email data occurring the following day, which was when UTA0355 had engineered a situation where their 2FA request would be approved,” Volexity researchers say.

To protect against such attacks, Volexity advises setting up alerts on logins using the Visual Studio Code _client\_id_, block access to ‘_insiders.vscode.dev_’ and ‘_vscode-redirect.azurewebsites.net_’.

The researchers also recommend setting up conditional access policies to limit access to approved devices only.