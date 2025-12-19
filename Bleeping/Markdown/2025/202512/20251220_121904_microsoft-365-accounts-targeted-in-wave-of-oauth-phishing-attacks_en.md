# Microsoft 365 accounts targeted in wave of OAuth phishing attacks

![Microsoft 365 accounts targeted in wave of OAuth phishing attacks](https://www.bleepstatic.com/content/hl-images/2025/08/04/Microsoft-365.jpg)

Multiple threat actors are compromising Microsoft 365 accounts in phishing attacks that leverage the OAuth device code authorization mechanism.

Attackers trick victims into entering a device code on Microsoft’s legitimate device login page, unknowingly authorizing an attacker-controlled application and granting them access to the target account without stealing credentials or bypassing multi-factor authentication (MFA).

Although the method isn’t new, email security firm Proofpoint says that these attacks have increased significantly in volume since September, and involve both financially motivated cybercriminals like TA2723 and state-aligned threat actors.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

"Proofpoint Threat Research has observed multiple threat clusters using device code phishing to trick users into granting a threat actor access to their Microsoft 365 account," the security company warned, adding that widespread campaigns using these attack flows are "highly unusual."

## Tools and campaigns

The attack chains that Proofpoint observed in the campaigns have slight variations, but they all involve tricking victims into entering a device code on Microsoft’s legitimate device login portals.

In some cases, the device code is presented as a one-time password, while the lure can be a token re-authorization notification in others.

The researchers observed two phishing kits used in the attacks, namely SquarePhish v1 and v2, and Graphish, which simplify the phishing process.

SquarePhish is a publicly available red teaming tool that targets OAuth device grant authorization flows via QR codes, mimicking legitimate Microsoft MFA/TOTP setups.

Graphish is a malicious phishing kit shared on underground forums, supporting OAuth abuse, Azure App Registrations, and adversary-in-the-middle (AiTM) attacks.

Regarding the campaigns Proofpoint observed, the researchers highlighted three in the report: 

* **Salary bonus attacks** – A campaign using document-sharing lures and localized company branding to entice recipients to click links to attacker-controlled websites. Victims are then instructed to complete "secure authentication" by entering a provided code on Microsoft’s legitimate device login page, which authorizes an attacker-controlled application.

![Authorization page used in the attack](https://www.bleepstatic.com/images/news/u/1220909/2025/December/1(1).jpg)

**Authorization page used in the attack**  
_Source: Proofpoint_

* **TA2723 attacks** – An actor involved in high-volume credential-phishing, previously known for spoofing Microsoft OneDrive, LinkedIn, and DocuSign, that started using OAuth device code phishing in October. Proofpoint assesses that early phases of these campaigns likely used SquarePhish2, with later waves potentially shifting to the Graphish phishing kit.

**TA2723's OneDrive spoof**  
_Source: Proofpoint_

* **State-aligned activity** – Since September 2025, Proofpoint observed a suspected Russia-aligned threat actor tracked as UNK\_AcademicFlare abusing OAuth device code authorization for account takeover. The actor uses compromised government and military email accounts to build rapport before sharing links that spoof OneDrive, leading victims into a device code phishing workflow. The activity primarily targets government, academic, think tank, and transportation sectors in the U.S. and Europe.

**Malicious email that follows a prior innocuous interaction**  
_Source: Proofpoint_

To block these attacks, Proofpoint recommends that organizations use Microsoft Entra Conditional Access where possible and consider introducing a policy on sign-in origin.