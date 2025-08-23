# WhatsApp unveils 'Private Processing' for cloud-based AI features

![WhatsApp](https://www.bleepstatic.com/content/hl-images/2025/04/30/whatsapp-header.jpg)

WhatsApp has announced the introduction of 'Private Processing,' a new technology that enables users to utilize advanced AI features by offloading tasks to privacy-preserving cloud servers.

This is required to utilize AI functionalities such as message summarization and writing suggestions on WhatsApp, which are too demanding for on-device hardware.

The new feature will be entirely opt-in and not enabled by default, giving users complete control over how and when they choose to utilize it.

Private Processing is not immediately available to WhatsApp users but will gradually be rolled out in the upcoming weeks.

## How Private Processing works

For those who opt to use Private Processing, the system performs an anonymous authentication via the user's WhatsApp client to ensure the user's validity.

Next, the app fetches public HPKE encryption keys from a third-party CDN so that Meta cannot trace requests back to specific users, maintaining full anonymity.

The user's device initiates a connection to a Meta gateway through a third-party relay, hiding their real IP address. It establishes a remote attestation (RA) + TLS session between the user's device and Meta's Trusted Execution Environment (TEE).

Next, the user's device sends an end-to-end encrypted request for AI data processing using an ephemeral encryption key, which is processed inside a Confidential Virtual Machine (CVM) isolated from Meta.

Meta claims the processing environment is stateless, and all messages are deleted after they're processed, leaving only "non-sensitive" logs behind.

Finally, the AI-generated response is encrypted with a unique key only known to the device and processing CVM and is sent back over the secure session for decryption on the user's device.

WhatsApp has [promised](https://engineering.fb.com/2025/04/29/security/whatsapp-private-processing-ai-tools/) to share the CVM binary and some source code to allow external validation, while a detailed white paper on the secure design of Private Processing will also be published soon.

## Privacy concerns

Despite the data security and privacy safeguarding assurances offered by Meta, there are always concerns when sensitive data leaves devices for processing on the cloud.

Ultimately, offloading AI tasks to cloud servers always comes with an inherent risk, even if implementing robust end-to-end encryption is utilized.

Users who are uncomfortable with how Private Processing works should leave it disabled.

For those who find advanced AI features useful but still need to stay in control over when data is allowed to leave their device, WhatsApp's recently launched ['Advanced Chat Privacy' feature](https://www.bleepingcomputer.com/news/security/whatsapps-new-advanced-chat-privacy-protects-sensitive-messages/) would be the ideal solution.