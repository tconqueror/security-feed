# From ClickFix to MetaStealer: Dissecting Evolving Threat Actor Techniques

![Huntress Labs Tradecraft Tuesday](https://www.bleepstatic.com/content/posts/2025/09/09/huntress-tradecraft-header.png)

_By John Hammond, [Alden Schmidt](mailto:alden.schmidt@huntresslabs.com), [Lindsey Welch](mailto:lindsey.odonnell-welch@huntresslabs.com)_

During the past fifteen business days, Huntress analysts have observed increased threat activity involving several notable techniques. One case involved a malicious AnyDesk installer, which initially mimicked a standard ClickFix attack through a fake Cloudflare verification page but then utilized Windows File Explorer and an MSI package masked as a PDF to deploy MetaStealer malware.

Additionally, two incidents involving the Cephalus ransomware variant were detected.

This ransomware distinguishes itself by employing DLL sideloading through a legitimate SentinelOne executable, SentinelBrowserNativeHost.exe, to launch the payload. These recent findings highlight the ongoing evolution in threat actor tradecraft, combining established social engineering methods with more technically advanced infection chains and evasive deployment strategies.

ClickFix attacks have been ticking up for over a year now, as attackers find success in tricking users into executing malicious code on their computers using CAPTCHA-based lures. We’ve seen quite a bit of these types of attacks on our end, but we’ve also seen threat actors adopting ClickFix-esque techniques in attacks that don’t follow the exact ClickFix playbook.

Recently, our very own [John Hammond](https://www.huntress.com/authors/john-hammond) received an email from someone who had come across a fake AnyDesk installer while searching for the AnyDesk remote tool. 

While early indicators of the attack look like it would turn into another ClickFix scam, a little bit of digging shows a unique infection chain that involves a fake Cloudflare Turnstile lure, the Windows search protocol, and an MSI package disguised as a PDF that cleverly grabs the victim’s hostname.

The attack ultimately aims to drop MetaStealer, a commodity infostealer that’s been around since 2022 and is known for harvesting credentials and stealing files.

## ClickFix, FileFix, and other ‘fix’ variants

First, a quick primer on the [widely used ClickFix technique](https://www.instagram.com/reel/DL8a95tB5DN/). The premise of ClickFix is that threat actors convince users to “fix” a purported issue, usually with a CAPTCHA on a webpage that they arrive on via a phishing message, or otherwise.

The “solution” is copying and pasting a command fed to victims via an attacker-controlled prompt, which quietly kicks off the attack chain.

While the classic ClickFix attack tricks users to paste and run commands in their Windows Run dialog box or via PowerShell, other variants of the attack have also sprung up that take a different approach. A few months ago, attackers turned to a similar technique, dubbed FileFix, which involves Windows File Explorer instead of the Run dialog box.

We’ve seen a number of incidents that stem from ClickFix attacks. In the August 26 incident shown in Figure 1 below, for instance, we responded to an attack where a user executed a malicious command given to them via a fake Cloudflare Turnstile, which is Cloudflare’s verification tool meant to replace CAPTCHAs for weeding out bots.

This then downloaded and installed an infostealer. 

Closer investigation revealed that the victim had visited the landing page **teams-one\[.\]com**. This page showed a Cloudflare Turnstile and marked the beginning stage of the ClickFix attack. 

![Another attack involving a Cloudflare Turnstile - this time an actual ClickFix attack](https://www.bleepstatic.com/images/news/security/h/huntress-labs/clickfix/fake-cloudflare-captcha.jpg)

**Figure 1: Another attack involving a Cloudflare Turnstile - this time an actual ClickFix attack**?????

Though there are similarities that we’ll outline below, the run-of-the-mill ClickFix incident demonstrated above differs significantly from the MetaStealer attack that we recently came across.

## [Learn to Wreck Hackers at Tradecraft Tuesday with Huntress](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=in%5Farticle)

Hacker tradecraft’s evolving daily, so let’s break it down on Tradecraft Tuesday!

Join us monthly for an in-depth look at attacker tradecraft—no sales or product talk involved. Sign up for the series today or catch up on previous episodes. No tricks, just tradecraft.

[Register for Tradecraft Tuesday](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=in%5Farticle)

## A ClickFix-turned-not-fix attack: what we saw

The initial link for the fake AnyDesk installer redirects users to **https\[://\]anydeesk\[.\]ink/download/anydesk\[.\]html**, which displays a Cloudflare Turnstile - and a very questionable UI.

The page purports to support “Secure Access Verification”, prompting the user to click a single button on the Cloudflare Turnstile to “verify you are human.”

![The initial link that redirects users to a fake Cloudflare Turnstile](https://www.bleepstatic.com/images/news/security/h/huntress-labs/clickfix/secure-access-verification-captcha.jpg)

**Figure 2: The initial link that redirects users to a fake Cloudflare Turnstile**

 A quick look at the underlying HTML for the webpage (using View Source) is shrouded by obfuscated JavaScript, but that can be easily unraveled with JavaScript deobfuscation tools available in the browser tools console.

This reveals the actual source code - and reveals the **window.location.href** value to be **https\[://\]verification\[.\]anydeesk\[.\]ink/reCAPTCHA-v2\[.\]php**.

Up to this point, this has all the tell-tale signs of a ClickFix campaign: it involves a classic human verification social engineering piece, and sets the end user up to click on a box. 

However, when the victim clicks the box, the prompts in this attack lead to Windows File Explorer, Windows’ file management tool, as opposed to the Windows Run dialog box as we have seen with ClickFix.

This is more indicative of a FileFix attack—but this attack still isn’t strictly FileFix, where victims are prodded to launch the address bar in Windows File Explorer (using a **Ctrl+L** and **Ctrl+V** combination to paste a PowerShell command that was automatically copied to their clipboard).

Instead, in this attack, the PHP above redirects users to the Windows protocol handler (**search-ms** URI), a legitimate feature enabling applications to kick off specific search queries in Windows File Explorer. 

**Figure 3: The attack chain redirects users to a prompt asking them to Open Windows File Explore**

The specific Windows File Explorer “Search” redirect location can be seen in Figure 4 below, which displays the name for a custom search query as part of the **search-ms** URI protocol. 

**Figure 4: The displayname parameter for search-ms reveals the next phase of the attack**

As seen in Figure 5 below, Windows File Explorer then directs the victim to an attacker-controlled SMB share, essentially a remote file share allowing clients to access files on a remote server over a network.

Here, victims are presented with a Windows shortcut LNK file – however, this LNK file is disguised as a PDF file called **Readme Anydesk.pdf**.

**Figure 5: A Windows shortcut file disguised as a decoy AnyDesk PDF** 

## Fake PDF lure: snagging victim hostnames

As you can see below, the LNK file’s payload is:

Once clicked, this file’s payload kicks off a few processes. Here, **cmd.exe** starts the automatic download of a legitimate AnyDesk installer on Microsoft Edge, possibly as a way to avoid suspicion for the victim.

Meanwhile, it also begins a download for another purported “PDF,” which is downloaded from **chat1\[.\]store** and dropped into the temporary directory. 

Notably, this fake PDF is configured to grab the **%COMPUTERNAME%** environment variable as a subdomain. Subdomains don’t need to know the user’s hostname ahead of time, so this is a clever way for the attacker to nab that information from the victim. 

The fake PDF is then installed by **msiexec** (revealing that it’s actually an MSI package) and the **cmd.exe** process is then killed.

Upon closer inspection of **chat1\[.\]store** (reached through a **curl** user agent), we can see everything from the MSI package, including files that would have been triggered as part of the attack chain.

The two important files in the MSI package are a DLL (**CustomActionDLL**) and a CAB archive (**Binary.bz.WrappedSetupProgram**) which contains several other files. The CAB file contains two additional malicious files: **1.js** which is responsible for cleaning up the infection chain, and **ls26.exe** which is the MetaStealer dropper. 

The MetaStealer file (**ls26.exe**) is a very large binary and is protected with Private EXE Protector. Upon further inspection, the executable reveals the same types of behavior that we’ve seen in known samples of MetaStealer, such as stealing from crypto wallets. 

## ClickFix variants and lessons learned

ClickFix, FileFix, and even this alternate-ClickFix attack we recently found show the power of blending [social engineering](https://www.huntress.com/social-engineering-guide?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle) with mundane processes, like CAPTCHAs or other verification tools.

Additionally, these types of attacks that require some level of manual interaction from the victim, as they work to “fix” the purported broken process themselves, work in part because they can potentially circumvent security solutions. 

The guidance for organizations in regards to ClickFix has previously centered around taking measures like disallowing users to use the Windows Run dialog box if it’s not needed for everyday tasks.

While this can be effective against traditional ClickFix attacks, the variants like the one above show that threat actors are continuing to move the needle in their infection chains, throwing a wrench into detection and prevention.

Organizations should take additional measures, including educating users about the lures linked to ClickFix-like attacks. Users should be trained on spotting CAPTCHAs that prompt them to copy and paste into the Run dialog box, or redirect to Windows File Explorer. 

## Maintain Situational Awareness—Register for Tradecraft Tuesday

Tradecraft Tuesday provides cybersecurity professionals with an in-depth analysis of the latest threat actors, attack vectors, and mitigation strategies.

Each weekly session features technical walkthroughs of recent incidents, comprehensive breakdowns of malware trends, and up-to-date indicators of compromise (IOCs).

Participants gain:

* Detailed briefings on emerging threat campaigns and ransomware variants
* Evidence-driven defense methodologies and remediation techniques
* Direct interaction with Huntress analysts for incident response insights
* Access to actionable threat intelligence and detection guidance

**[Register for Tradecraft Tuesday →](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=inline)**

Advance your defensive posture with real-time intelligence and technical education specifically designed for those responsible for safeguarding their organization’s environment.