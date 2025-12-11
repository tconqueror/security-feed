# New ConsentFix attack hijacks Microsoft accounts via Azure CLI

![Microsoft](https://www.bleepstatic.com/content/hl-images/2024/01/26/microsoft-red-header.jpg)

A new variation of the ClickFix attack dubbed 'ConsentFix' abuses the Azure CLI OAuth app to hijack Microsoft accounts without the need for a password or to bypass multi-factor authentication (MFA) verifications.

A [ClickFix attack](https://www.bleepingcomputer.com/tag/clickfix/) is a social engineering technique that attempts to trick users into running commands on their computer to install malware or steal data. They commonly use fake instructions that pretend to fix an error or verify that they are human and not a bot.

This new ConsentFix variant was discovered by cybersecurity firm Push Security, which explains that the ConsentFix technique steals OAuth 2.0 authorization codes that can be used to obtain an [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/?view=azure-cli-latest) access token.

Azure CLI is a Microsoft command-line application that uses an OAuth flow to let users authenticate and manage Azure and Microsoft 365 resources from their local machine. In this campaign, attackers trick victims into completing that Azure CLI OAuth flow and then steal the resulting authorization code, which they exchange for full account access without needing the user's password or MFA.

## The ConsentFix attack

A ConsentFix attack starts with the victim landing on a compromised, legitimate website that ranks high on Google Search results for specific terms.

The visitor is shown a fake Cloudflare Turnstile CAPTCHA widget that asks for a valid business email address. The attacker's script checks this address against a list of intended targets, filtering out bots, analysts, and anyone else not on the target list.

![Victim prompted to enter their email address](https://www.bleepstatic.com/images/news/u/1220909/2025/December/entermeial.jpg)

**Victim prompted to enter their email address**  
_Source: Push Security_

Users who pass this check are shown a page that resembles ClickFix interaction patterns, providing the victim with instructions to verify they are human.

These instructions are to click the 'Sign in' button on the page, which opens a legitimate Microsoft URL in a new tab. 

![The ClickFix-styled page that steals the URL with the code](https://www.bleepstatic.com/images/news/u/1220909/2025/December/verifyurl.jpg)

**The ClickFix-styled page that steals the URL with the code**  
_Source: Push Security_

However, this is not your typical Microsoft login prompt, but rather an Azure login page used to generate an Azure CLI OAuth access code.

**Microsoft Azure CLI login page**  
_Source: BleepingComputer_

If the user is already logged into the Microsoft account, they only need to select their account; otherwise, they authenticate normally on Microsoft's real login page.

Once this happens, Microsoft redirects them to a localhost page, and the browser address bar now displays a URL containing an Azure CLI OAuth authorization code tied to the user's account.

The phishing process completes when the user pastes the URL into the malicious page, as per the provided instructions, granting the attacker access to the Microsoft account via the Azure CLI OAuth app.

"Once the steps are completed, the victim has effectively granted the attacker access to their Microsoft account via Azure CLI," [explains Push](http://pushsecurity.com/blog/consentfix).

"At this point, the attacker has effective control of the victim's Microsoft account, but without ever needing to phish a password or pass an MFA check."

"In fact, if the user was already logged in to their Microsoft account (i.e., they had an active session), no login is required at all."

Push says the attack triggers only once per victim IP address, so even if valid targets return to the same phishing page, they will not get the Cloudflare Turnstile check.

The researchers suggest that defenders look for unusual Azure CLI login activity, such as logins from new IP addresses, and monitor for legacy Graph scopes, which attackers intentionally leverage to evade detection.