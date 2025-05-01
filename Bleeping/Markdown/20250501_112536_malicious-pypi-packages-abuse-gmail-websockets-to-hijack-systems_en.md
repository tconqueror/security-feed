# Malicious PyPI packages abuse Gmail, websockets to hijack systems

![Gmail](https://www.bleepstatic.com/content/hl-images/2023/10/03/Gmail_headpic.jpg)

Seven malicious PyPi packages were found using Gmail's SMTP servers and WebSockets for data exfiltration and remote command execution.

The packages were discovered by [Socket's threat research team](https://socket.dev/blog/using-trusted-protocols-against-you-gmail-as-a-c2-mechanism), who reported their findings to the PyPI, resulting in the removal of the packages.

However, some of these packages were on PyPI for over four years, and based on [third-party download counters](https://pepy.tech/), one was downloaded over 18,000 times.

Here's the complete list shared by Socket:

* Coffin-Codes-Pro (9,000 downloads)
* Coffin-Codes-NET2 (6,200 downloads)
* Coffin-Codes-NET (6,100 downloads)
* Coffin-Codes-2022 (18,100 downloads)
* Coffin2022 (6,500 downloads)
* Coffin-Grave (6,500 downloads)
* cfc-bsb (2,900 downloads)

The 'Coffin' packages appear to be impersonating the [legitimate Coffin package](https://pypi.org/project/Coffin/) that serves as a lightweight adapter for integrating Jinja2 templates into Django projects.

The malicious functionality Socket discovered in these packages centers on covert remote access and data exfiltration through Gmail.

The packages used hardcoded Gmail credentials to log into the service's SMTP server (smpt.gmail.com), sending reconnaissance information to allow the attacker to remotely access the compromised system.

As Gmail is a trusted service, firewalls and EDRs are unlikely to flag this activity as suspicious.

After the email signaling stage, the implant connects to a remote server using WebSocket over SSL, receiving tunnel configuration instructions to establish a persistent, encrypted, bidirectional tunnel from the host to the attacker.

Using a 'Client' class, the malware forwards traffic from the remote host to the local system through the tunnel, allowing internal admin panel and API access, file transfer, email exfiltration, shell command execution, credentials harvesting, and lateral movement.

Socket highlights strong indicators of potential cryptocurrency theft intent for these packages, seen in the email addresses used (e.g., blockchain.bitcoins2020@gmail.com) and similar tactics having been used in the past to steal Solana private keys.

If you have installed any of those packages in your environment, remove them immediately and rotate keys and credentials as needed.

A related report published almost simultaneously by [Sonatype](https://www.sonatype.com/blog/revived-cryptojs-library-is-a-crypto-stealer-in-disguise) researcher and fellow BleepingComputer reporter Ax Sharma focuses on a crypto-stealing package named 'crypto-encrypt-ts,' found in npm.

The package masquerades as a TypeScript version of the popular but now unmaintained 'CryptoJS' library while exfiltrating cryptocurrency wallet secrets and environment variables to a threat actor-controlled Better Stack endpoint.

The malicious package, which persists on infected systems via cron jobs, only targets wallets with balances that surpass 1,000 units, attempting to snatch their private keys.

The package was downloaded nearly 2,000 times before being reported and removed from npm.