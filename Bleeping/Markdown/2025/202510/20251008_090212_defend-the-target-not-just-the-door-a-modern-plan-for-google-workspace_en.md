# Defend the Target, Not Just the Door: A Modern Plan for Google Workspace

![Identity management](https://www.bleepstatic.com/content/hl-images/2024/07/02/identity-cybersecurity-framework.jpg)

Modern work does not live in one app. It lives in a mesh of email, files, chat, and a web of connectors that shuttle data between them. That is why the [Salesloft/Drift incident](https://material.security/resources/the-supply-chain-is-the-new-watering-hole?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20251008-bleepingcomputer) landed with such force for Google Workspace teams. No one “hacked Google.” Attackers rode a trusted integration and ended up with exactly what they wanted: data.

In early August, the same threat actor that plundered Salesforce records via compromised OAuth tokens also used stolen Drift Email tokens to access a small number of Google Workspace mailboxes that had explicitly integrated with Drift.

On August 9, Google confirmed that activity, revoked the tokens, and disabled the integration. It was a clean illustration of how delegated access can sidestep your usual guardrails.

## When the App Graph Becomes the Attack Surface

If you have spent the past few years tightening identity, hardening MFA, and killing legacy protocols, this might feel unfair. You can do all of that and still lose ground to a third‑party token with perfectly legitimate scopes.

The uncomfortable truth is that the attack surface is now the app graph—the lattice of OAuth grants and API permissions that bind your SaaS together.

The security story is no longer about whether a login prompt fired. It is about what an integration is allowed to do once it is in.

## What Customers Actually Felt During Salesloft/Drift

We spent the days after the disclosure talking with customers. The mood was not panic; it was a measured assessment. Our threat research team built a series of detections to scan for IOCs related to the breach. Teams mapped where Drift was connected, pruned access, and rotated keys.

With Material in place, the attacker’s dwell time becomes largely irrelevant. Material’s Account Takeover Resilience protects the sensitive mailbox data at rest, so while the token could have given access to the mailbox, access to the most sensitive data still demanded a human step‑up.

That is the assume‑breach mindset in practice—accept that someone will eventually obtain valid access, and make sure the target is not readable by default.

![Salesloft Drift breach timeline](https://www.bleepstatic.com/images/news/security/m/material/oauth-apps/salesloft-drift-breach-timeline.png)

## This Was Not a One‑Off

Salesloft/Drift fits a broader pattern. The crews behind recent Salesforce intrusions are not chasing shells on endpoints; they are chasing tokens and legitimate access and taking advantage of the cover it provides.

The playbook is simple and scalable: use valid tokens, run high‑volume queries, and walk away with data. Around the same time, we saw attackers rummage through exports to find cloud secrets and pivot again.

Last year’s Snowflake wave told the same story with different logos. Credentials and tokens became industrial‑scale data theft, followed by the same cleanup grind: hunt for secrets in emails and files, rotate keys, reset tokens, and re‑baseline app access.

These attacks aren’t going away anytime soon, they’ll affect different platforms but offer similar lessons. Focusing on securing the perimeter of the cloud office is no longer sufficient–and if we’re being honest with ourselves, it hasn’t been for a while. There are simply too many ways into the emails, files and accounts within your cloud workspace. Our approach must evolve to include robust detection and response capabilities across the entire cloud office environment.

## [The Hidden Trends in Sensitive File Security](https://material.security/resources/exploring-sensitive-data-trends-what-weve-learned-from-protecting-email-and-files?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer)

Our Data Shows Sensitive Files Grew 1100%: Insights from Securing Email & Drive.

Material Security’s analysis of email and cloud data uncovered surprising trends in how sensitive information is stored, shared, and secured, offering fresh perspective on evolving risks and defenses.

[Read the Report](https://material.security/resources/exploring-sensitive-data-trends-what-weve-learned-from-protecting-email-and-files?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer)

## What “Modern” Cloud Workspace Resilience Actually Requires

So what does resilient security for Google Workspace look like in this reality? It starts with a shift in emphasis. We still prevent inbound threats, but we stop betting the business on prevention alone. We design for containment and resilience.

In practice, that means treating Workspace as critical infrastructure—its own environment with its own signals, failure modes, and blast radius—and protecting it at three layers: integrations, identities, and contents.

On integrations, the job is visibility and control. You inventory every third‑party app with access to Gmail, Drive, Calendar, and Admin APIs. You remove what you do not need. You tighten scopes on what you keep. You watch for new high‑risk grants as if they were new admin accounts, because in effect they are.

When an incident like Drift hits, you bulk‑revoke and rotate first and investigate second. If you wait for perfect evidence in logs, you are already late. The platform response to August 9 was quick; your internal response should be just as crisp.

On identities, you go beyond check‑the‑box MFA. Phishing‑resistant authentication methods are now table stakes. Legacy protocols like IMAP and POP and app specific passwords that mint long‑lived access have to go. You assume consent‑phishing and token replay will continue because they will.

Identity hardening is necessary, but it is not sufficient. Your ability to detect potentially-suspicious account behavior must go beyond simply detecting unusual logins to monitoring behavior within the environment: data access patterns, email rules, file sharing behavior, and more.

Attackers are continually evolving their evasion techniques and getting better at hiding their tracks, so being able to detect and respond to these behaviors in real-time is critical.

The decisive layer is content. If an integration or stolen session can read everything in an executive mailbox, the rest is academic. But message‑level MFA flips that script. Sensitive threads, legal archives, and regulated mail stay locked until a human proves intent and legitimacy in the moment. That single design choice turns a stolen token from catastrophic to annoying. It also buys time for the rest of your response—revocations, rotations, cleanup—without leaking secrets in the meantime.

But all those controls only matter if your team can wield them under pressure–or even better, if those controls can operate independently at machine speed. That means automating playbooks that pull from Workspace‑native telemetry to act in real time.

This means being able to revoke app tokens tied to a compromised vendor, suspend accounts behaving suspiciously, quarantine mail matching a new indicator, revoke risky Drive sharing, and require step‑up to open anything marked sensitive—as they are observed in your environment.

## How Material Security Fits

Material was built for exactly this operating reality in [Google Workspace](https://material.security/providers/google-workspace?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20251008-bleepingcomputer): we were founded with a modern approach to email and cloud office security. We make Workspace harder to misuse, even with valid tokens in hand.

We protect the content that matters most with message‑level MFA, just‑in‑time access, and frictionless control over risky Drive sharing: so a compromised integration cannot crack open your most sensitive messages and files.

We normalize the noisy signals from Gmail, Drive, and the Admin APIs and turn them into actions your team can take quickly. And we treat OAuth governance as a first‑class surface. You can see which apps have dangerous scopes, auto‑revoke what is stale, and respond broadly when the next vendor discloses a token issue.

![Defending OAuth applications](https://www.bleepstatic.com/images/news/security/m/material/oauth-apps/oauth-threats.png)

## Lessons to Keep

Assume integrations will be abused. Assume tokens will leak. Assume creative attackers will find the shortest path to the data. Then design so that those assumptions do not lead to headlines.

The Salesloft/Drift episode will be far from the last supply‑chain or token story we will read. A month from now it could be a different app, a different scope, a different set of logos.

But the common thread will be the same: defenses are strongest when they protect the target directly and accept that someone, somewhere, will eventually talk their way past the front door. Build for that world, and a stolen token becomes a speed bump instead of a breach.

**Learn more about [Material Security’s approach](https://material.security/providers/google-workspace?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20251008-bleepingcomputer) and see purpose-built cloud workspace security in action.**

_Sponsored and written by [Material Security](https://material.security/providers/google-workspace?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20251008-bleepingcomputer)._