# New Spiderman phishing service targets dozens of European banks

![New Spiderman phishing service targets dozens of European banks](https://www.bleepstatic.com/content/hl-images/2025/12/10/spiderman.jpg)

A new phishing kit called Spiderman is targeting customers of numerous European banks and cryptocurrency services using pixel-perfect replicas of legitimate sites.

The platform allows cybercriminals to launch phishing campaigns that can capture login credentials, two-factor authentication (2FA) codes, and credit card data.

The Spiderman phishing kit, analyzed by researchers at Varonis, targets financial institutions in five countries, including major brands such as Deutsche Bank, ING, Comdirect, Blau, O2, CaixaBank, Volksbank, and Commerzbank.

The researchers observed that it can create phishing pages for online portals of fintech companies, such as the Swedish service Klarna and PayPal. It can also steal seed phrases for Ledger, Metamask, and Exodus cryptocurrency wallets.

![Some of the targeted platforms](https://www.bleepstatic.com/images/news/u/1220909/2025/December/04.jpg)

**Some of the targeted platforms**  
_Source: Varonis_

“Because Spiderman is modular, new banks, portals, and authentication methods can be added. As European countries roll out updated e-banking flows, this kit will likely evolve in parallel,” Varonis says in its [report](https://www.varonis.com/blog/spiderman-phishing-kit).

The researchers found that Spiderman is popular among cybercriminals, with one of its groups on Signal counting 750 members.

From the dashboard, operators can view victim sessions in real time, capture credentials, perform one-click data export, intercept PhotoTAN/one-time pass (OTP) codes in real time, and harvest credit card details.

![Real-time interaction with victim through the control panel](https://www.bleepstatic.com/images/news/u/1220909/2025/December/01.jpg)

**Real-time interaction through the control panel**  
_Source: Varonis_

PhotoTAN is an OTP system used by many banks in Europe, where a colored mosaic image is displayed during login or transaction approval steps, which the user must scan with the bank’s app to proceed.

The app decodes the mosaic and displays a transaction-specific OTP that must be entered back into the banking site.

Although PhotoTAN capture [isn’t a novel feature](https://www.bleepingcomputer.com/news/security/new-v3b-phishing-kit-targets-customers-of-54-european-banks/) in phishing kits, it is considered a “must-have” for platforms targeting European institutions.

Spiderman operators can configure their targeting scope from the control panel, limiting it to specific countries, adding ISP allowlisting, device-type filters (mobile or desktop users), and setting up redirects for visitors that don’t qualify for phishing attacks.

Varonis researchers warn that the data captured by Spiderman can lead to banking account takeover, SIM swapping, credit card fraud, and identity theft.

All phishing kits rely on victims clicking on a link that takes them to a fake login page, so the best protection is to always confirm you’re on the official domain before entering your credentials, and double-checking for [browser-in-the-browser](https://www.bleepingcomputer.com/news/security/sneaky2fa-phaas-kit-now-uses-redteamers-browser-in-the-browser-attack/) windows that could display the correct URL.

Receiving an SMS or PhotoTAN prompt on your device that is not linked to an action you made is a sign of a takeover attempt and should be reported to the bank immediately.