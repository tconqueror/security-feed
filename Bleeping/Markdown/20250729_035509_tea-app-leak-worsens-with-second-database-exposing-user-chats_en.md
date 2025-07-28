# Tea app leak worsens with second database exposing user chats

![Tea logo](https://www.bleepstatic.com/content/hl-images/2025/07/28/tea-header.jpg)

The Tea app data breach has grown into an even larger leak, with the stolen data now shared on hacking forums and a second database discovered that allegedly contains 1.1 million private messages exchanged between the app's members.

The Tea app is a women-only dating safety platform where members can share reviews about men, with access to the platform only granted after providing a selfie and government ID verification.

On Friday, an anonymous user posted on 4chan that Tea used an unsecured Firebase storage bucket to store drivers' licenses and selfies uploaded by members to verify they are women, as well as photos and images shared in comments.

The user shared a Python script that could be used to download the data from the now-secured storage bucket.

In total, over 59 GB of data was exposed in the leak, with Tea confirming in a public statement that it affects users who signed up before 2024.

"A legacy data storage system was compromised, resulting in unauthorized access to a dataset from prior to February 2024," reads a [security breach announcement](https://www.teaforwomen.com/cyberincident).

"This dataset includes approximately 72,000 images, including approximately 13,000 selfies and photo identification submitted by users during account verification and approximately 59,000 images publicly viewable in the app from posts, comments and direct messages."

The platform states that selfies were not deleted as expected to comply with law enforcement requirements related to cyber-bullying prevention.

Threat actors have now begun sharing torrents of the leaked data on hacking forums, potentially exposing the app's members to social engineering attacks.

BleepingComputer has confirmed that the shared data contains driver's licenses, selfies, and message attachments.

To make matters worse, [404 Media now reports](https://www.404media.co/a-second-tea-breach-reveals-users-dms-about-abortions-and-cheating/) that an additional database was found containing 1.1 million private messages sent between users on the Tea platform.

This database contains much more recent data, ranging from 2023 to last week, and reportedly includes messages discussing sensitive topics, such as those about abortions, cheating husbands, and two-timing boyfriends.

According to 404 Media, it's possible to identify users based on social media profiles, phone numbers, or other personal details revealed in the messages.

What was meant to be a safe space for women has now become a tool to embarrass them, with someone even creating a “facesmash”-style site where visitors can rate the selfies exposed in the leaked data.

Tea says they continue to work with third-party cybersecurity experts to contain the incident and conduct an investigation into the attack.

The app says that it also notified law enforcement, who are assisting with the investigation.