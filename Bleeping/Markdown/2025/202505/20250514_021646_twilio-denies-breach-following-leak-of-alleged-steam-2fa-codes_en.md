# Twilio denies breach following leak of alleged Steam 2FA codes

![Twilio denies breach following leak of alleged Steam 2FA codes](https://www.bleepstatic.com/content/hl-images/2022/09/12/steam-header-new.jpg)

Twilio has denied in a statement for BleepingComputer that it was breached after a threat actor claimed to be holding over 89 million Steam user records with one-time access codes.

The threat actor, using the alias Machine1337 (also known as EnergyWeaponsUser), advertised a trove of data allegedly pulled from Steam, offering to sell it for $5,000.

When examining the leaked files, which contained 3,000 records, BleepingComputer found historic SMS text messages with one-time passcodes for Steam, including the recipient's phone number.

![Threat actor's post on XSS](https://www.bleepstatic.com/images/news/u/1220909/2025/May/forum-post(1).jpg)

**Threat actor's post on XSS**  
*Source: BleepingComputer*

Owned by Valve Corporation, Steam is the world's largest digital distribution platform for PC games, with over 120 million monthly active users.

Valve did not respond to our requests for a comment on the threat actor's claims.

Independent games journalist MellolwOnline1, who is also the creator of the SteamSentinels community group that monitors abuse and fraud in the Steam ecosystem, suggests that the incident is a supply-chain compromise involving Twilio.

MellowOnline1 pointed to technical evidence in the leaked data that indicates real-time SMS log entries from Twilio's backend systems, hypothesizing a compromised admin account or abuse of API keys.

[![Tweet](https://www.bleepstatic.com/images/news/u/1220909/2025/May/steam.png)](https://x.com/MellowOnline1/status/1921682082025115818)

Twilio is a cloud communications company that provides APIs for sending SMS, voice calls, and 2FA messages, widely used by apps like Steam for user authentication.

When asked by BleepingComputer about their possible involvement in the alleged Steam breach, a Twilio spokesperson acknowledged the situation and confirmed they're investigating.

"Twilio takes these threats very seriously and is reviewing the alleged incident. We will provide more information as it becomes available," a company spokesperson told BleepingComputer.

Twilio later followed up with a statement clarifying that the company's systems had not been breached.

"There is no evidence to suggest that Twilio was breached. We have reviewed a sampling of the data found online, and see no indication that this data was obtained from Twilio." - Twilio spokesperson

Looking at the data, one possible explanation for its origin is a leak from an SMS provider that intermediates the communication of one-time access codes between Twilio and Steam users.

Some of the messages delivered are clearly confirmation codes for accessing a Steam account or for associating a phone number with one.

However, BleepingComputer could not determine if the data comes from an SMS provider or who it might be. Additionally, we could not verify the threat actor's claims.

It is worth mentioning that some of the data is relatively new, as we found many of the delivery dates were from the beginning of March.

Twilio provides a two-factor authentication (2FA) product called [Verify API](https://www.twilio.com/en-us/user-authentication-identity/verify) that customers, game providers among them, can implement with various communication channels (SMS, WhatsApp, voice, email, passkeys, silent device approval, push, or time-based one-time passwords).

Out of abundance of caution, Steam users are recommended to enable [Steam Guard Mobile Authenticator](https://help.steampowered.com/en/faqs/view/7EFD-3CAE-64D3-1C31) for additional security and monitor account activity for unauthorized login attempts.