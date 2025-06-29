# Let’s Encrypt ends certificate expiry emails to cut costs, boost privacy

![Email](https://www.bleepstatic.com/content/hl-images/2024/01/03/email.jpg)

Let's Encrypt has announced it will no longer notify users about imminent certificate expirations via email due to high costs, privacy concerns, and unnecessary complexities.

The decision to end the expiration notification email service was implemented as of June 4, 2025, but Let's Encrypt has now communicated it via a blog post to raise awareness and prevent unexpected disruptions.

Let's Encrypt is a nonprofit Certificate Authority (CA) that provides free, automated, and open digital certificates to enable HTTPS (SSL/TLS) on websites. In terms of size, they are among the largest CAs in the world, issuing hundreds of millions of certificates to billions of websites.

Let's Encrypt is a transparent CA that has minimized data retention wherever possible. Its root certificate is included in all major browsers and OS trust stores, while it enjoys support from prominent tech firms such as Google, Cisco, Mozilla, EFF, Facebook, and Akamai.

The organization utilizes an automated protocol called ACME (Automatic Certificate Management Environment), which enables websites and server software to automate the issuance, installation, and renewal of certificates with minimal or no human intervention.

According to the [latest announcement](https://letsencrypt.org/2025/06/26/expiration-notification-service-has-ended/), the existence of this automation is the primary reason why the email notification service is being sunset, as its need is diminishing.

The adoption of automated renewal solutions has been further accelerated by standards changes, such as the CA/Browser Forum's recent announcement to reduce certificate lifespans to 47 days by 2029.

This decision made manual management impractical, if not impossible, strongly incentivizing the adoption of automation to stay compliant and avoid outages.

A second key reason for the decision to drop the email service is the cost of running it, which Let's Encrypt estimates to be "tens of thousands of dollars per year."

The organization believes it would be far more beneficial to allocate this money to other aspects of its infrastructure, which is also unnecessarily strained by handling email distribution activities.

"Providing expiration notifications adds complexity to our infrastructure, which takes time and attention to manage and increases the likelihood of mistakes being made," explained Let's Encrypt.

"Over the long term, particularly as we add support for new service components, we need to manage overall complexity by phasing out system components that can no longer be justified."

Finally, the organization has user data privacy concerns, as it now has to retain, manage, and protect a sizable database of email addresses linked to issuance records to notify the appropriate parties.

The key takeaway for potentially impacted users is to adopt tools that support the ACME protocol if they haven't already done so and to stop relying on Let's Encrypt's notification emails.

If you need to receive renewal alerts, consider setting up an external notification service in a different manner.