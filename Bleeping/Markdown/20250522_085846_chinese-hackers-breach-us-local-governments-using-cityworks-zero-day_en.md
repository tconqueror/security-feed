# Chinese hackers breach US local governments using Cityworks zero-day

![Panda bear](https://www.bleepstatic.com/content/hl-images/2024/07/09/red-cyber-panda.jpg)

Chinese-speaking hackers have exploited a now-patched Trimble Cityworks zero-day to breach multiple local governing bodies across the United States.

Trimble Cityworks is a Geographic Information System (GIS)-based asset management and work order management software primarily used by local governments, utilities, and public works organizations and designed to help infrastructure agencies and municipalities manage public assets, handle permitting and licensing, and process work orders.

The hacking group (UAT-6382) behind this campaign used a Rust-based malware loader to deploy Cobalt Strike beacons and VSHell malware designed to backdoor compromised systems and provide long-term persistent access, as well as web shells and custom malicious tools written in Chinese.

These attacks started in January 2025, when Cisco Talos observed the first signs of reconnaissance activity within the breached organizations' networks.

"Talos has found intrusions in enterprise networks of local governing bodies in the United States (U.S.), beginning January 2025 when initial exploitation first took place. Upon gaining access, UAT-6382 expressed a clear interest in pivoting to systems related to utilities management," [said](https://blog.talosintelligence.com/uat-6382-exploits-cityworks-vulnerability/) Cisco Talos security researchers Asheer Malhotra and Brandon White.

"The web shells, including AntSword, chinatso/Chopper and generic file uploaders, contained messaging written in the Chinese language. Furthermore, the custom tooling, TetraLoader, was built using a malware-builder called 'MaLoader' that is also written in Simplified Chinese."

## Federal agencies warned to patch immediately

The security flaw exploited in these attacks ([CVE-2025-0994](https://nvd.nist.gov/vuln/detail/CVE-2025-0994)) is a high-severity deserialization vulnerability that allows authenticated threat actors to execute code remotely on the targets' Microsoft Internet Information Services (IIS) servers.

In early February 2025, when it released security updates to patch this vulnerability, Trimble warned that it was aware of attackers [trying to exploit CVE-2025-0994](https://www.bleepingcomputer.com/news/security/hackers-exploit-cityworks-rce-bug-to-breach-microsoft-iis-servers/) to breach some Cityworks deployments.

The U.S. Cybersecurity and Infrastructure Security Agency (CISA) also [added CVE-2025-0994](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-0994&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) to its catalog of actively exploited vulnerabilities on February 7, ordering federal agencies to patch their systems within three weeks as mandated by the November 2021 Binding Operational Directive (BOD) 22-01.

"These types of vulnerabilities are frequent attack vectors for malicious cyber actors and pose significant risks to the federal enterprise," the [cybersecurity agency warned](https://www.cisa.gov/news-events/alerts/2025/02/07/cisa-adds-one-known-exploited-vulnerability-catalog).

Days later, on February 11, CISA [released an advisory](https://www.bleepingcomputer.com/news/security/hackers-exploit-cityworks-rce-bug-to-breach-microsoft-iis-servers/) warning to organizations in the water and wastewater systems, energy, transportation systems, government services and facilities, and communications sectors to "install the updated version immediately."