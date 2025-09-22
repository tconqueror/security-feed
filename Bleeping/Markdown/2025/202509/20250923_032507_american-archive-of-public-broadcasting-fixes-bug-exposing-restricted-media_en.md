# American Archive of Public Broadcasting fixes bug exposing restricted media

![Camera](https://www.bleepstatic.com/content/hl-images/2025/09/22/digital-camera-media.jpg)

​A vulnerability in the American Archive of Public Broadcasting's website allowed downloading of protected and private media for years, with the flaw quietly patched this month.

BleepingComputer was tipped about the flaw by a cybersecurity researcher who asked to remain anonymous, stating that the flaw has been exploited since at least 2021, even after the researcher previously reported it to the organization.

After contacting AAPB about the flaw, a spokesperson confirmed the issue, and the researcher validated that the fix was implemented within 48 hours.

"We're committed to protecting and preserving the archival material in the AAPB and have strengthened security for the archive," stated AAPB's Communications Manager, Emily Balk, to BleepingComputer.

"We look forward to continuing to make public media history free and accessible to the public."

The American Archive, operated by WGBH Educational Foundation (GBH) and the Library of Congress, is a public nonprofit archive whose mission is to collect, digitize, and preserve historically significant content produced by public radio and television in the United States.

BleepingComputer was told that the AAPB vulnerability first circulated as a rumor in online discussions about the leak of the Sesame Street "Wicked Witch of the West" episode on the Lost Media Wiki Discord channel.

Lost Media Wiki took down the episode, saying that it was "likely obtained in an illegal data breach," urging members to refrain from re-sharing it on its Discord channel.

Initially secret, the exploit method began circulating in Discord preservation groups by mid-2024, leading to further leaks of protected content on Discord servers focused on content preservation.

Known as data hoarders, these communities dedicate themselves to archiving software, websites, operating systems, and various forms of media, including TV shows, music, and movies. However, they often operate in a gray area, where copyrighted content is preserved and shared, blurring the line with digital piracy.

Even with AAPB's takedown efforts, the exploit continued to circulate on various Discord servers and messaging apps, with a proof-of-concept shared with BleepingComputer showing just how easy it was to abuse.

The exploit shared with BleepingComputer is a simple Tampermonkey script that exploits an insecure direct object reference (IDOR) flaw, allowing users to request media files by ID and bypass AAPB's access controls.

The bug enabled users to change the media ID parameter in media access requests, allowing them to access resources by the ID, even if they were protected or private.

Although the main /media/{ID} pages had some access controls, attackers could bypass them by tampering with fetch or XMLHttpRequest calls made in the background.

Instead of AAPB's server rejecting those requests with a '403 Forbidden' error, as long as the request had a valid media ID, the content was served.

While the vulnerability has now been fixed, it is not known how much content was accessed and shared within the data hoarder community.

The leak of content at American Archive followed another incident earlier this year, where [PBS employee contact information was leaked](https://www.bleepingcomputer.com/news/security/pbs-confirms-data-breach-after-employee-info-leaked-on-discord-servers/) and spread through Discord servers for fans of 'PBS Kids.'

Both incidents illustrate how archival and fan communities can gain access to sensitive or private data, even when it's not used for malicious purposes.