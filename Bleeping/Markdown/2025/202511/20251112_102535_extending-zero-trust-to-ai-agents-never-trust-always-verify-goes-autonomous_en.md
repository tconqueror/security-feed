# Extending Zero Trust to AI Agents: “Never Trust, Always Verify” Goes Autonomous

![AI Zero Trust](https://www.bleepstatic.com/content/posts/2025/11/12/token-security-ai-zero-trust.jpg)

_Written by Ido Shlomo, CTO and Co-Founder, Token Security_

As organizations rapidly adopt AI assistants and autonomous agents to streamline workflows and boost efficiency, they may be unwittingly expanding their attack surface. AI agents, whether embedded in IT operations, customer service processes, or LLM-based internal tools, are acting on our behalf, making decisions, accessing sensitive data, and executing automated actions at machine speed.

The challenge? Most security frameworks weren’t built with these new agent actors in mind. We’ve spent years refining Zero Trust for users and applications, but we now need to ask a difficult question: What happens when the user is a self-directed piece of software?

The answer begins with a renewed commitment to Zero Trust to be applied not just to people and traditional services, but to every AI agent operating inside our systems.

## The Rise of Autonomous Agents

For decades, identity was a human-centric concern. Then came service accounts, containers, and APIs (machine identities) that demanded their own governance. Now we face the next evolution: agentic identities.

AI agents behave with the flexibility of humans, but at the scale and velocity of machines. Unlike static code, they learn, adapt, and make autonomous decisions. That means their behavior is harder to predict, and their access requirements change dynamically.

Yet many of these agents today operate with hard-coded credentials, excessive privileges, and no real accountability. In essence, we’ve handed the intern an admin badge and told them to move fast.

If CISOs want to [deploy AI safely and securely](https://www.token.security/blog/the-top-10-identity-centric-security-risks-of-autonomous-ai-agents?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=november-12), these agents must become first-class identities, governed with even more rigor than any employee or application.

## [Securing Agentic AI: A Free Guide from Token Security](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-30)

AI agents aren't just following instructions, they're taking action.

See how Token Security is helping enterprises redefine access control for the age of Agentic AI, where actions, intent, and accountability must align.

[Download it here](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-30)

## “Never Trust, Always Verify” for AI

Zero Trust starts with a simple principle: never trust, always verify. It assumes that users, machines and agents will be breached, and it demands that every access request, no matter the source, is authenticated, authorized, and monitored.

This philosophy applies perfectly to autonomous agents. Here's what that looks like in practice:

* **Identity-first access:** Every AI agent must have a unique, auditable identity. No shared credentials. No anonymous service tokens. Each action should be attributable.
* **Least-privilege by default:** Agents should only have the minimum access required for their function. If an agent is designed to read sales data, it shouldn’t be able to write to billing records or access HR systems.
* **Dynamic, contextual enforcement:** As agents evolve and tasks shift, their permissions must be continually reassessed. Static policies will not work. Real-time context, such as what’s being accessed, by whom, and under what conditions, should drive decision-making.
* **Continuous monitoring and validation:** Autonomous doesn’t mean unsupervised. Agents must be monitored like privileged users. Unusual behaviors like accessing a new system, transferring large volumes of data, or escalating privileges should trigger alerts or intervention.

## The Risk of Excessive Agency

AI is being rapidly adopted to drive innovation, improve efficiencies, and create competitive advantages. It doesn’t intend to cause harm, but that doesn’t mean it can’t.

Imagine a helpdesk agent with broad access to internal systems. It’s designed to automate ticket handling, but a prompt injection or misconfiguration causes it to reset user passwords, delete records, or email sensitive data externally.

That’s not theoretical, it’s happening. AI agents can hallucinate new behaviors, misunderstand instructions, or act outside their expected scope. Worse, attackers know this and are actively probing AI interfaces for ways to compromise them.

This is what we call Excessive Agency: when AI agents are given more power than they should have, and no guardrails are in place to stop them from using it.

## Building Guardrails Without Bottlenecks

Security professionals are now walking a fine line. On one hand, they want to empower innovation. On the other hand, they need to enforce discipline. That balance is particularly delicate with AI.

The solution lies in designing guardrails that scale. That means:

* **Scoped tokens and short-lived credentials:** Instead of long-term secrets, issue time-limited access tokens with narrowly defined scopes. If compromised, they expire quickly and do minimal damage.
* **Tiered trust models:** Not all actions are equal. Routine, low-risk tasks can be automated freely. High-risk operations, like deleting data or moving funds, should require human-in-the-loop approval or multi-factor triggers.
* **Apply access boundaries:** Don’t allow agents to call anything, anywhere. [Enforce strict access policies and service-level boundaries](https://www.token.security/blog/securing-agentic-ai-defining-permissions-for-unpredictable-ai-agents?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=november-12) so they stay in their lane.
* **Clear ownership:** Every agent should have an internal human owner, someone accountable for its purpose, behavior, and permissions.

With these controls in place, security becomes an enabler of AI, not an obstacle.

## A Call to CISOs: Lead with Identity

We’re entering an era where “logins” no longer belong solely to people. Agents are writing code, analyzing risk, querying data, and chatting with customers. If we treat them like afterthoughts in our identity strategy, we’re building systems on blind trust and that’s precisely what Zero Trust was meant to prevent.

CISOs must lead the charge. It starts by expanding the Zero Trust framework to explicitly include autonomous agents. From there, it requires investing in identity-first AI security architectures, monitoring tools, and access governance that can handle non-human actors. If you’re scaling your AI infrastructure, Token Security can help ensure security along the way.

**[Book a technical demo with our team](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=november-12) to see how we’re securing agentic AI without sacrificing speed.**

Security isn’t about stopping AI. It’s about enabling it safely, predictably, and with accountability.

_Sponsored and written by [Token Security](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=november-12)._