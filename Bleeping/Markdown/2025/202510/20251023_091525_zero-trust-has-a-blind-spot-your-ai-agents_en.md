# Zero Trust Has a Blind Spot—Your AI Agents

![AI agents](https://www.bleepstatic.com/content/posts/2025/10/23/robots-ai-token-security.jpg)

_By Ido Shlomo, CTO and Co-Founder, Token Security_

Agentic AI has arrived. From custom GPTs to autonomous copilots, AI agents now act on behalf of users and organizations, or even act as just another teammate, making decisions, accessing systems, and invoking other agents without direct human intervention.

But, with this new level of autonomy comes an urgent security question: If AI is doing the work, how do we know when to trust it?

In traditional systems, Zero Trust architecture assumes no implicit trust, where every user, endpoint, workload, and service must continuously prove who they are and what they’re authorized to do.

However, in the agentic AI world, these principles break down fast. AI agents often operate under inherited credentials, with no registered owner or identity governance.

The result is a growing population of agents that may look trusted but actually are not, [one of many risks of autonomous AI agents in your infrastructure](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23).

To close this gap, organizations must apply the NIST AI Risk Management Framework ([AI RMF](https://www.nist.gov/itl/ai-risk-management-framework)) through a Zero Trust lens with identity at the core. Identity has to be the root of trust for AI, and without it, everything else (access controls, auditability, accountability) falls apart.

## Identity Risk in the Agentic Era

NIST’s AI RMF provides a high-level guide to managing AI risk across four functions: Map, Measure, Manage, and Govern. But interpreting these through the lens of identity governance reveals where AI-specific risks are hiding.

Take the “Map” function. How many AI agents are currently active in your organization? Who created them and who owns them? What access do they have to enterprise systems and services? Most security teams can’t answer these questions today.

AI agents are being spun up on internal dev workstations, production accounts, or cloud sandboxes with little oversight.

Shadow agents often inherit over-permissioned credentials or authenticate using a long-lived secret. Many persist with no owner, no rotation policy, no permissions right-sizing, and no monitoring.

These "orphaned agents" violate Zero Trust by default. They operate without a trusted identity, meaning the system is trusting entities it cannot verify.

## [Securing Agentic AI: Rethinking Permissions for Autonomous Systems](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23)

AI agents are now taking action—not just following instructions.

Learn how Token Security is helping enterprises redefine access control for the age of Agentic AI, where actions, intent, and accountability must align.

[Download the Free Guide](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23)

## Why Identity Must Come First

To fix this, security teams must start with the first principle of Zero Trust: the right permissions and credentials need to be applied before granting trust. This applies not only to users, but to AI agents as well.

Every AI agent should have:

* A unique, managed identity
* A clear owner or responsible team
* An intent-based permission scheme, tied to what access it actually needs
* A lifecycle: created, reviewed, rotated, and retired like any other identity

This transforms agentic AI from an ungoverned risk to a governed entity. [Identity becomes the gatekeeper for everything the AI agent touches](https://www.token.security/blog/securing-agentic-ai-why-everything-starts-with-identity?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23), whether it’s reading sensitive data, issuing system commands, or invoking another agent.

## Applying the NIST Framework: Identity-Driven Zero Trust

Here’s how each NIST AI RMF function can be implemented through an identity-centric Zero Trust approach:

**Map:** Discover and inventory all AI agents, including custom GPTs, copilots, and MCP servers. Flag agents with missing or unclear ownership. Map what each agent can access and link that to its intended purpose. Monitor agent behavior continuously, not just for model outputs but for identity behavior. Is the agent accessing systems it has never used before? Has its credential expired, but still works? Anomalous identity use is an early warning sign of compromise or drift.

**Manage:** Right-size permissions for every AI identity. Use intent-based access to ensure least privilege is enforced dynamically. Revoke stale credentials, rotate secrets, and remove agents that no longer serve a purpose.

**Govern:** Apply identity governance to AI agents with the same rigor used for humans. Assign owners, enforce lifecycle policies, and audit identity use across your multi-agent ecosystem. If an agent takes a sensitive action, you should be able to answer immediately: Who authorized this, and why?

## From Blind Spots to Proven Trust

The risks are real. Orphaned AI agents can serve as backdoors for attackers. Over-permissioned agents can exfiltrate sensitive data in seconds. And when a breach occurs, the audit trail is often nonexistent. Without clear identities, security teams are left struggling to pinpoint the problem: “We don’t know who did it.”

Identity can’t just be another layer in AI security. It needs to be the foundation. It aligns with Zero Trust by ensuring every AI agent action is tied to a known, governed entity. And it enables secure AI adoption at scale because trust in AI must be earned, not assumed.

AI agents may be autonomous, but their trust must be built on accountability. Identity is how we get there and establish that trust. By embedding identity controls into every phase of AI deployment (discovery, permissioning, monitoring, and governance), organizations can eliminate blind spots and enforce Zero Trust where it matters most.

It’s time we start applying it to AI agents to ensure a stronger security and compliance posture.

**If you’re ready to map your agentic AI and gain control of your agents, [book a demo of Token Security](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23) to see how our platform gets it done.**

_Sponsored and written by [Token Security](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23)._