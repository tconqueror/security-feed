# SonicWall finds no SSLVPN zero-day, links ransomware attacks to 2024 flaw

![Sonicwall](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall_headpic.jpeg)

SonicWall says that recent Akira ransomware attacks exploiting Gen 7 firewalls with SSLVPN enabled are exploiting an older vulnerability rather than a zero-day flaw.

The company says that the attackers are targeting CVE-2024-40766, an unauthorized access flaw fixed in August 2024.

"We now have high confidence that the recent SSLVPN activity is not connected to a zero-day vulnerability," reads the update on the SonicWall bulletin published this week.

"Instead, there is a significant correlation with threat activity related to CVE-2024-40766, which was previously disclosed and documented in our public advisory [SNWLID-2024-0015](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2024-0015)."

CVE‑2024‑40766 is a critical [SSLVPN access control flaw](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-critical-access-control-flaw-in-sonicos/) in SonicOS, allowing unauthorized access to vulnerable endpoints, enabling attackers to hijack sessions or gain VPN access in protected environments.

The flaw was [exploited extensively](https://www.bleepingcomputer.com/news/security/sonicwall-sslvpn-access-control-flaw-is-now-exploited-in-attacks/) following its disclosure roughly a year ago, including by [Akira](https://www.bleepingcomputer.com/news/security/critical-sonicwall-sslvpn-bug-exploited-in-ransomware-attacks/) and [Fog ransomware](https://www.bleepingcomputer.com/news/security/fog-ransomware-targets-sonicwall-vpns-to-breach-corporate-networks/) operators who leveraged it to breach corporate networks.

On Friday, Arctic Wolf Labs first hinted at the potential existence of a zero-day vulnerability in SonicWall Gen 7 firewalls, after noticing Akira ransomware attack patterns that supported this assumption.

SonicWall quickly confirmed that it is aware of an ongoing campaign, and [advised customers](https://www.bleepingcomputer.com/news/security/sonicwall-urges-admins-to-disable-sslvpn-amid-rising-attacks/) to turn off SSL VPN services and limit connectivity to trusted IP addresses until the situation clears up.

Following internal investigations on 40 incidents, the vendor now disputes the possibility of attackers exploiting a zero-day vulnerability in its products.

Instead, SonicWall says the Akira attacks are targeting endpoints that did not follow the recommended course of action for mitigating CVE-2024-40766 when migrating from Gen 6 to Gen 7 firewalls.

"Many of the incidents relate to migrations from Gen 6 to Gen 7 firewalls, where local user passwords were carried over during the migration and not reset," [explains SonicWall](https://www.sonicwall.com/support/notices/gen-7-and-newer-sonicwall-firewalls-sslvpn-recent-threat-activity/250804095336430).

"Resetting passwords was a critical step outlined in the original advisory."

The recommended action now is to update firmware to version 7.3.0 or later, which has stronger brute-force and MFA protections, and reset all local user passwords, especially those used for SSLVPN.

As SonicWall also emailed customers this latest update, many [took to Reddit](https://www.reddit.com/r/msp/comments/1mjk7k7/sonicwall%5Fwalks%5Fback%5Fzero%5Fday%5Fnotice%5Fon%5Fsslvpn/) to express their doubts about the accuracy of the vendor's claims, saying that not everything in it checks out with their own experience.

Some [noted](https://www.reddit.com/r/sonicwall/comments/1mjin7r/sonicwall%5Fzeroday%5Fupdate%5F230pm%5F86/) that they had breaches on accounts that didn't exist before migrating to Gen 7 firewalls, and even claimed that SonicWall declined to examine their logs.

These contradicting reports, combined with the ambiguous wording SonicWall used in its update, leave room for uncertainty, so vigilance and immediate application of the recommended measures remain crucial.