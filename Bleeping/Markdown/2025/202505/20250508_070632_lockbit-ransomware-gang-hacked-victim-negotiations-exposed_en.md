# LockBit ransomware gang hacked, victim negotiations exposed

![LockBit](https://www.bleepstatic.com/content/hl-images/2023/02/01/lockbit-flames.jpg)

The LockBit ransomware gang has suffered a data breach after its dark web affiliate panels were defaced and replaced with a message linking to a MySQL database dump.

All of the ransomware gang's admin panels now state. "Don't do crime **CRIME IS BAD** xoxo from Prague," with a link to download a "paneldb\_dump.zip."

![LockBit dark web site defaced with link to database](https://www.bleepstatic.com/images/news/ransomware/l/lockbit/admin-panel-data-breach/lockbit-panel-breached.png)

**LockBit dark web site defaced with link to database**

As [first spotted](https://x.com/ReyXBF/status/1920220381681418713) by the threat actor, Rey, this archive contains a SQL file dumped from the site affiliate panel's MySQL database.

From analysis by BleepingComputer, this database contains twenty tables, with some more interesting than others, including:

* A '**btc\_addresses**' table that contains 59,975 unique bitcoin addresses.
* A '**builds**' table contains the individual builds created by affiliates for attacks. Table rows contain the public keys, but no private keys, unfortunately. The targeted companies' names are also listed for some of the builds.
* A '**builds\_configurations**' table contains the different configurations used for each build, such as which ESXi servers to skip or files to encrypt.
* A '**chats**' table is very interesting as it contains 4,442 negotiation messages between the ransomware operation and victims from December 19th to April 29th.  
![Affiliate panel 'chats' table](https://www.bleepstatic.com/images/news/ransomware/l/lockbit/admin-panel-data-breach/chats-table.png)  
**Affiliate panel 'chats' table**
* A '**users**' table lists 75 admins and affiliates who had access to the affiliate panel, with [Michael Gillespie](https://x.com/demonslay335) spotting that passwords were stored in plaintext. Examples of some of the plaintext passwords are 'Weekendlover69, 'MovingBricks69420', and 'Lockbitproud231'.

Based on the last date record in the negotiation chats table, the database appears to have been dumped at some point on April 29th, 2025.

It's unclear who carried out the breach and how it was done, but the defacement message matches the one used in a recent [breach of Everest ransomware's dark web site](https://www.bleepingcomputer.com/news/security/everest-ransomwares-dark-web-leak-site-defaced-now-offline/), suggesting a possible link.

Furthermore, the phpMyAdmin SQL dump shows that the server was running PHP 8.1.2, which is vulnerable to critical and actively exploited vulnerability tracked as [CVE-2024-4577](https://www.bleepingcomputer.com/news/security/critical-php-rce-vulnerability-mass-exploited-in-new-attacks/) that can be used to achieve remote code execution on servers. 

In 2024, a law enforcement operation called Operation Cronos [took down LockBit's infrastructure](https://www.bleepingcomputer.com/news/security/lockbit-ransomware-disrupted-by-global-police-operation/), including 34 servers hosting the data leak website and its mirrors, data stolen from the victims, cryptocurrency addresses, 1,000 decryption keys, and the affiliate panel.

Although LockBit managed to rebuild and resume operations after the takedown, this latest breach strikes a further blow to its already damaged reputation.

It's too early to tell if this additional reputation hit will be the final nail in the coffin for the ransomware gang.

Other ransomware groups who have experienced similar leaks include [Conti](https://www.bleepingcomputer.com/news/security/conti-ransomwares-internal-chats-leaked-after-siding-with-russia/), [Black Basta](https://www.bleepingcomputer.com/news/security/black-basta-ransomware-gang-s-internal-chat-logs-leak-online/), and [Everest](https://www.bleepingcomputer.com/news/security/everest-ransomwares-dark-web-leak-site-defaced-now-offline/).