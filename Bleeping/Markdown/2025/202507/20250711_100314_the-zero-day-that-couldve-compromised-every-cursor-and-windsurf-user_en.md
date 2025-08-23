# The zero-day that could've compromised every Cursor and Windsurf user

![Code editor and developer platform logos](https://www.bleepstatic.com/content/posts/2025/07/11/koi-header-image.jpg)

A security researcher from [Koi Security](https://www.koi.security/?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx) stumbled upon a critical zero-day buried deep in the infrastructure powering today’s AI coding tools. Had it been exploited, a non-sophisticated attacker could’ve hijacked over 10 million machines with a single stroke.

AI coding assistants like Cursor and Windsurf have exploded in popularity, promising supercharged productivity for developers around the world. Behind their sleek interfaces lies a shared foundation: community-built VS Code forks and an open marketplace of extensions that powers the magic. But, with this new wave of developer tooling comes a dangerous blind spot.

**Dubbed VSXPloit:** A single overlooked flaw in OpenVSX - a critical component in the developer supply chain - allowed silent, full-system compromise on any machine running a VS Code fork. One bug. Total control.

Let’s dive in.

Today’s AI-powered editors heavily rely on extensions to deliver their most basic functionality. Features like syntax highlighting, linting, and debugging aren’t hardcoded into the editor - they are provided by extensions.

Each of these extensions runs with full privileges on the developer’s machine. This in turn means that a single compromised extension can lead to full machine takeover of anyone who installs it.

![Open VSX impact](https://www.bleepstatic.com/images/news/security/k/koi/zero-day-ai/open-vsx.jpg)

This exact nightmare scenario is what security researcher Oren Yomtov from [Koi Security](https://www.koi.security/?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx), a company providing a platform for securing software provisioning and extensions, stumbled upon.

[In a recent post](https://blog.koi.security/marketplace-takeover-how-we-couldve-taken-over-every-developer-using-a-vscode-fork-f0f8cf104d44?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx) Yomtom explains that while examining the build process behind OpenVSX, the open-source marketplace powering extensions for tools like Cursor, Windsurf, VSCodium, and others, he discovered a critical flaw.

The vulnerability allowed any attacker, not only to gain control over a single extension, but an supply chain armageddon, gaining full control over the entire marketplace.

Given this flaw, any attacker could push malicious updates under the trusted @open-vsx account. At first, Yomtov assumed it had to be a mistake, this code had been running for years, used by tens of millions. But when he recreated the attack in his lab, the simulation worked flawlessly.

What seemed unthinkable was suddenly very real: a silent, full-scale security disaster was sitting in plain sight.

## [Secure Your Dev Environment from Hidden Extension Threats](https://www.koi.security/get-a-demo?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx)

Learn how Koi helps organizations discover, assess, and govern risky extensions across VSCode, OpenVSX, Chrome, and other marketplaces.

Gain full visibility and protect your development supply chain.

[Request a Demo](https://www.koi.security/get-a-demo?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx)

## The Vulnerability: A Variation On The Classic “Pwn Request”

To understand how the vulnerability worked, you first need to understand how extensions make their way into OpenVSX in the first place.

If you want to publish an extension to Open VSX, you have two options:

1. Upload it to Open VSX yourself
2. Request an extension to be auto-published by creating a pull request that adds the extension to the list in the extensions.json file

![Docs](https://www.bleepstatic.com/images/news/security/k/koi/zero-day-ai/auto-publish-request.jpg)

“The nightly build is where the problem lies,” says Yomtov.

Every night, OpenVSX runs an automated process that fetches the latest versions of community-submitted extensions, builds them, and publishes them to the marketplace. It’s meant to make life easier for developers, but in this case, it introduced a critical flaw.

To get an extension auto-published, all a developer has to do is submit a simple pull request adding it to a public list. From there, OpenVSX takes over: it pulls the code, installs the dependencies, builds the extension, and publishes it using a powerful secret token that belongs to the trusted @open-vsx account.

This token was meant to stay hidden, only seen by trusted infrastructure. Unfortunately, due to how the build process runs arbitrary code from public repositories, any extension author could craft a malicious update that **silently captures the token**.

What’s even more alarming is that they wouldn’t need to submit a malicious extension directly. They could have hidden their code inside a dependency, or even a dependency-of-a-dependency, and the system would have executed it automatically during the nightly build. From there, stealing the token was trivial.

And with that token in hand, an attacker wouldn’t just control their own extension. They could publish updates, overwrite existing ones, and silently hijack the entire marketplace.

## The Impact: A Supply-Chain Nightmare That Exposed Millions of Developers

With access to the @open-vsx account’s token, an attacker could have created a world wide supply chain nightmare. “That token is a super-admin credential,” explains Yomtov. “It can publish new extensions, overwrite existing ones, and impersonate any publisher in the ecosystem.”

From that point on, the damage becomes almost effortless. Every time a developer installs an extension or their editor auto-updates one in the background, which continuously happens, the attacker’s payload would be silently delivered to their machine. No alerts. No prompts. No suspicion. Full takeover.

And what could that payload do? “Pretty much anything,” says Yomtov. Extensions in VS Code and its forks run as Node.js processes, which means they can access files, launch other programs, make network requests, and execute arbitrary code.

A malicious update to a popular extension, say, the Python plugin, could quietly install a keylogger, steal browser cookies, swipe source code, infect builds, or backdoor entire development pipelines.

There have been isolated cases of rogue VS Code extensions stealing SSH keys or crypto wallets. But this wouldn’t be one bad actor slipping through the cracks. This would be full-scale takeover, supply-chain compromise at ecosystem scale. Like SolarWinds, but for developer tools.

While the impact would be most severe for desktop editors like Cursor, Windsurf, and VSCodium, even browser-based environments such as Gitpod or StackBlitz could be affected, depending on how deeply integrated the compromised extensions are.

## So What Can You Do About It?

We asked Yomtov what users and organizations should take away from this incident. His answer was blunt: “Assume every extension is untrusted until proven otherwise.”

Extensions may feel like harmless add-ons, but under the hood, they’re powerful software components, often written by individuals, running with full permissions, and automatically updated without oversight.

“It’s no different than pulling in a package from npm or PyPI, and generally even worse” Yomtov says. “If you wouldn’t blindly trust a GitHub repo with root access to your machine, you shouldn’t trust an extension either.”

To protect ourselves, Yomtov recommends organizations treat extensions as part of their attack surface and apply the same discipline they use for any other dependency. That means:

1. **Maintaining a real inventory** of what’s installed, across which machines, and by whom
2. **Assessing risk** based on who built the extension, how it’s maintained, and what it actually does
3. **Enforcing clear policies** around what’s allowed, and taking action when something drifts out of bounds
4. **Monitoring continuously**, since extensions can update silently and introduce new risks overnight

Koi’s research team continues to [find both vulnerable and actively malicious extensions](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-with-17m-installs-found-on-web-store/) - not just in OpenVSX,or Microsoft’s marketplace, even in other extension marketplaces like the Chrome Web Store.

“The ecosystem has grown faster than the guardrails,” says Yomtov. “Until that changes, the safest assumption is zero trust. Every extension is a potential backdoor unless you’ve reviewed and are watching it.”

Yomtov and the team at [Koi Security](https://www.koi.security/?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx) responsibly disclosed the vulnerability to the Eclipse Foundation, which maintains the OpenVSX project. Over the following weeks, they worked closely with the maintainers to validate the issue, design a robust fix, and ensure the patch was properly implemented and deployed.

Thanks to this collaboration, the vulnerability has been closed and the marketplace is once again safe for the millions of developers who rely on it daily.

But the incident serves as a wake-up call - even trusted infrastructure needs constant scrutiny, especially when it holds the keys to the entire development ecosystem.

**Learn how Koi helps organizations discover, assess, and govern risky extensions across VSCode, OpenVSX, Chrome, and other marketplaces**

[**Chat with us.**](http://www.koi.security/?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx)

_Sponsored and written by [Koi Security](https://koi.security?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx)._