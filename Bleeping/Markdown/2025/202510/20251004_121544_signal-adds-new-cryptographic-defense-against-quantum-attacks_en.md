# Signal adds new cryptographic defense against quantum attacks

![Signal adds new cryptographic defense against quantum attacks](https://www.bleepstatic.com/content/hl-images/2025/09/08/Signal.jpg)

Signal announced the introduction of Sparse Post-Quantum Ratchet (SPQR), a new cryptographic component designed to withstand quantum computing threats.

SPQR will serve as an advanced mechanism that continuously updates the encryption keys used in conversations and discarding the old ones.

Signal is a cross-platform, end-to-end encrypted messaging and calling app managed by the non-profit Signal Foundation, with an estimated monthly active user base of up to 100 million.

The new component guarantees forward secrecy and post-compromise security, ensuring that even in the case of key compromise or theft, future messages exchanged between parties will be safe.

In terms of cryptography, SPQR utilizes post-quantum Key-Encapsulation Mechanisms (ML-KEM) instead of elliptic-curve Diffie-Hellman, and features efficient chunking and erasure coding to handle large key sizes without bloating bandwidth.

Signal has been using CRYSTALS-Kyber (a post-quantum KEM) alongside an implementation of the Elliptic Curve Diffie-Hellman [since 2023](https://www.bleepingcomputer.com/news/security/signal-adds-quantum-resistant-encryption-to-its-e2ee-messaging-protocol/) to protect against quantum computing attacks that threaten to break current encryption.

However, SPQR comes on top of the existing double ratchet system, forming what Signal calls a Triple Ratchet, formulates a hyper-secure “mixed key.”

“When you want to send a message you ask both the Double Ratchet and SPQR “What encryption key should I use for the next message?” and they will both give you a key,” [reads Signal’s announcement](https://signal.org/blog/spqr/).

“Instead of either key being used directly, both are passed into a Key Derivation Function – a special function that takes random-enough inputs and produces a secure cryptographic key that’s as long as you need. This gives you a new “mixed” key that has hybrid security.”

The new system was designed in collaboration with PQShield, AIST (Japan), and New York University, with its technical foundation based in part on USENIX 2025 and Eurocrypt 2025 papers.

The design was also formally verified using ProVerif, and the Rust implementation robustness was tested using the hax tool. Continuous verification will now be applied to all future builds, ensuring proofs are reproduced with every code change.

Signal says the rollout of SPQR on the messaging platform will be gradual, and users don’t need to take any action for the upgrade to apply apart from keeping their clients updated to the latest version.

The new system will be backward compatible in the sense that, when an SPQR-enabled client communicates with someone who doesn’t support the technology yet, the security model will be downgraded.

Once SPQR is made available to all clients, Signal will enforce it across all sessions.