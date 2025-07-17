# Google sues to disrupt BadBox 2.0 botnet infecting 10 million devices

![Android devices](https://www.bleepstatic.com/content/hl-images/2024/12/19/android-malware-botnet.jpg)

Google has filed a lawsuit against the anonymous operators of the Android BadBox 2.0 malware botnet, accusing them of running a global ad fraud scheme against the company's advertising platforms.

The BadBox 2.0 malware botnet is a cybercrime operation that utilizes infected Android Open Source Project (AOSP) devices, including smart TVs, streaming boxes, and other connected devices that lack security protections, such as Google Play Protect.

These devices become infected either by threat actors purchasing low-cost AOSP devices, modifying the operating system to include the BadBox 2 malware, and then reselling them online, or by tricking users into downloading and installing malicious apps on their devices that contain the malware.

The malware then becomes a backdoor that connects to command-and-control (C2) servers operated by the attackers, where it receives commands to execute on the device.

Once compromised, devices become part of the BadBox 2.0 botnet, where they are turned into residential proxies sold to other cybercriminals without the victims' knowledge or are used to conduct ad fraud.

Google's lawsuit primarily focuses on the ad fraud component, which the botnet commonly conducts against the company's advertising platforms.

This ad fraud is done in three ways:

* **Hidden ad rendering**: Fake "evil twin" apps are silently installed on infected devices to load hidden ads in the background on attacker-controlled websites with Google ads, generating fraudulent ad revenue for the operation.
* **Web-based game sites**: Bots are instructed to launch invisible web browsers and play rigged games that rapidly trigger Google ad views. Each ad view results in revenue for the attacker-controlled publisher accounts.
* **Search ad click fraud**: Bots are instructed to perform search queries on attacker-operated websites that utilize AdSense for Search, generating advertising revenue from advertisements shown in the retrieved search results.

In December 2024, the [original BadBox botnet was disrupted by Germany](https://www.bleepingcomputer.com/news/security/germany-blocks-badbox-malware-loaded-on-30-000-android-devices/) after the country blocked communication between the infected devices and their command and control (C2) infrastructure by sinkholing DNS queries.

However, that did not stop the criminal enterprise, as the threat actors quickly launched BadBox 2.0, which is now believed to have [infected over 10 million Android-based devices](https://www.bleepingcomputer.com/news/security/fbi-badbox-20-android-malware-infects-millions-of-consumer-devices/) as of April 2025\. Google's [complaint](http://legacy.www.documentcloud.org/documents/26001727-google-badbox2-complaint/) says that there are more than 170,000 infected devices in New York state alone.

Google's complaint states that it has already terminated thousands of publisher accounts linked to the operation, but warns that the botnet continues to grow and poses an increasing cybersecurity risk. 

"If the BadBox 2.0 Scheme is not disrupted, it will continue to proliferate," warns Google.

"The BadBox 2.0 Enterprise will continue to generate revenue, will use those proceeds to expand its reach, producing new devices and new malware to fuel its criminal activity, and Google will be forced to continue expending substantial financial resources to investigate and combat the Enterprise's fraudulent activity."

Because the defendants are unknown and believed to reside in China, Google is pursuing relief under the Computer Fraud and Abuse Act and the Racketeer Influenced and Corrupt Organizations (RICO) Act.

The company seeks damages and a permanent injunction to dismantle the malware infrastructure and prevent the further spread of the malware.

Included in the complaint is a list of over 100 internet domains that are part of the cybercrime operation's infrastructure.