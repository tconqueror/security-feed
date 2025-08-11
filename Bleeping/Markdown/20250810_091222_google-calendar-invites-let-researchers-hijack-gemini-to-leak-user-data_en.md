# Google Calendar invites let researchers hijack Gemini to leak user data

![Gemini](https://www.bleepstatic.com/content/hl-images/2024/08/13/Gemini.jpg)

Google fixed a bug that allowed maliciously crafted Google Calendar invites to remotely take over Gemini agents running on the target's device and leak sensitive user data.

The attack unfolded without requiring any user involvement beyond typical interactions with the assistant, which occur daily for users of Gemini.

Gemini is Google's large language model (LLM) assistant integrated into Android, Google web services, and Google's Workspace apps, having access to Gmail, Calendar, and Google Home.

By sending a calendar invite with an embedded prompt injection, often hidden in the event title, attackers can potentially exfiltrate email content and Calendar information, track victim location, control smart home devices via Google Home, open apps on Android, and trigger Zoom video calls.

The attack was demonstrated in a [report by SafeBreach](https://www.safebreach.com/blog/invitation-is-all-you-need-hacking-gemini/) researchers, who noted that it does not require white-box model access and was not blocked by prompt filtering or other protection measures in Gemini.

## You've got an invite

The attack started with a Google Calendar event invite sent to the target, with the event title containing an indirect prompt injection.

Once the victim interacts with Gemini, like asking "What are my calendar events today," Gemini pulls the list of events from Calendar, including the malicious event title the attacker embedded.

This becomes part of Gemini's context window, and the assistant treats it as part of the conversation, unable to realize the instruction is hostile to the user.

Depending on the prompt the attacker uses, they may trigger tools or agents to perform Calendar event wiping or editing, open a URL to retrieve the target's IP address, join a Zoom call, use Google Home to control physical devices, or access emails and extract sensitive user data.

![Overview of the attack](https://www.bleepstatic.com/images/news/u/1220909/2025/August/overview.jpg)

**Overview of the attack**  
_Source: SafeBreach_

This is a downside of Gemini's broad permissions to take actions across tools, as this is precisely where its usefulness comes from.

One thing to note is that the attacker may need to send six Calendar invites for the attack to work while maintaining a certain level of stealthiness, only including the malicious prompt on the last one.

This is because the Calendar Events section only displays the five most recent events, with the rest tucked under a 'Show more' button. When prompted, though, Gemini will parse them all, including the malicious prompt.

Meanwhile, the user will not see the malicious title or realize the compromise unless they manually expand the events list on Calendar by clicking on 'Show more.'

![Google Calendar events screen](https://www.bleepstatic.com/images/news/u/1220909/2025/August/show-more.jpg)

**Google Calendar events screen**  
_Source: SafeBreach_

Last month, Mozilla's security researcher [Marco Figueroa highlighted](https://www.bleepingcomputer.com/news/security/google-gemini-flaw-hijacks-email-summaries-for-phishing/) another case of an easily attainable prompt injection attack targeting Gemini again, laying the ground for convincing phishing attacks against the target.

Google responded to the report by stating that they are continuously rolling out new safeguards for Gemini to defend against a wide range of adversarial attacks, with many mitigations planned for imminent implementation or already in some deployment stage.

"We fixed this issue before it could be exploited thanks to the great work and responsible disclosure by Ben Nassi and team," Andy Wen, senior director, security product management, Google Workspace, told BleepingComputer. 

"Their research helped us better understand novel attack pathways, and accelerated our work to deploy new, cutting edge defenses which are now in place protecting users. It's a great example of why red-teaming and cross-industry collaboration is so important."