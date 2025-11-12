# Windows 11 now supports 3rd-party apps for native passkey management

![Windows 11 now supports 3rd-party apps for native passkey management](https://www.bleepstatic.com/content/hl-images/2023/10/09/Passkeys_passwordless.jpg)

Microsoft announced that passwordless authentication is now easier on Windows 11 through native support for third-party passkey managers, the first ones supported being 1Password and Bitwarden.

This is possible after the Windows security team worked together with third-party managers to improve passwordless authentication by developing a passkey API for Windows 11\. 

The [new feature](http://techcommunity.microsoft.com/blog/windows-itpro-blog/windows-11-expands-passkey-manager-support/4467572) has been introduced with the [November 2025 security update](https://www.bleepingcomputer.com/news/microsoft/microsoft-november-2025-patch-tuesday-fixes-1-zero-day-63-flaws/) for [Windows 11](https://www.bleepingcomputer.com/news/microsoft/windows-11-kb5068861-and-kb5068865-cumulative-updates-released/), released yesterday.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Passkeys are a secure authentication mechanism that follows the FIDO2/WebAuthn standards, utilizing private-public key cryptography for local challenge signing and server-side verification, rather than passwords.

When users register on a passkey-enabled site or app, Windows generates a key pair, with the private key securely stored on Microsoft Password Manager, 1Password, or Bitwarden.

![Bitwarden login with passkey Windows integration](https://www.bleepstatic.com/images/news/u/1220909/2025/November/Bitwarden.jpg)

**Bitwarden login with passkey Windows integration**  
_Source: Microsoft_

From then on, when attempting to log in on that site or app, a challenge is served to Windows, and the user is requested to verify themselves using Windows Hello, which is protected by PIN and biometrics authentication.

The system is considered superior to passwords due to its portability, higher convenience for users, and immunity to phishing attacks.

Microsoft has been pushing the adoption of passkeys on Windows, and the addition of third-party app support via the new API adds more flexibility for users.

In addition to the third-party app support, Microsoft has also integrated Microsoft Password Manager from Microsoft Edge natively into Windows as a plugin to allow users to choose their passkey manager.

Microsoft highlights the following security benefits for this development:

* Passkey creation, authentication, and management are protected by Windows Hello
* Syncing is available across Windows devices when signed into Edge with the same Microsoft account
* Syncing is protected by the manager PIN and a cloud enclave
* Azure Managed Hardware Security Modules (HSMs) safeguard encryption keys
* Sensitive operations run in Azure Confidential Compute
* Recovery uses Azure Confidential Ledger

**LinkedIn passkey saved on Microsoft Password Manager**  
_Source: Microsoft_

Microsoft Edge [introduced passkey saving and syncing](https://blogs.windows.com/msedgedev/2025/11/03/microsoft-edge-introduces-passkey-saving-and-syncing-with-microsoft-password-manager/) with Microsoft Password Manager earlier this month, in version 142 and later, for Windows 10 and above.

Bitwarden has supported passkey storage and management since November 2023 and introduced “[Log in with Passkeys](https://bitwarden.com/blog/log-into-bitwarden-with-a-passkey/)” in January 2024.

The popular password manager [announced the Windows 11 integration](https://bitwarden.com/blog/bitwarden-launches-passkey-management/) via an update on its original feature launch announcement, noting that its system-level integration on the OS is currently at beta stage.

This means that there may be functional limitations or potential instability until sufficient broad-scale testing and bug fixing happens.