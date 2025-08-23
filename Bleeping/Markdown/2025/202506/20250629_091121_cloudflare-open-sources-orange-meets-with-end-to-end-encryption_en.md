# Cloudflare open-sources Orange Meets with End-to-End encryption

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2025/06/12/Cloudflare.jpg)

Cloudflare has implemented end-to-end encryption (E2EE) to its video calling app Orange Meets and open-sourced the solution for transparency.

The application has been available since last year when the internet giant launched it as a demo for Cloudflare Calls (now Realtime).

With the [introduction of E2EE](https://blog.cloudflare.com/orange-me2eets-we-made-an-end-to-end-encrypted-video-calling-app-and-it-was/) and the resolution of various trust and verification issues, users interested in strong cryptographic assurances can explore Orange Meets as a foundation for secure video calling in research or prototyping contexts.

## E2EE encryption design

Orange Meets implements end-to-end encryption using Messaging Layer Security (MLS), an IETF-standardized group key exchange protocol.

The Rust-based implementation of MLS on Orange Meets enables continuous group key agreement, which supports secure group key exchange, forward secrecy, post-compromise security, and scalability.

The encryption is handled entirely on the client side using WebRTC, so Cloudflare or the Selective Forwarding Unit (SFU) acts as forwarding intermediaries that do not have access to sensitive communication data.

![Orange Meet topology](https://www.bleepstatic.com/images/news/u/1220909/2025/June/topology.jpg)

**Orange Meet topology**  
_Source: Cloudflare_

Cloudflare has [also introduced](https://blog.cloudflare.com/orange-me2eets-we-made-an-end-to-end-encrypted-video-calling-app-and-it-was/) a "Designated Committer Algorithm" that handles dynamic group membership changes (user joins/leaves a video call) securely.

This system practically designates a specific member as the party that governs MLS updates in a fully client-side fashion, automatically selecting a new designated committer based on the group's state.

![Designated committer handling a new user join action](https://www.bleepstatic.com/images/news/u/1220909/2025/June/designated-commiter.jpg)

**Designated committer handling a new user join action**  
_Source: Cloudflare_

Finally, each video conferencing session displays a "safety number" representing the group's cryptographic state, which participants are encouraged to verify outside the platform.

This prevents "Monster-in-the-Middle" (MitM) attacks where a malicious server substitutes key material.

Cloudflare formally modeled the Designated Committer Algorithm in TLA+, a specification language used to mathematically verify that the protocol behaves correctly under all possible conditions, thereby catching subtle edge-case bugs.

All that being said, it is essential to emphasize that Orange Meets is more of a technical showcase and open-source prototype than a polished consumer product.

It is not as feature-rich and user-friendly as Zoom, Google Meet, Signal, or Microsoft Teams and hasn't been thoroughly audited or battle-tested yet.

Cloudflare's tool is more geared towards developers with an interest in MLS integration and cryptography, as well as privacy enthusiasts and curious users who want to tinker with open-source E2EE video calling. It is also suitable for researchers or engineers evaluating MLS implementations.

Orange Meets does not require installation to test or use, as a live demo is [available online](http://e2ee.orange.cloudflare.dev).

Alternatively, users may set up their own instance by using the source code available on this [GitHub repository](https://github.com/cloudflare/orange).