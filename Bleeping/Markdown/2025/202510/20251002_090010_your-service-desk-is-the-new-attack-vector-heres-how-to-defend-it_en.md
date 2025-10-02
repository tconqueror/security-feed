# Your Service Desk is the New Attack Vector—Here's How to Defend It.

![FastPassCorp header](https://www.bleepstatic.com/content/posts/2025/09/30/fastpass-social-engineering-help-desk.jpg)

## The service desk is the new perimeter

Attackers aren’t picking locks—they’re picking people. The fastest way inside many enterprises is still the service desk. Threat actors like Scattered Spider have turned social engineering into a science, and your help desk agents are their primary target.

One convincing phone call can turn a routine password reset into full domain access.

The MGM Resorts and Clorox incidents showed how devastating one successful social-engineering call can be, with a nine-figure business impact and weeks of disruption.

That’s not a fluke; it’s the playbook.

## Training Helps, Controls Decide

Yes, agent training matters. No, it won’t save you on its own. Social engineers are specialists at exploiting helpful humans under time pressure.

Scripts, “common sense,” and ad-hoc challenge questions break down when an attacker is calm, prepared, and persuasive.

If your last line of defense is an overworked agent making a judgment call, you’ve already lost.

**Bottom line:** user verification must be a **security-owned workflow**, not an agent-owned conversation.

## [Lock Down the Help Desk with a NIST-Aligned Workflow](https://www.fastpasscorp.com/best-practices-ivm-user-verification-guide/?utm%5Fsource=article&utm%5Fmedium=webpage&utm%5Fcampaign=bleepingcomputer)

See how to design role-based, points-based verification that fits your ServiceNow flow and stops social engineering without slowing support.

Download our comprehensive guide and start building a more resilient help desk today

[See the Guide](https://www.fastpasscorp.com/best-practices-ivm-user-verification-guide/?utm%5Fsource=article&utm%5Fmedium=webpage&utm%5Fcampaign=bleepingcomputer)

## A workflow approach to help desk user verification

Shift verification out of the agent’s head and into a formal **IT-security workflow** that’s consistent, logged, and enforced:

* **Mandatory controls:** Agents **never** handle or view credentials. The workflow does.
* **Role-based verification:** Align the depth of checks to the risk of the persona (execs, admins, finance, contractors, etc.). High-risk roles demand stronger proofs.
* **Points-based flexibility:** Real life happens—phones die, travel breaks MFA. Use multiple proof types with scores that add up to a pass/fail threshold.
* **ITSM integration:** Keep the agent in their normal tool (e.g., ServiceNow). Tickets launch the verification flow automatically and return the result + telemetry back to the ticket.
* **Reduce Agent Stress and Error:**  A formal workflow removes the burden of being a security expert from your agents. They no longer have to make high-stakes judgment calls, leading to faster, more consistent, and less stressful ticket handling. This isn't just better security; it's better service.

## What “good” looks like (NIST-aligned profiles)

Most of our customers start with three verification profiles mapped to user risk and available factors. It could be like this:

* **Profile 1 (Standard User - Low Assurance): For routine requests like a password reset for a standard employee.**  
   * Method: A push notification to their registered corporate authenticator app (Okta Verify, MS Authenticator). This is fast, familiar, and leverages existing infrastructure.
* **Profile 2 (Privileged User / Sensitive Action - High Assurance): For domain admins, finance controllers, or anyone requesting a sensitive change.**  
   * Method: Requires two distinct factors. For example: Successful authenticator push notification  
    AND  
    a one-time code sent to the corporate email address on file.  
    OR answering a question based on a non-public attribute from the HRIS system (e.g., "What is your employee ID number?").
* **Profile 3 (Contingency / MFA Failure - Flexible Assurance): For when the user has lost their primary MFA device.**  
   * Method: The user must achieve 100 points from a menu of options, preventing them from being fully locked out.  
         * One-time code to personal email on file: (50 points)  
         * One-time code to personal phone number on file: (50 points)  
         * Verification of device serial number from MDM: (60 points)  
         * answering a question based on a non-public attribute from the HRIS system (e.g., "What is your employee ID number?"). (50 points)

**Tip:** If MFA isn’t universally available, prefer enterprise-verified data (HRIS/IDP attributes, device posture, geo/behavior signals) over guessable personal trivia. Keep a short, vetted list and retire any question that leaks or shows up in breaches.

![Adaptive identity verification workflow](https://www.bleepstatic.com/images/news/security/f/fastpass/social-engineering-help-desk/BottomImage.jpg)

## Detect attacks early, document everything

When verification lives inside the workflow, you get security outcomes “for free”. These are some of the extra benefits realized by our customers:

* **Early warning:** Spikes in failed verifications against the same user or role are smoke before fire—auto-alert SecOps. Automatic warning against suspicious accounts, same user calling in short time.
* **Audit trail:** Every attempt, factor, score, and outcome is stamped back onto the ticket.
* **Compliance:** Automated reporting demonstrates consistent controls across the desk.

## Rollout plan that won’t break the desk

All organizations have their own project principles but these are common traits:

1. **Inventory factors + gaps:** Which users have MFA? Which don’t? What secure data is suitable for knowledge checks?
2. **Define 3 profiles:** Map to low/medium/high-risk roles; set pass threshold to 100.
3. **Integrate with ITSM:** Trigger the flow from your ticket (e.g., ServiceNow) with user ID + category; write back results and telemetry.
4. **Train for process, not persuasion:** Agents learn one thing—**follow the workflow**.
5. **Measure and tune:** Track failure rates, time-to-resolution, escalations, and false rejects. Adjust scoring and questions quarterly.

## A note on our tools

**[FastPass Identity Verification Manager (IVM)](https://www.fastpasscorp.com/products/identity-verification-manager/?utm%5Fsource=article&utm%5Fmedium=webpage&utm%5Fcampaign=bleepingcomputer)** implements this model: mandatory, role-based, and points-based verification, tightly integrated with ITSM.

It centralizes checks, enforces policy, and returns results + context to the ticket for alerting, audit, and compliance.

If you’re facing Scattered Spider-style tactics, this is the kind of guardrail that blocks them at the first hop.

[FastPassCorp](https://www.fastpasscorp.com/?utm%5Fsource=article&utm%5Fmedium=webpage&utm%5Fcampaign=bleepingcomputer) has assisted several large organizations with implementation of secure user workflow, and has gained a superior experience in the field documented in the available guides and videos.

## The takeaway

You don’t beat social engineering with nicer posters and longer scripts. You beat it by removing discretion, raising proof, and instrumenting the workflow the attacker is trying to exploit.

Do that, and the service desk stops being a soft target and starts acting like a proper control.

## Concerned about Scattered Spider?

If you’d like to know how you can protect your service desk and agents against a Scattered Spider or other social engineering attack?

**Have a look at our videos [and guides for implementing a secure user verification workflow](https://www.fastpasscorp.com/best-practices-ivm-user-verification-guide/?utm%5Fsource=article&utm%5Fmedium=webpage&utm%5Fcampaign=bleepingcomputer) or [contact us for a meeting on your situation](https://www.fastpasscorp.com/contact/?utm%5Fsource=article&utm%5Fmedium=webpage&utm%5Fcampaign=bleepingcomputer).**

_Sponsored and written by [FastPassCorp](https://www.fastpasscorp.com/contact/?utm%5Fsource=article&utm%5Fmedium=webpage&utm%5Fcampaign=bleepingcomputer)._