# Malicious Rust packages on Crates.io steal crypto wallet keys

![Malicious Rust packages on Crates.io steal crypto wallet keys](https://www.bleepstatic.com/content/hl-images/2024/04/09/Rust-headpic-red.jpg)

Two malicious packages with nearly 8,500 downloads in Rust's official crate repository scanned developers' systems to steal cryptocurrency private keys and other secrets.

Rust crates are distributed through a central registry at [Crates.io](https://crates.io/), the equivalent of npm for JavaScript, PyPI for Python, and Ruby Gems for Ruby.

The malicious crates, named _faster\_log_ and _async\_println_, were published on the platform on May 25 and were downloaded 7,200 and 1,200 times, respectively.

Researchers at code security company Socket discovered the malicious crates and reported them to Crate.io. The platform removed both and suspended the publishing accounts, 'rustguruman' and 'dumbnbased', on September 24th.

## Targeting crypto secrets

Socket explains in a [report](http://socket.dev/blog/two-malicious-rust-crates-impersonate-popular-logger-to-steal-wallet-keys) that the two crates impersonated the legitimate ‘fast\_log’ crate, copying its README file, repository metadata, and retaining the real project’s logging functionality to reduce suspicion.

![Cloning the legitimate project to reduce suspicion](https://www.bleepstatic.com/images/news/u/1220909/2025/September/impersonation.jpg)

**Cloning the legitimate project to reduce suspicion**  
_Source: Socket_

The attackers exploited the log file packing functionality to scan for sensitive information.

A payload hidden in the malicious crates executed at runtime to scan the victim’s environment and project source files for the following three item types:

* Hex strings that look like Ethereum private keys
* Base58 strings that resemble Solana keys/addresses
* bracketed byte arrays that might hide keys or seeds

When the code found matches, it bundled it with the file path and line number and exfiltrated the data to a hardcoded Cloudflare Worker URL address (_mainnet\[.\]solana-rpc-pool\[.\]workers\[.\]dev_).

Socket confirmed that this endpoint was live and accepting POST requests during its tests, noting that the host is not an official Solana RPC endpoint.

Crate.io [noted in its announcement](https://blog.rust-lang.org/2025/09/24/crates.io-malicious-crates-fasterlog-and-asyncprintln/) that the malicious crates had no dependent downstream crates on the platform, and the two banned publishers had submitted no other projects, so the attack has been cleared now.

![The malicious packages appearing on the search results for the legitimate crate](https://www.bleepstatic.com/images/news/u/1220909/2025/September/search-results.jpg)

**The malicious crates appearing in search results for the legitimate project**  
_Source: Socket_

Developers who have downloaded either crate need to perform a system cleanup and move their digital assets to new wallets to prevent theft.

Before downloading a Rust crate, developers should verify the publisher's reputation. Another defense is to double-check building instructions to make sure they don't automatically fetch malicious packages.