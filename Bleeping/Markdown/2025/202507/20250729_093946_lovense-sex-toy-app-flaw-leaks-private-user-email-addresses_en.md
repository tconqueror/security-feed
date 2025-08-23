# Lovense sex toy app flaw leaks private user email addresses

![Lovense](https://www.bleepstatic.com/content/hl-images/2025/07/28/lovense-toy.jpg)

The connected sex toy platform Lovense is vulnerable to a zero-day flaw that allows an attacker to get access to a member's email address simply by knowing their username, putting them at risk of doxxing and harassment.

Lovense is an interactive sex toy manufacturer, best known for producing app-controlled sex toys with names like the Lush, the Gush, and, perhaps most boldly, the Kraken. The company claims to have 20 million customers worldwide.

While Lovense toys are commonly used for both local and long-distance entertainment, they are also popular among cam models who allow viewers to tip or subscribe for remote control of their toys.

However, the connected experience can also expose their Lovense username, and due to this flaw, potentially reveal their private email address.

Lovense usernames are often publicly shared on forums and social media, making them easy targets for attackers.

The flaw was discovered by security researcher BobDaHacker, who collaborated with researchers Eva and Rebane to reverse engineer the app and automate the attack.

The researchers disclosed two flaws over four months ago, on March 26, 2025. However, only one of the flaws, a critical account hijacking flaw, was subsequently fixed.

### The Lovense flaws

The vulnerability stems from the interaction between Lovense's XMPP chat system, used for communication between users, and the platform's backend.

"So it all started when I was using the Lovense app and muted someone. That's it. Just muted them," explains [BobDaHacker's report](https://bobdahacker.com/blog/lovense-still-leaking-user-emails).

"But then I saw the API response and was like... wait, is that an email address? Why is that there? After digging deeper, I figured out how to turn any username into their email address."

To exploit the flaw, an attacker makes a POST request to the `/api/wear/genGtoken` API endpoint with their credentials, which returns a gtoken (authentication token) and AES-CBC encryption keys.

The attacker then takes any publicly known Lovense username and encrypts it using the retrieved encryption keys. This encrypted payload is sent to the `/app/ajaxCheckEmailOrUserIdRegisted?email={encrypted_username}` API endpoint.

The server responds with data containing a fake email address, which the researcher converted into a fake Jabber ID (JID) used by Lovense's XMPP server.

By adding this fake JID to their XMPP contact list and sending a presence subscription over XMPP (similar to a friend request), the attacker can refresh the roster (contact list), which now includes both the fake JID and the real one associated with the target's account.

However, the problem is that the real JID is constructed using the user's actual email, in the format username!!!domain.com_w@im.lovense.com, allowing attackers to extract the victim's email address.

For example, if it returned bleeping!!!example.com_w@im.lovense.com, the resulting actual email of the Lovense account is bleeping@example.com.

The researchers confirmed that the entire process can be completed in less than one second per user with a script. BleepingComputer created a fake account today and shared our username with BobDaHacker, allowing them to simply connect as a friend and return the email we registered with.

The researcher also stated that it's not necessary to accept a friend request to exploit the flaw.

BleepingComputer also confirmed that it is relatively easy to find legitimate usernames on forums and Lovense-related sites, like lovenselife.com.

The researcher also claims that the FanBerry extension, created by Lovense, and the Tophy app can be used to harvest usernames, making wide-scale email harvesting possible.

The researchers also discovered a critical vulnerability that let them completely hijack an account.

Using only an email address, an attacker could generate authentication tokens without needing a password. Using these tokens, an attacker could impersonate a user on Lovense platforms, including Lovense Connect, StreamMaster, and Cam101.

These tokens reportedly worked on admin accounts as well.

While Lovense has mitigated this flaw by rejecting the tokens on its APIs, the researchers noted that gtokens can still be generated without a password.

Both issues were reported to Lovense on March 26, 2025. In April, after also submitting the bugs on HackerOne, Lovense informed the researchers that the email issue was already known and fixed in an upcoming version.

The company initially downplayed the account hijacking flaw, but after being told it could allow full admin account access, Lovense reclassified it as critical.

In total, the researchers received $3,000 for the disclosure of the flaws.

On June 4, the company claimed the flaws were fixed, but the researchers confirmed this was not the case. Lovense ultimately fixed the account hijack flaw in July but stated that it would take approximately 14 months to resolve the email flaw, as it would break compatibility with older versions of their app.

"We've launched a long-term remediation plan that will take approximately ten months, with at least four more months required to fully implement a complete solution," Lovense told the researcher.

"We also evaluated a faster, one-month fix. However, it would require forcing all users to upgrade immediately, which would disrupt support for legacy versions. We've decided against this approach in favor of a more stable and user-friendly solution."

The researchers criticized this response, stating the company repeatedly claimed the issues were fixed when they were not.

"Your users deserve better. Stop putting old app support over security. Actually fix things. And test your fixes before saying they work," BobDaHacker wrote in the report.

In 2016, [multiple Lovense flaws](https://internetofdon.gs/lovense/) exposed email addresses or allowed attackers to determine if an email address had an account at Lovense.

BleepingComputer reached out to Lovense for comment but did not receive a response.