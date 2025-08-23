# Threat actors downgrade FIDO2 MFA auth in PoisonSeed phishing attack

![Hacker](https://www.bleepstatic.com/content/hl-images/2024/05/07/hacker-card.jpg)

A PoisonSeed phishing campaign is bypassing FIDO2 security key protections by abusing the cross-device sign-in feature in WebAuthn to trick users into approving login authentication requests from fake company portals.

The PoisonSeed threat actors are known to employ large-volume phishing attacks for financial fraud. In the past, [distributing emails containing crypto seed phrases](https://www.bleepingcomputer.com/news/security/poisonseed-phishing-campaign-behind-emails-with-wallet-seed-phrases/) used to drain cryptocurrency wallets.

In the recent phishing attack [observed by Expel](https://expel.com/blog/poisonseed-downgrading-fido-key-authentications-to-fetch-user-accounts/), the PoisonSeed threat actors do not exploit a flaw in FIDO2's security but rather abuse the legitimate cross-device authentication feature.

Cross-device authentication is a WebAuthn feature that allows users to sign in on one device using a security key or authentication app on another device. Instead of requiring a physical connection, such as plugging in a security key, the authentication request is transmitted between devices via Bluetooth or a QR code scan.

The attack begins by directing users to a phishing site that impersonates corporate login portals, such as from Okta or Microsoft 365.

When the user enters their credentials into the portal, the campaign uses an adversary-in-the-middle (AiTM) backend to silently log in with the submitted credentials on the legitimate login portal in real-time.

The user targeted in the attack normally would use their FIDO2 security keys to verify multi-factor authentication requests. However, the phishing backend instead tells the legitimate login portal to authenticate using cross-device authentication.

This causes the legitimate portal to generate a QR code, which is transmitted back to the phishing page and displayed to the user.

When the user scans this QR code using their smartphone or authentication app, it approves the login attempt initiated by the attacker.

![PoisonSeed attack flow to bypass FIDO2 protections](https://www.bleepstatic.com/images/news/security/phishing/p/poisonseed/bypass-fido2/poisonseed-attack-flow.jpg)

**PoisonSeed attack flow to bypass FIDO2 protections**  
_Source: Expel_

This method effectively bypasses FIDO2 security key protections by allowing attackers to initiate a login flow that relies on cross-device authentication instead of the user's physical FIDO2 key.

Expel warns that this attack does not exploit a flaw in the FIDO2 implementation, but instead abuses a legitimate feature that downgrades the FIDO key authentication process.

To mitigate the risk, Expel recommends the following defenses:

* Limiting geographic locations from which users are allowed to log in and establishing a registration process for individuals traveling.
* Routinely check for the registration of unknown FIDO keys from unknown locations and uncommon security key brands.
* Organizations can consider enforcing Bluetooth-based authentication as a requirement for cross-device authentication, which significantly reduces the effectiveness of remote phishing attacks.

Expel also observed a separate incident where a threat actor registered their own FIDO key after compromising an account via what is believed to be phishing and resetting the password. However, this attack did not require any methods to trick the user, like a QR code.

This attack highlights how threat actors are finding ways to bypass phishing-resistant authentication by tricking users into completing login flows that bypass the need for physical interaction with a security key.