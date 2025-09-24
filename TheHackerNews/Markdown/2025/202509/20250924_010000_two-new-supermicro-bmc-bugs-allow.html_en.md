# Two New Supermicro BMC Bugs Allow Malicious Firmware to Evade Root of Trust Security

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEha20McHRa6QM9%5FcLc5Zt0tgtjRrsac1WMDmrRCwhyphenhyphenZDOgR9xL9btaZ6kzvvX3O1qceOw6fEkSwDCvv-5lhAw7FHGAHgCtFH%5FyMRbmkD6cCiHmTInnVxWNUA2-SmYefabOsra8y%5Fv49M7aDTFMuT52Tt7CWhbFC9wWiYLeQ8fZ-hVYdWCKntdz%5Fvx82qf8U/s728-rw-e365/bmc-exploit.jpg)

Cybersecurity researchers have disclosed details of two security vulnerabilities impacting Supermicro Baseboard Management Controller (BMC) firmware that could potentially allow attackers to bypass crucial verification steps and update the system with a specially crafted image.

The [medium-severity vulnerabilities](https://www.supermicro.com/en/support/security%5FBMC%5FIPMI%5FSept%5F2025), both of which stem from improper verification of a cryptographic signature, are listed below -

* **[CVE-2025-7937](https://nvd.nist.gov/vuln/detail/CVE-2025-7937)** (CVSS score: 6.6) - A crafted firmware image can bypass the Supermicro BMC firmware verification logic of Root of Trust ([RoT](https://www.binarly.io/blog/repeatable-failures-test-keys-used-to-sign-production-software-again)) 1.0 to update the system firmware by redirecting the program to a fake "fwmap" table in the unsigned region
* **[CVE-2025-6198](https://nvd.nist.gov/vuln/detail/CVE-2025-6198)** (CVSS score: 6.4) - A crafted firmware image can bypass the Supermicro BMC firmware verification logic of the Signing Table to update the system firmware by redirecting the program to a fake signing table ("sig\_table") in the unsigned region

[](https://thehackernews.uk/exec-guide-d)

The image validation process carried out during a firmware update takes place over three steps: Retrieve the public key from the BMC SPI flash chip, process the "fwmap" or "sig\_table" table embedded in the uploaded image, and compute a cryptographic hash digest of all "signed" firmware regions, and verify the signature value against the calculated hash digest.

Firmware security company Binarly, which has been credited with discovering and reporting the two shortcomings, said CVE-2025-7937 is a bypass for [CVE-2024-10237](https://www.binarly.io/blog/ghost-in-the-controller-abusing-supermicro-bmc-firmware-verification), which was [disclosed](https://nvd.nist.gov/vuln/detail/CVE-2024-10237) by Supermicro in January 2025\. The vulnerability was originally [discovered](https://developer.nvidia.com/blog/analyzing-baseboard-management-controllers-to-secure-data-center-infrastructure/) by NVIDIA, alongside CVE-2024-10238 and CVE-2024-10239.

CVE-2024-10237 is a "logical flaw in the validation process of the uploaded firmware, which could ultimately result in the BMC SPI chip being reflashed with a malicious image," Binarly researcher Anton Ivanov [said](https://www.binarly.io/blog/broken-trust-fixed-supermicro-bmc-bug-gains-a-new-life-in-two-new-vulnerabilities) in a report shared with The Hacker News. "This security issue could allow potential attackers to gain complete and persistent control of both the BMC system and the main server OS."

"This vulnerability demonstrated that the validation process could be manipulated by adding custom entries to the 'fwmap' table and relocating the original signed content of the image to unreserved firmware space, which ensures that the calculated digest still matches the signed value."

On the other hand, CVE-2024-10238 and CVE-2024-10239 are two stack overflow flaws in the firmware's image verification function, allowing an attacker to execute arbitrary code in the BMC context.

Binarly's analysis found the fix for CVE-2024-10237 to be insufficient, identifying a potential attack pathway by which a custom "fwmap" table can be inserted before the original one, which is then used during the validation process. This essentially enables the threat actor to run custom code in the context of the BMC system.

[](https://thehackernews.uk/cis-security-suite)

Further investigation into the implementation of the firmware validation logic in the X13SEM-F motherboard determined a flaw within the "auth\_bmc\_sig" function that could permit an attacker to load a malicious image without modifying the hash digest value.

"Once again, as all the regions used for the digest calculation are defined in the uploaded image itself (in the 'sig\_table'), it is possible to modify it, along with some other parts of the image – for example, the kernel – and move the original data to unused space in the firmware," Ivanov said. "This means that the signed data digest will still match the original value."

Successful exploitation of CVE-2025-6198 can not only update the BMC system with a specially crafted image, but also get around the BMC RoT security feature.

"Previously, we reported the discovery of the test key on Supermicro devices, and their PSIRT doubled down that the hardware RoT (Root of Trust) authenticates the key and has no impact on this discovery," Alex Matrosov, CEO and Head of REsearch at Binarly, told The Hacker News.

"However, new research shows that the previous statement from Supermicro is not accurate, and CVE-2025-6198 bypasses the BMC RoT. In this case, any leak of the signing key will impact the entire ecosystem. Reusing the signing key is not the best approach, and we recommend at least rotating the signing keys per product line. Based on previous incidents like [PKfail](https://thehackernews.com/2024/08/new-flaws-in-sonos-smart-speakers-allow.html) and the Intel Boot Guard key leakage, the reuse of cryptographic signing keys could cause an industry-wide impact."