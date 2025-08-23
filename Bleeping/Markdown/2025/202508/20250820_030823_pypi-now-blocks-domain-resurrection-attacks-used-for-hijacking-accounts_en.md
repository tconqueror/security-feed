# PyPI now blocks domain resurrection attacks used for hijacking accounts

![PyPI now blocks domain resurrection attacks used for hijacking accounts](https://www.bleepstatic.com/content/hl-images/2024/03/28/back.jpg)

The Python Package Index (PyPI) has introduced new protections against domain resurrection attacks that enable hijacking accounts through password resets.

PyPI is the official repository for open-source Python packages. It is used by software developers, product maintainers, and companies working with Python libraries, tools, and frameworks.

Accounts of project maintainers publishing software on PyPI are linked to email addresses. In the case of some projects, the email address is tied to a domain name.

If a domain name expires, an attacker can register it and use it to take control of a project on PyPi after setting up an email server and issuing a password reset request for the account.

The risk from this is that of a supply-chain attack where hijacked projects push malicious versions of popular Python packages, which, in many cases would be installed automatically using pip.

One notable case of such an attack was the [compromise of the ‘ctx’ package](https://www.bleepingcomputer.com/news/security/popular-python-and-php-libraries-hijacked-to-steal-aws-keys/) in May 2022, where a threat actor added code that targeted Amazon AWS keys and account credentials.

In an attempt to tackle this problem, PyPI now checks whether the domains of verified email addresses on the platform have expired or are entering expiration phases, and marks those addresses as unverified.

Technically, PyPI uses Domainr’s Status API to determine a domain’s lifecycle stage (active, grace period, redemption period, pending deletion) to decide if action needs to be taken on a given account.

![Domain lifecycle stages](https://www.bleepstatic.com/images/news/u/1220909/2025/August/diagram(1).jpg)

**Domain lifecycle stages**  
_Source: PyPI_

Once the email addresses enter that state, they cannot be used for password resets or other account recovery actions, thus closing the opportunity window for exploitation even if an attacker registers the domain.

The [new measures](https://blog.pypi.org/posts/2025-08-18-preventing-domain-resurrections/) actually entered development in April, when tentative scans were performed to evaluate the landscape. Eventually, they were introduced in June 2025, with daily scans. Since then, over 1,800 email addresses have been unverified under the new system.

While not foolproof or adequate against all attack scenarios, the new measures significantly reduce the risk of attackers taking over PyPI accounts through the exploitation of expired domains.

PyPI recommends that users add a backup email from a non-custom domain to their account to avoid disruptions, and enable two-factor authentication on their PyPI account for stronger protection against hijacking.