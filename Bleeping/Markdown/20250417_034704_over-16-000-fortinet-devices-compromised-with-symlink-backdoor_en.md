# Over 16,000 Fortinet devices compromised with symlink backdoor

![Fortinet](https://www.bleepstatic.com/content/hl-images/2023/03/13/Fortinet.jpg)

Over 16,000 internet-exposed Fortinet devices have been detected as compromised with a new symlink backdoor that allows read-only access to sensitive files on previously compromised devices.

This exposure is being reported by threat monitoring platform The Shadowserver Foundation, which initially reported 14,000 devices were exposed.

Today, Shadowserver's Piotr Kijewski told BleepingComputer that the cybersecurity organization now detects [16,620 devices](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=30&source=compromised%5Fwebsite&source=compromised%5Fwebsite6&tag=fortinet-compromised%2B&dataset=unique%5Fips&style=stacked) impacted by the recently revealed persistence mechanism.

Last week, Fortinet warned customers that they had [discovered a new persistence mechanism](https://www.bleepingcomputer.com/news/security/fortinet-hackers-retain-access-to-patched-fortigate-vpns-using-symlinks/) used by a threat actor to retain read-only remote access to files in the root filesystem of previously compromised but now patched FortiGate devices.

Fortinet said that this was not through the exploitation of new vulnerabilities but is instead linked to attacks starting in 2023 and continuing into 2024, where a threat actor utilized zero days to compromise FortiOS devices.

Once they gained access to the devices, they created symbolic links in the language files folder to the root file system on devices with SSL-VPN enabled. As the language files are publicly accessible on FortiGate devices with SSL-VPN enabled, the threat actor could browse to that folder and gain persistent read access to the root file system, even after the initial vulnerabilities were patched.

"A threat actor used a known vulnerability to implement read-only access to vulnerable FortiGate devices. This was achieved via creating a symbolic link connecting the user filesystem and the root filesystem in a folder used to serve language files for the SSL-VPN. This modification took place in the user filesystem and avoided detection," [Fortinet said](https://www.fortinet.com/blog/psirt-blogs/analysis-of-threat-actor-activity).

"Therefore, even if the customer device was updated with FortiOS versions that addressed the original vulnerabilities, this symbolic link may have been left behind, allowing the threat actor to maintain read-only access to files on the device's file system, which may include configurations."

This month, Fortinet began notifying customers privately by email about FortiGate devices detected by FortiGuard as being compromised with this symlink backdoor.

![Emails sent to owners of compromised devices](https://www.bleepstatic.com/images/news/u/1109292/2025/Fortinet-email.jpg)

**Emails sent to owners of compromised devices**  
_Source: BleepingComputer_

Fortinet has released an updated AV/IPS signature that will detect and remove this malicious symbolic link from compromised devices. The latest version of the firmware has also been updated to detect and remove the link. The update also prevents unknown files and folders from being served by the built-in webserver.

Finally, if a device was detected as compromised, it is possible that the threat actors had access to the latest configuration files, including credentials.

Therefore, all credentials should be reset, and admins should follow the other steps in [this guide](https://community.fortinet.com/t5/FortiGate/Technical-Tip-Recommended-steps-to-execute-in-case-of-a/ta-p/230694).