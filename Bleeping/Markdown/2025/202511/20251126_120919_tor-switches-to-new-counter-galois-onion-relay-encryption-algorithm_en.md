# Tor switches to new Counter Galois Onion relay encryption algorithm

![Tor switches to new Counter Galois Onion relay encryption algorithm](https://www.bleepstatic.com/content/hl-images/2024/09/19/tor-logo.jpg)

Tor has announced improved encryption and security for the circuit traffic by replacing the old tor1 relay encryption algorithm with a new design called Counter Galois Onion (CGO).

One reason behind this decision is to make the network [more resilient](https://blog.torproject.org/introducing-cgo/) against modern traffic-interception attacks that could compromise data security and undermine Tor user anonymity.

The Tor network is a global system consisting of thousands of relays that create a circuit for data packets to travel to their destination through three relays (entry, middle, and exit), each hop adding a layer of encryption (onion routing).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Users of the Tor Browser, a hardened version of Firefox built for browsing the Tor network, benefit from this onion routing to communicate privately, share or access information anonymously, bypass censorship, and evade ISP-level tracking.

Typically, Tor is used by dissidents, activists, whistleblowers, journalists, researchers, and generally privacy-conscious people, including cybercriminals looking to access darknet markets.

As the Tor team explains in an announcement, Tor1 was developed at a time when cryptography was far less advanced than today, and the standards have improved significantly since then.

One issue with the tor1 design is that it uses AES-CTR encryption without hop-by-hop authentication, which leads to malleable relay encryption. This means that an adversary could modify traffic between relays they control and observe predictable changes - a tagging attack that is part of the [internal covert channel](https://spec.torproject.org/proposals/344-protocol-info-leaks.html#11-highly-severe-internal-covert-channel-vectors) class of attacks. 

Another problem is that tor1 uses partial forward secrecy by reusing the same AES keys throughout a circuit’s lifetime, enabling decryption in the event of key theft.

A third security concern is that tor1 uses a 4-byte SHA-1 digest for cell authentication, giving attackers a one-in-4 billion probability to forge a cell without being detected.

The Tor project notes that only the first attack in the list is more severe, and the last two examples were mentioned "for the sake of completeness."

## Introducing CGO

CGO addresses the above problems. It is built on a Rugged Pseudorandom Permutation (RPRP) construction called UIV+, [designed by cryptography researchers](https://eprint.iacr.org/2025/583) Jean Paul Degabriele, Alessandro Melloni, Jean-Pierre Münch, and Martijn Stam.

Tor says that this system has been [verified](http://eprint.iacr.org/2025/2017) to meet specific security requirements, including protection against "tagging resistance, immediate forward secrecy, longer authentication tags, limited bandwidth overhead, relatively efficient operation, and modernized cryptography."

Specifically, CGO improves on the following compared to Tor1:

* **Tagging protection:** CGO uses wide-block encryption and tag chaining, so any modification makes the entire cell and future cells unrecoverable, blocking tagging attacks.
* **Forward secrecy:** CGO updates keys after every cell, so past traffic cannot be decrypted even if current keys are exposed.
* **Stronger authentication:** SHA-1 is removed from relay encryption entirely, and CGO uses a 16-byte authenticator, which the Tor team comments is what “sensible people use.”
* **Circuit integrity:** CGO chains T’ (encrypted tag) and N (initial nonce) across cells, so each cell depends on all previous cells, ensuring tampering resistance.

Overall, CGO is a modern, research-based encryption and authentication system that addresses many of Tor1’s problems without incurring large bandwidth penalties.

The project maintainers say that adding CGO into the C Tor implementation and its Rust-based client, Arti, is underway, and the feature is marked as experimental. Pending work includes the addition of onion service negotiation and performance optimizations.

Tor browser users do not need to do anything to benefit from CGO, as the change will happen automatically once the new system can be fully deployed. However, a timeline for when it will become the default option has not been provided.