# Email security needs more seatbelts: Why click rate is the wrong metric

![Email security seatbelts](https://www.bleepstatic.com/content/posts/2026/01/08/seatbelt-email.jpg)

So many security teams still measure phishing with the click rate. It’s easy to track and easy to put in a slide deck, but it’s also misleading. Measuring clicks is like "measuring the tide coming and going"—it fluctuates naturally and rarely predicts real-world impact.

The more meaningful question is the one most programs can’t answer: If an attacker gets into a mailbox, how much damage can they do?

That is your true maturity metric. Not completion rates, and not who remembered to hover over a URL. Even if your click rates are minuscule, all it takes is a single employee not paying attention. Not to mention the growing prevalence of inbox breaches that occur without any phishing attack at all.

## Phishing is just one possible entrance; the crisis happens next

In the incidents that keep CISOs awake, phishing is just how access is obtained. The real problem is what happens once an attacker is inside:

* They exfiltrate years of sensitive mailbox data and shared files.
* They use the mailbox to reset passwords for downstream apps.
* They use the compromised identity to phish other employees from a trusted source.

MFA isn't a silver bullet here—there are plenty of ways into a cloud workspace that bypass it entirely. If compromises are inevitable, the goal shifts from perfect prevention to resilience.

## [Secure Your Google Workspace Without the Guesswork](https://material.security/lp-cloud-office-security?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20260109-bleepingcomputer)

By implementing automated remediation workflows for your cloud workspace, Material Security handles the tedious stuff—like clawing back sensitive attachments or revoking risky third-party app permissions—without requiring manual intervention for every event.

[Request a demo](https://material.security/lp-cloud-office-security?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20260109-bleepingcomputer)

## The layered approach to resilient email security

Most email security tools on the market today focus solely on stopping inbound attacks–prevention. And this is of course critical–but it can’t be the only protection. Modern attacks move too fast, they come at too great a scale, and they’re too sophisticated. Any program relying on inbound protection alone is insufficient.

1. **Prevention** \- blocking inbound threats, fixing misconfigurations, shoring up risky file shares. Taking as many steps as possible to prevent attacks before they occur.
2. **Detect and recover** \- Having the visibility to spot signs of compromise and takeover before damage can be done. Not just unusual login behavior, but data access patterns, email forwarding rules, file sharing behavior, and other signs that an account isn’t behaving as it normally would.
3. **Containment** \- Always-on risk mitigation that reduces the blast radius and minimizes the damage an attacker can do once they breach an account. Limit their ability to exfiltrate sensitive data, move laterally, and spread the attack across the environment.

Most organizations do fairly well at prevention, though often too limited in scope. More mature organizations have some detection and response capabilities. But very few effectively manage containment.

![Prevention flowchart](https://www.bleepstatic.com/images/news/security/m/material/email-security/1-26-bleeping-computer-fig1.png)

## The missing layer: containment

Containment isn’t glamorous and doesn’t fit neatly into an existing security category. But it can also have an incredible impact on the severity of a breach.

Think of it this way: prevention is maintaining your car, driving safely, and avoiding accidents. Detection and response is making sure everyone’s OK and calling for help after an accident. Containment is the seatbelt and airbags: the safety measures that make the crash less catastrophic.

Containment isn't a slogan; it’s a set of pragmatic controls aimed at an attacker's post-compromise goals:

* **Make mailbox exfiltration harder:** Why does gaining access to an account mean unfettered access to years of PII and financial reports? Internal segmentation—requiring extra verification for sensitive messages—limits what an attacker can "loot."
* **Block lateral movement via password resets:** If you want one control that changes a breach trajectory, it’s this: intercept password reset emails and force an additional MFA challenge so a compromised mailbox doesn't become a compromised identity.
* **Fix "settings debt":** Attackers love legacy defaults. Disabling IMAP/POP (which bypasses MFA) and cleaning up app-specific passwords are basic hygiene steps that significantly shrink your blast radius.

## Moving beyond manual triage

The hurdle for most teams is time. No one has the bandwidth to manually audit every file permission or triage every user report.

If you're serious about containment, you need systems that do the boring work automatically—detecting risks and remediating them in the background—so your team only steps in when judgment is actually required.

![Containment flowchart](https://www.bleepstatic.com/images/news/security/m/material/email-security/1-26-bleeping-computer-fig2.png)

## What to measure instead

If click rate is just the tide, these metrics actually reflect your risk:

* **Mailbox lootability:** How much sensitive content is accessible without extra verification?
* **Reset-path exposure:** How many critical apps can be accessed via email-only password resets?
* **Time-to-contain:** How fast can you limit an attacker's actions once they are inside?

Email security has spent years obsessed with the front door. It’s time to start asking: if an attacker is in a mailbox right now, what can they do in the next ten minutes—and how quickly can you take that power away?

**[See how Material Security automates containment.](https://material.security/product?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20260109-bleepingcomputer)**

_Sponsored and written by [Material Security](https://material.security/product?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20260109-bleepingcomputer)._