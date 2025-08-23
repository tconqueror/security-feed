# ExpressVPN bug leaked user IPs in Remote Desktop sessions

![ExpressVPN](https://www.bleepstatic.com/content/hl-images/2025/07/21/expressvpn-header.jpg)

ExpressVPN has fixed a flaw in its Windows client that caused Remote Desktop Protocol (RDP) traffic to bypass the virtual private network (VPN) tunnel, exposing the users' real IP addresses.

One of the key premises of a VPN is masking a user's IP address, allowing users to stay anonymous online, and in some cases, bypass censorship. Failing to do so is a severe technical failure for a VPN product.

ExpressVPN is a leading VPN service provider, consistently rated among the top VPN services, and used by millions worldwide. It utilizes RAM-only servers that don't retain user data and adheres to an audited no-logs policy.

On April 25, 2025, a security researcher known as "Adam-X" reported a vulnerability through ExpressVPN's bug bounty program that exposed RDP and other TCP traffic transmitted over port 3389.

Upon investigating, the ExpressVPN team found that the issue was caused by remnants of debug code used for internal testing being mistakenly included in production builds, specifically, from 12.97 (released four months ago) to 12.101.0.2-beta.

"If a user established a connection using RDP, that traffic could bypass the VPN tunnel," [reported ExpressVPN in an announcement](https://www.expressvpn.com/blog/expressvpn-rdp-leak-fixed/).

"This did not affect encryption, but it meant that traffic from RDP connections wasn't routed through ExpressVPN as expected."

"As a result, an observer, like an ISP or someone on the same network, could have seen not only that the user was connected to ExpressVPN, but also that they were accessing specific remote servers over RDP—information that would normally be protected."

A patch was made available with ExpressVPN version 12.101.0.45, released on June 18, 2025.

The privacy firm notes that the security lapse did not compromise encryption on the tunnels, and the leak scenarios only affect those using Remote Desktop Protocol (RDP), which they consider to be low-risk for their customers.

"As mentioned above, in practice, this issue would most commonly have affected users actively using RDP—a protocol that's generally not used by typical consumers," reads ExpressVPN's advisory.

"Given that ExpressVPN's user base is made up predominantly of individual users rather than enterprise customers, the number of affected users is likely small."

RDP is a Microsoft network protocol that enables users to remotely control Windows systems over a network, used by IT administrators, remote workers, and enterprises.

Still, it is recommended that users upgrade their Windows clients to version 12.101.0.45 for ultimate protection.

ExpressVPN states that it will strengthen its internal build checks to prevent similar bugs from being introduced in production in the future, including enhanced automation in development testing.

Last year, ExpressVPN faced another issue causing [DNS request leaks](https://www.bleepingcomputer.com/news/security/expressvpn-bug-has-been-leaking-some-dns-requests-for-years/) when users enabled the 'slipt tunneling' feature on the Windows client.

The feature was temporarily disabled until a fix was implemented in a future release.