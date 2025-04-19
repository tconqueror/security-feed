# Widespread Microsoft Entra lockouts tied to new security feature rollout

![Microsoft with a red background](https://www.bleepstatic.com/content/hl-images/2024/01/26/microsoft-red-header.jpg)

Windows administrators from numerous organizations report widespread account lockouts triggered by false positives in the rollout of a new Microsoft Entra ID's "leaked credentials" detection app called MACE.

These alerts and lockouts began last night, with some admins believing they were false positives as the accounts have unique passwords that are not used on any other sites or applications.

Microsoft Entra ID, formerly Azure Active Directory, is a cloud-based identity and access management service that helps organizations manage user identities and secure access to resources.

In a [Reddit thread](https://www.reddit.com/r/sysadmin/comments/1k2pmkz/new%5Fentra%5Fleaked%5Fcredentials%5Fno%5Fbreach%5Fon%5Fhibp%5Fetc/) posted early this morning, Windows admins reported receiving multiple alerts from Entra indicating that some of their user accounts had been found with credentials leaked on the dark web or other locations.

These accounts were automatically locked out of the tenant, with numerous users impacted per organization.

"Us as well... about 1/3rd of our accounts got locked out about \~1 hour ago. We're a MSP so I'm assuming this is happening to our clients as well," posted an admin on [Reddit](https://www.reddit.com/r/sysadmin/comments/1k2pmkz/comment/mnvyx3p/).

The locked-out accounts showed no signs of compromise, such as suspicious sign-ins, and were protected with MFA. Furthermore, breach notification services like Have I Been Pwned (HIBP) had no matches for these accounts.​

Another report on Reddit further corroborated that this was widespread, with an MDR provider stating they [received over 20,000 notifications](https://www.reddit.com/r/sysadmin/comments/1k2pmkz/new%5Fentra%5Fleaked%5Fcredentials%5Fno%5Fbreach%5Fon%5Fhibp%5Fetc/) from Microsoft overnight regarding leaked credentials from different customers.

While Microsoft has not publicly confirmed the cause of these lockouts, Microsoft told one of the affected organizations it was caused by an issue with the rollout of a new Enterprise application called "MACE Credential Revocation."

"Just got off with engineer. It is Tenant Lockout due to this MACE ninja rollout they did. no signs of compromise. He needs an hour to convert the ticket from compromise to lockout but can breathe a sigh of relief. It was Error Code: 53003 for conditional access policy," an admin reported on Reddit.

Multiple people confirmed this application was added to tenants right before they began receiving the alerts.

MACE Credential Revocation app is a [Microsoft Entra feature](https://learn.microsoft.com/en-us/entra/identity/authentication/feature-availability#:~:text=Leaked%20credentials%20%28MACE%29) used to detect leaked credentials and lockout potentially compromised accounts.

While all alerts of leaked credentials should be investigated to confirm that an account was not compromised, if you received a flurry of alerts at once this rollout likely caused it.

BleepingComputer contacted Microsoft with questions about this incident but has not received a response at this time.