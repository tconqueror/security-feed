# SSL/TLS certificate lifespans reduced to 47 days by 2029

![Padlock](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

The CA/Browser Forum has voted to significantly reduce the lifespan of SSL/TLS certificates over the next 4 years, with a final lifespan of just 47 days starting in 2029.

The CA/Browser Forum is a group of certificate authorities (CAs) and software vendors, including browser developers, working together to establish and maintain security standards for digital certificates used in Internet communications.

Its members include major CAs like DigiCert and GlobalSign, as well as browser vendors such as Google, Apple, Mozilla, and Microsoft.

Earlier this year, [Apple proposed](http://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/bvWh5RN6tYI) a motion to reduce certificate lifespans, which Sectigo, the Google Chrome team, and Mozilla endorsed.

This proposal would gradually reduce the lifespan of certificates over the next four years from its current 398-day lifespan to 47 days in March 2029.

The goal is to minimize risks from outdated certificate data, deprecated cryptographic algorithms, and prolonged exposure to compromised credentials. It also encourages companies and developers to utilize automation to renew and rotate TLS certificates, making it less likely that sites will be running on expired certificates.

SSL/TLS certificates are digital files that enable secure communication over the internet (HTTPS) by encrypting data and authenticating websites.

They encrypt the connection so sensitive data like passwords and credit card data entered on website forms cannot be intercepted by attackers in the middle.

These certificates are also used to authenticate the website and guarantee data integrity, meaning the information exchanged between the user and the server hasn't been tampered with.

When those certificates expire without renewal, users see a warning on their browser informing them that their connection isn't private or secure.

Currently, the lifespan and the Domain Control Validation (DCV) of those certificates is 398 days, but the majority of certificate authorities agreed that this is too long in today's security landscape.

With [25 votes for and none against](https://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/9768xgUUfhQ?pli=1), the CA/Browser Forum has now ruled to shorten the lifespan as follows:

* **From March 15, 2026**, certificate lifespan and DCV will be reduced to 200 days
* **From March 15, 2027**, certificate lifespan and DCV will be reduced to 100 days
* **From March 15, 2029**, the certificate lifespan will be reduced to 47 days and DCV to 10 days

Shortening the certificate lifecycle is bound to introduce management overhead and add a large burden for people who handle multiple domains. However, it is expected to force more frequent revalidation of companies requesting certificates, encourage automation, and ultimately make the ecosystem more agile and secure.

This gradual shortening of certificate lifespans gives impacted entities enough time to implement and transition to automated certificate renewal systems, such as those offered by cloud providers, Let's Encrypt, or certificate providers that support the ACME protocol.