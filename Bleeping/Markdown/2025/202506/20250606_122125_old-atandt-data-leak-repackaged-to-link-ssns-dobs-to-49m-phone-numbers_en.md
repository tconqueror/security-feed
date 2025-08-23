# Old AT&T data leak repackaged to link SSNs, DOBs to 49M phone numbers

![AT&T](https://www.bleepstatic.com/content/hl-images/2024/04/03/att-usa.jpg)

A threat actor has re-released data from a 2021 AT&T breach affecting 70 million customers, this time combining previously separate files to directly link Social Security numbers and birth dates to individual users.

AT&T told BleepingComputer that they are investigating the data but also believe it originates from the known breach and was repackaged into a new leak.

"It is not uncommon for cybercriminals to repackage previously disclosed data for financial gain. We just learned about claims that AT&T data is being made available for sale on dark web forums, and we are conducting a full investigation," AT&T told BleepingComputer.

As first spotted by [HackRead](https://hackread.com/hackers-leak-86m-att-records-with-decrypted-ssns/), the AT&T data was released on a popular Russian-speaking hacking forum, where a threat actor claimed it was stolen during the 2024 [AT&T Snowflake data theft attack](https://www.bleepingcomputer.com/news/security/massive-atandt-data-breach-exposes-call-logs-of-109-million-customers/), which exposed the call logs of 109 million customers.

"Originally one of the database from the snowflake breach here is my backup I created which has bogus numbers such as 00000 (I think federal agents...?) removed and I have also decrypted the SSNs and DOBs," reads the forum post.

![Forum post leaking the 2021 AT&T data](https://www.bleepstatic.com/images/news/security/d/data-breaches/a/att/2021-re-release/forum-post.jpg)

**Forum post leaking the 2021 AT&T data**  
_Source: BleepingComputer_

However, BleepingComputer's analysis of the leak indicates that the data actually originates from an [AT&T data breach in 2021](https://www.bleepingcomputer.com/news/security/atandt-denies-data-breach-after-hacker-auctions-70-million-user-database/) conducted by a well-known threat actor named ShinyHunters, who attempted to sell it for $200,000.

Three years later, in March 2024, another threat actor [leaked the entire AT&T data on a cybercrime forum](https://www.bleepingcomputer.com/news/security/att-says-leaked-data-of-70-million-people-is-not-from-its-systems/) for free, stating it was from ShinyHunter's 2021 AT&T breach.

This data included names, addresses, mobile phone numbers, encrypted date of birth, encrypted social security numbers, and other internal information. However, included in the leak were individual files that mapped the encrypted SSNs and DOBs with their unencrypted plain text strings.

At the time, AT&T first denied that the data was theirs but eventually [confirmed that the data was stolen from their systems](https://www.bleepingcomputer.com/news/security/atandt-confirms-data-for-73-million-customers-leaked-on-hacker-forum/) and impacted 73 million customers.

Analysis of the current leak by BleepingComputer shows it's the same data leaked in 2024 but cleaned up to remove internal AT&T data and add the unencrypted Social Security number and date of birth to each customer record.

In total, there are 88,320,017 lines of data in the leak, but when you remove duplicates, it goes down to 86,017,088 unique records.

Further processing of the data shows that it contains 48,896,044 unique phone numbers with associated customer information.

This significant drop is caused by many customers having multiple records with the same phone number used at different addresses.

To reiterate, this is not a new AT&T leak or the stolen Snowflake data but rather a repackaged version of the 2021 data breach.