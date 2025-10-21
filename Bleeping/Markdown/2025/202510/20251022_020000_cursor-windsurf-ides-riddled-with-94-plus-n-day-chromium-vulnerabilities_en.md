# Cursor, Windsurf IDEs riddled with 94+ n-day Chromium vulnerabilities

![Cursor, Windsurf IDEs riddled with 94+ n-day Chromium vulnerabilities](https://www.bleepstatic.com/content/hl-images/2025/01/31/Chromium-headpic.jpg)

The latest releases of Cursor and Windsurf integrated development environments are vulnerable to more than 94 known and patched security issues in the Chromium browser and the V8 JavaScript engine.

An estimated 1.8 million developers, the userbase for the two IDEs, are exposed to the risks.

Ox Security researchers explain that both development environments are built on old software that includes outdated versions of the open-source Chromium browser and Google's V8 engine.

They say that Cursor and Windsurf rely on old versions of VS Code that include old releases of the Electron framework for building cross-platform apps using web technologies (HTML, CSS, JavaScript).

"Since Electron embeds Chromium and V8, this means the IDEs rely on outdated Chromium and V8 engines, exposing them to vulnerabilities that have already been patched in newer versions," the researchers say in a [report](http://www.ox.security/blog/94-Vulnerabilities-in-Cursor-and-Windsurf-Put-1-8M-Developers-at-Risk/) shared with BleepingComputer.

The researchers say that Cursor and Windsurf are vulnerable to at least 94 vulnerabilities present in the Chromium builds they use.

Despite the security issue being disclosed responsibly since October 12, the risks are still present as Cursor considered the report "out of scope" and Windsurf did not respond.

![Inheriting n-days from older Electron apps](https://www.bleepstatic.com/images/news/u/1220909/2025/October/image(1).jpg)

**Inheriting n-days from older Electron apps**  
_Source: Ox Security_

## Chrome risks on the IDE

Cursor and Windsurf are AI-powered code editors forked from Visual Studio Code. They integrate large-language models (LLMs) to help developers write software more easily and quickly.

They are distributed as Electron apps, meaning an application runtime that packages a specific Chromium build for rendering web content, and includes the browser's V8 JavaScript engine in the binary.

The specific Electron release pins a Chromium + V8 version, and if the vendor doesn't upgrade it, flaws fixed in every subsequent release become exploitable risks in the IDE.

Ox Security demonstrated that it is possible to exploit the Maglev JIT integer overflow described in CVE-2025-7656 through a deeplink, which executes Cursor and injects a prompt instructing its browser to visit a remote URL hosting an exploit payload.

The remote page serves JavaScript that triggers CVE-2025-7656 exploitation, causing denial of service by crashing the renderer.

Nir Zadok and Moshe Siman Tov Bustan of Ox Security demonstrated their findings by targeting Cursor IDE with an exploit for CVE-2025-7656, an integer overflow vulnerability in Google Chrome's V8 engine [fixed](https://www.bleepingcomputer.com/news/security/google-fixes-actively-exploited-sandbox-escape-zero-day-in-chrome/) on July 15.

The proof-of-concept exploit caused Cursor to enter a denial-of-service condition (crash), as shown in the video below:

However, Ox Security notes that arbitrary code execution is also possible in real-world attacks.

An adversary would have multiple options to trigger the vulnerability. The researchers say that an attacker could use a malicious extension to trigger the exploit or inject the exploit code into documentation and tutorials.

Hackers could also rely on classic phishing attacks or leverage poisoned repositories by planting malicious code in README files that are previewed in the IDE.

![Overview of the attack](https://www.bleepstatic.com/images/news/u/1220909/2025/October/image%20(1).jpg)

**Overview of the attack**  
_Source: Ox Security_

Ox Security notes that the exploit does not work on the latest VS Code, which is regularly updated and addresses all known bugs.

Upon receiving the proof-of-concept exploit, Cursor dismissed the report by saying that self-inflicted DoS is out of scope.

But the researchers noted that this stance ignores the more severe exploitation potential of the flaw, including memory-corruption primitives, or even the broader set of unpatched CVEs in the Electron apps used.

"Since their last Chromium update on 2025-03-21 for version 0.47.9 since Chromium 132.0.6834.210 was out, at least 94 known CVEs have been published. We've weaponized just one. The attack surface is massive," explains Ox Security.

BleepingComputer has contacted both Cursor and Windsurf asking for a comment on Ox Security's report, but we have not heard back by publication time.