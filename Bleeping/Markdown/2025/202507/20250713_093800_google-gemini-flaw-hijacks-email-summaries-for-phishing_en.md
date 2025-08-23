# Google Gemini flaw hijacks email summaries for phishing

![Gmail](https://www.bleepstatic.com/content/hl-images/2023/10/03/Gmail_headpic.jpg)

Google Gemini for Workspace can be exploited to generate email summaries that appear legitimate but include malicious instructions or warnings that direct users to phishing sites without using attachments or direct links.

Such an attack leverages indirect prompt injections that are hidden inside an email and obeyed by Gemini when generating the message summary. 

Despite similar prompt attacks being reported since 2024 and safeguards being implemented to block misleading responses, the technique remains successful.

## Attack through Gemini

A prompt-injection attack on Google's Gemini model was [disclosed through 0din](https://0din.ai/blog/phishing-for-gemini), Mozilla's bug bounty program for generative AI tools, by researcher Marco Figueroa, GenAI Bug Bounty Programs Manager at Mozilla.

The process involves creating an email with an invisible directive for Gemini. An attacker can hide the malicious instruction in the body text at the end of the message using HTML and CSS that sets the font size to zero and its color to white.

![Crafting the malicious email](https://www.bleepstatic.com/images/news/u/1220909/2025/July/craft.jpg)

**Crafting the malicious email**  
_Source: 0DIN_

The malicious instruction will not be rendered in Gmail, and because there are no attachments or links present, the message is highly likely to reach the potential target's inbox.

If the recipient opens the email and asks Gemini to generate a summary of the email, Google's AI tool will parse the invisible directive and obey it.

An example provided by Figueroa shows Gemini following the hidden instruction and includes a security warning about the user's Gmail password being compromised, along with a support phone number.

![Gemini summary result served to the user](https://www.bleepstatic.com/images/news/u/1220909/2025/July/geminisummary.jpg)

**Gemini summary result served to the user**  
_Source: 0DIN_

As many users are likely to trust Gemini's output as part of Google Workspace functionality, chances are high for this alert to be considered a legitimate warning instead of a malicious injection.

Figueroa offers a few detections and mitigation methods that security teams can apply to prevent such attacks. One way is to remove, neutralize, or ignore content that is styled to be hidden in the body text.

Another approach is to implement a post-processing filter that scans Gemini output for urgent messages, URLs, or phone numbers, flagging the message for further review.

Users should also be aware that Gemini summaries should not be considered authoritative when it comes to security alerts.

BleepingComputer has contacted Google to ask about defenses that prevent or mitigate such attacks, and a spokesperson directed us to a Google [blog post](https://security.googleblog.com/2025/06/mitigating-prompt-injection-attacks.html) on security measures against prompt injection attacks.

"We are constantly hardening our already robust defenses through red-teaming exercises that train our models to defend against these types of adversarial attacks," a Google spokesperson told BleepingComputer.

The company representative clarified to BleepingComputer that some of the mitigations are in the process of being implemented or are about to be deployed.

Google has seen no evidence of incidents manipulating Gemini in the way demonstrated in Figueroa's report, the spokesperson said.