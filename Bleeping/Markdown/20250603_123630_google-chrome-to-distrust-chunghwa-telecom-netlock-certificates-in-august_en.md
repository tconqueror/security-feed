# Google Chrome to distrust Chunghwa Telecom, Netlock certificates in August

![Chrome](https://www.bleepstatic.com/content/hl-images/2023/11/28/Google_Chrome.jpg)

Google says it will no longer trust root CA certificates signed by Chunghwa Telecom and Netlock in the Chrome Root Store due to a pattern of compliance failures and failure to make improvements.

The change will come in Google Chrome version 139, which is scheduled for release on August 1, 2025.

The tech giant cites ongoing compliance failures, broken improvement commitments, and lack of measurable progress as the reasons for this action.

"Chrome's confidence in the reliability of Chunghwa Telecom and Netlock as CA Owners included in the Chrome Root Store has diminished due to patterns of concerning behavior observed over the past year," [reads the announcement](https://security.googleblog.com/2025/05/sustaining-digital-certificate-security-chrome-root-store-changes.html).

"These patterns represent a loss of integrity and fall short of expectations, eroding trust in these CA Owners as publicly-trusted certificate issuers trusted by default in Chrome."

Chunghwa Telecom is Taiwan's largest telecom provider, operating internet, mobile, and fixed-line services. It runs a public Certificate Authority (CA) called ePKI and HiPKI, issuing digital certificates for secure web communications.

Netlock is a significant Hungarian provider of digital certification services (electronic signatures, timestamping, and TLS/SSL certificates), best known for its Arany (Gold Class) Root CA, which is widely used in Hungary and other European countries.

The Chrome Root Store is a list of trusted certificate authorities maintained by Google and used by Chrome to validate HTTPS connections. 

Both entities have acted as public Certification Authorities (CAs) for years, with their certificates included in the Chrome Root Store, meaning Chrome trusted them by default.

Starting on August 1, 2025, Google Chrome will display a "Your connection is not private" warning when users visit websites that continue to use certificates issued by Chunghwa Telecom or Netlock, as their root CAs will no longer be trusted.

![Warning generated on pages using non-trusted certificates](https://www.bleepstatic.com/images/news/u/1220909/2025/June/warning.jpg)

**Warning generated on pages using non-trusted certificates**  
_Source: Google_

Although moving past that page will be possible, this action will break the smooth browsing experience on impacted sites and create trust issues for visitors.

For this reason, impacted web admins are recommended to take action now and switch to a trusted CA as soon as possible.

While Netlock and Chunghwa Telecom certificates signed up to July 31, 2025, will still be trusted, it is recommended not to postpone their inevitable replacement.

Google notes that impacted enterprises can override trust changes by installing the affected roots as locally trusted.

It should be noted that this change will not impact Microsoft Edge, Mozilla Firefox, or Apple Safari, as they utilize different browser trust stores.

This latest action follows a similar one [against Entrust](https://security.googleblog.com/2024/06/sustaining-digital-certificate-security.html), announced in June 2024 and entering into force on November 12, 2024.

At the time, Google justified its decision by noting that Entrust had been involved in multiple publicly disclosed incidents that showed it had failed to meet industry compliance and security standards since 2018.

Similarly, Entrust failed to deliver on promises to improve its practices or showcase measurable progress.

In March 2025, Google announced new mandatory security [requirements for all CAs](https://security.googleblog.com/2025/03/new-security-requirements-adopted-by.html) issuing publicly trusted HTTPS/TLS certificates, signaling its intent to tighten standards and push CAs to quickly meet evolving compliance expectations.

The Chunghwa Telecom and Netlock cases are the first examples of enforcing those stricter requirements, with more likely to follow in the future.