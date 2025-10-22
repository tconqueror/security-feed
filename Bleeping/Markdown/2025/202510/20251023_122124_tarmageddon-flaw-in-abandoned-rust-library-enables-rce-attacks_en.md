# TARmageddon flaw in abandoned Rust library enables RCE attacks

![Hacker](https://www.bleepstatic.com/content/hl-images/2024/05/07/hacker-box.jpg)

A high-severity vulnerability in the now-abandoned async-tar Rust library and its forks can be exploited to gain remote code execution on systems running unpatched software.

Tracked as [CVE-2025-62518](https://nvd.nist.gov/vuln/detail/CVE-2025-62518), this logic flaw results from a desynchronization issue that allows unauthenticated attackers to inject additional archive entries during TAR file extraction.

This occurs specifically when processing nested TAR files with mismatched ustar and PAX extended headers, causing the parser to jump into the file content and mistake it for tar headers, leading to the extraction of attacker-supplied files.

Edera, the cybersecurity company that discovered the vulnerability and dubbed it [TARmageddon](https://edera.dev/stories/tarmageddon), explains that threat actors can exploit it to overwrite files in supply chain attacks by replacing configuration files and hijacking build backends.

This security flaw affects not only projects using async-tar but also tokio-tar, an extremely popular fork with [over 7 million downloads on crates.io](https://crates.io/crates/tokio-tar) that has also been abandoned.

While the active forks have already been [patched](https://github.com/edera-dev/cve-tarmageddon/tree/main/patches), Edera says it's not possible to accurately estimate the impact of this vulnerability due to the widespread nature of its forks, including tokio-tar.

"Due to the widespread nature of tokio-tar in various forms, it is not possible to truly quantify upfront the blast radius of this bug across the ecosystem," [said Edera](https://edera.dev/stories/tarmageddon).

"While the active forks have been successfully patched (see also Astral Security Advisory), this disclosure highlights a major systemic challenge: the highly downloaded tokio-tar remains unpatched."

The TARmageddon vulnerability affects many widely used projects, including Binstalk, Astral's uv Python package manager, the wasmCloud universal application platform, liboxen, and the open-source testcontainers library.

While some of the downstream projects Edera contacted have announced plans to remove the vulnerable dependency or switch to a patched fork, others have not responded, and more projects that haven't been notified are likely also using it.

Edera advises developers to either upgrade to a patched version or immediately remove the vulnerable tokio-tar dependency. They should switch to the actively maintained astral-tokio-tar fork if their projects depend on the vulnerable tokio-tar library. Edera's async-tar fork (krata-tokio-tar) will be archived to reduce confusion in the ecosystem.