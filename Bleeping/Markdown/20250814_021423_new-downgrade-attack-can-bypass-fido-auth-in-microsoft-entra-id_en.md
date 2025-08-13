# New downgrade attack can bypass FIDO auth in Microsoft Entra ID

![Microsoft](https://www.bleepstatic.com/content/hl-images/2024/01/26/microsoft-red-header.jpg)

Security researchers have created a new FIDO downgrade attack against Microsoft Entra ID that tricks users into authenticating with weaker login methods, making them susceptible to phishing and session hijacking.

These weaker login channels are vulnerable to adversary-in-the-middle phishing attacks that employ tools like Evilginx, enabling attackers to snatch valid session cookies and hijack the accounts.

Although the attack doesn't prove a vulnerability in FIDO itself, it shows that the system can be bypassed, which is a crucial weakness.

This is especially worrying considering the increased adoption of FIDO-based authentication in critical environments, a consequence of the technology being touted as extremely phishing-resistant.

FIDO passkeys are a passwordless authentication method based on the FIDO2 and WebAuthn standards, designed to eliminate the weaknesses of passwords and traditional multi-factor authentication (MFA).

When a user registers a passkey, their device generates a pair of keys (private + public), which are used for solving a random, unique challenge during login onto online services, verifying the user's identity.

As only the user's device holds the correct private key, which isn't transmitted anywhere during the login process, there's nothing phishing actors can intercept.

## Downgrading and bypassing FIDO

The new downgrade attack created by [Proofpoint researchers](https://www.proofpoint.com/us/blog/threat-insight/dont-phish-let-me-down-fido-authentication-downgrade) employs a custom phishlet within the Evilginx adversary-in-the-middle (AiTM) framework to spoof a browser user agent that lacks FIDO support.

Specifically, the researchers spoof Safari on Windows, which is [not compatible](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-fido2-compatibility) with FIDO-based authentication in Microsoft Entra ID.

"This seemingly insignificant gap in functionality can be leveraged by attackers," explains Proofpoint researcher Yaniv Miron.

"A threat actor can adjust the AiTM to spoof an unsupported user agent, which is not recognized by a FIDO implementation. Subsequently, the user would be forced to authenticate through a less secure method. This behavior, observed on Microsoft platforms, is a missing security measure."

When the target clicks a phishing link delivered via email, SMS, or an OAuth consent prompt, they are directed to a phishing site running the custom phishlet. As this is an AiTM attack, the legitimate Microsoft Entra ID form is proxied by the phishing platform and shown to the targeted user.

Because the phishlet spoofs an unsupported browser user agent, Microsoft Entra ID turns off FIDO authentication and instead returns an error.

This error prompts the user to choose an alternate verification fallback method, such as the Microsoft Authenticator app, SMS code, or OTP.

![Login error (left) and fallback options (right)](https://www.bleepstatic.com/images/news/u/1220909/2025/August/1.jpg)

**Login error (left) and fallback options (right)**  
_Source: Proofpoint_

If the user uses one of the alternative methods, the AiTM proxy intercepts both their account credentials and the MFA token or session cookie.

The attacker then imports the stolen cookie into their own browser, granting full access to the victim's account, which was theoretically phishing-resistant.

Proofpoint says it has observed no cases of this technique being used by hackers in the wild yet, as threat actors still focus on easier targets such as accounts lacking MFA protection. Still, the risk is significant, especially in limited, highly targeted attacks.

To mitigate risks from this emerging threat, consider turning off fallback authentication methods for your account or activating additional checks and confirmations when such processes are triggered.

If a login process suddenly asks for a different method instead of a registered passkey, it's a red flag, and users should abort and verify via official, trusted channels.

In July, Expel researchers presented a different FIDO downgrade attack [dubbed 'PoisonSeed](https://www.bleepingcomputer.com/news/security/threat-actors-try-to-downgrade-fido2-mfa-auth-in-poisonseed-phishing-attack/),' where a phishing site stole the target's credentials and initiated a cross-device authentication flow, generating a QR code on the real service's login page, tricking the target to scan it to approve a login request from a rogue device.

Although the concept was interesting, the researchers later discovered that it was practically infeasible due to proximity requirements, which led to the fraudulent authentication requests failing.