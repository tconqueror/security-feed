# O2 UK patches bug leaking mobile user location from call metadata

![Antenna](https://www.bleepstatic.com/content/hl-images/2021/08/23/Cell-towers.jpg)

A flaw in O2 UK's implementation of VoLTE and WiFi Calling technologies could allow anyone to expose the general location of a person and other identifiers by calling the target.

The problem was discovered by security researcher Daniel Williams, who says the flaw existed on O2 UK's network since March 27, 2017, and was resolved yesterday.

O2 UK is a British telecommunications service provider owned by Virgin Media O2. As of March 2025, the company reported having nearly 23 million mobile customers and 5.8 million broadband clients across the UK, positioning it as one of the major providers in the country.

In March 2017, the firm launched its IP Multimedia Subsystem (IMS) service, branded as "4G Calling," for better audio quality and line reliability during calls.

However, as Williams discovered while analyzing the traffic during such a call, the signalling messages (SIP Headers) exchanged between the communicating parties are far too verbose and revealing, including IMSI, IMEI, and cell location data.

"The responses I got from the network were extremely detailed and long, and were unlike anything I had seen before on other networks," [explains Williams](https://mastdatabase.co.uk/blog/2025/05/o2-expose-customer-location-call-4g/).

"The messages contained information such as the IMS/SIP server used by O2 (Mavenir UAG) along with version numbers, occasional error messages raised by the C++ services processing the call information when something went wrong, and other debugging information."

![Information exposed in the SIP Headers](https://www.bleepstatic.com/images/news/u/1220909/2025/May/cell-id-calculator.jpg)

**Information exposed in the SIP Headers**  
_Source: mastdatabase.co.uk_

## Locating users by call

Using the Network Signal Guru (NSG) app on a rooted Google Pixel 8, Williams intercepted raw IMS signalling messages exchanged during a call and decoded the cell ID to find the last cell tower the call recipient connected to.

Then, he used public tools that provide cell tower maps to find the geographic coordinates of the tower.

![Locating the cell tower](https://www.bleepstatic.com/images/news/u/1220909/2025/May/cellmapper-sector.jpg)

**Locating the cell tower**  
_Source: mastdatabase.co.uk_

For urban areas where tower coverage is dense, the accuracy would reach 100 m2 (1076 ft2). In rural areas, geo-locating would get less precise, but could still be revealing for the target.

Williams found the trick also worked when the target was abroad, as he located a test subject in Copenhagen, Denmark.

**Tracking a person in Denmark**  
_Source: mastdatabase.co.uk_

## O2 UK confirms fix

Williams says that he contacted O2 UK multiple times on March 26 and 27, 2025, to report his findings, receiving no answers.

Finally, he got direct confirmation from O2 UK earlier today that the issue has been fixed, and he confirmed this through testing.

In a statement to BleepingComputer, a Virgin Media spokesperson confirmed that a fix has been implemented, noting that customers do not have to take any action to protect themselves.

"Our engineering teams have been working on and testing a fix for a number of weeks – we can confirm this is now fully implemented, and tests suggest the fix has worked, and our customers do not need to take any action," Virgin Media O2 told BleepingComputer.

BleepingComputer asked O2 whether this flaw was known to be exploited and if they plan to inform customers accordingly, but we did not receive an answer.