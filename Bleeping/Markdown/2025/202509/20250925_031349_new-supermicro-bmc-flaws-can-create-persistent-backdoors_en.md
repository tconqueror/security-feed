# New Supermicro BMC flaws can create persistent backdoors

![New Supermicro BMC flaws can create persistent backdoors](https://www.bleepstatic.com/content/hl-images/2023/12/18/warning.jpg)

Two vulnerabilities affecting the firmware of Supermicro hardware, including Baseboard Management Controller (BMC) allow attackers to update systems with maliciously crafted images.

Supermicro is a maker of servers, motherboards, and data center hardware. BMC is a microcontroller on Supermicro server motherboards that permits remote system monitoring and management even if the system is powered off.

Experts at firmware security company Binarly discovered a bypass for a flaw ([CVE-2024-10237](https://nvd.nist.gov/vuln/detail/CVE-2024-10237)) that Supermicro patched this year in January along with another vulnerabililty identified as CVE-2025-6198.

"This security issue could allow potential attackers to gain complete and persistent control of both the BMC system and the main server OS," Binarly researchers say.

Both security issues can be used to update BMC systems with unofficial firmware, but the researchers say that CVE-2025-6198 can alse be exploited to bypass the BMC RoT (Root of Trust) - a security feature validating that the system is booting with legitimate firmware.

Planting malicious firmware enables persistence across reboots and OS re-installs, high-level control of the server, and reliable bypass of security checks.

To fix CVE-2024-10237, Supermicro [added checks](https://www.supermicro.com/en/support/security%5FBMC%5FIPMI%5FJan%5F2025) to restrict custom _fwmap_ entries, which are a table of instructions inside the firmware image that could be leveraged to manipulate firmware images.

![The signature validation process](https://www.bleepstatic.com/images/news/u/1220909/2025/September/validation%20process.jpg)

**The signature validation process**  
_Source: Binarly_

However, Binarly researchers [discovered](https://www.binarly.io/blog/broken-trust-fixed-supermicro-bmc-bug-gains-a-new-life-in-two-new-vulnerabilities) that it was still possible to inject a malicious _fwmap_ before the vendor’s original is loaded by the system, declaring the signed regions in a way that would let the attacker relocate or replace actual content while keeping the digest consistent.

This means that the calculated hash equals the signed value and the signature verification succeeds, even though parts in the firmware image have been swapped or replaced.

![Bypassing the check](https://www.bleepstatic.com/images/news/u/1220909/2025/September/signed-regions.jpg)

**Bypassing the check**  
_Source: Binarly_

As a result, the BMC accepts and flashes the image, introducing a potentially malicious bootloader or kernel, while everything still appears signed and valid.

The researchers reported the issue to Supermicro. The company confirmed the vulnerability, which is now identified as [CVE-2025-7937](https://nvd.nist.gov/vuln/detail/CVE-2025-7937).

The second bug that Binarly discovered, CVE-2025-6198, arises from a flawed validation logic within the _auth\_bmc\_sig_ function, executed in the OP-TEE environment of the X13SEM-F motherboard firmware.

Since the signed regions are defined in the uploaded image itself, attackers can modify the kernel or other regions and relocate original data to unused firmware space, keeping the digest valid.

The researchers demonstrated flashing and execution of a customized kernel, demonstrating that kernel authentication is not performed during boot, meaning the Root of Trust feature only partially protects the process.

**Injecting a custom BMC firmware**  
_Source: Binarly_

Exploiting the vulnerability achieves the same result as the bypass, permitting the injection of malicious firmware or downgrading the existing image to a less secure one.

Supermicro has released [firmware fixes](http://www.supermicro.com/en/support/security%5FBMC%5FIPMI%5FSept%5F2025) for impacted models. Binarly has released proof-of-concept [exploits for both issues](https://github.com/binarly-io/Research-Data/blob/main/Blogs/The%20Broken%20Trust%3A%20Fixed%20Supermicro%20BMC%20Bug%20Gains%20a%20New%20Life%20in%20Two%20New%20Vulnerabilities/Images/X13SEM-F%5FCVE-2025-6198%5FPOC.bin), so prompt action to protect potentially impacted systems is required.

BMC firmware flaws [are persistent](https://www.bleepingcomputer.com/news/security/intel-and-lenovo-servers-impacted-by-6-year-old-bmc-flaw/) and can be particularly dangerous, in some cases causing [mass-bricking of servers](https://www.bleepingcomputer.com/news/security/critical-ami-megarac-bugs-can-let-hackers-brick-vulnerable-servers/). These problems are also not theoretical, as CISA has previously [flagged exploitation](https://www.bleepingcomputer.com/news/security/cisa-ami-megarac-bug-that-lets-hackers-brick-servers-now-actively-exploited/) of such bugs in the wild.