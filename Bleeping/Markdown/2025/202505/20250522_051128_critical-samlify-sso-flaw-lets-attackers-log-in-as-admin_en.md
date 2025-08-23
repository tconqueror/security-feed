# Critical Samlify SSO flaw lets attackers log in as admin

![Login prompt](https://www.bleepstatic.com/content/hl-images/2025/05/21/login-prompt.jpg)

A critical Samlify authentication bypass vulnerability has been discovered that allows attackers to impersonate admin users by injecting unsigned malicious assertions into legitimately signed SAML responses.

Samlify is a high-level authentication library that helps developers integrate SAML SSO and Single Log-Out (SLO) into Node.js applications. It is a popular tool for building or connecting to identity providers (IdPs) and service providers (SPs) using SAML.

The library is used by SaaS platforms, organizations implementing SSO for internal tools, developers integrating with corporate Identity Providers like Azure AD or Okta, and in federated identity management scenarios. It is very popular, measuring over 200,000 weekly downloads on npm.

The flaw, tracked as [CVE-2025-47949](https://nvd.nist.gov/vuln/detail/CVE-2025-47949), is a critical (CVSS v4.0 score: 9.9) Signature Wrapping flaw impacting all versions of Samlify before 2.10.0.

As EndorLabs explained in a report, Samlify correctly verifies that the XML document providing a user's identity is signed. Still, it proceeds to read fake assertions from a part of the XML that isn't.

Attackers holding a valid signed SAML response through interception or via public metadata can modify it to exploit the parsing flaw in the library and authenticate as someone else.

"The attacker then takes this legitimately signed XML document and manipulates it. They insert a second, malicious SAML Assertion into the document," [explains EndorLabs](https://www.endorlabs.com/learn/cve-2025-47949-reveals-flaw-in-samlify-that-opens-door-to-saml-single-sign-on-bypass).

"This malicious assertion contains the identity of a target user (e.g., an administrator's username)."

"The crucial part is that the valid signature from the original document still applies to a benign part of the XML structure, but the SP's vulnerable parsing logic will inadvertently process the unsigned, malicious assertion."

This is a complete SSO bypass, allowing unauthorized remote attackers to perform privilege escalation and log in as administrators.

The attacker needs no user interaction or special privileges, and the only requirement is access to a valid signed XML blob, making the exploitation relatively simple.

To mitigate the risk, it is recommended that users upgrade to Samlify version 2.10.0, released earlier this month.

Note that GitHub [still offers 2.9.1](https://github.com/tngan/samlify/releases) as the latest version, but [npm hosts](https://www.npmjs.com/package/samlify) the safe-to-use 2.10.0 as of writing.

There have not been any reports of active exploitation of CVE-2025-47949 in the wild, but impacted users are advised to take immediate action and secure their environments.