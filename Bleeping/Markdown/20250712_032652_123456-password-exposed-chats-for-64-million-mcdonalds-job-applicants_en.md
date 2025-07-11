# '123456' password exposed chats for 64 million McDonald’s job applicants

![McDonald's sign](https://www.bleepstatic.com/content/hl-images/2024/03/15/mcdonalds-sign.jpg)

Cybersecurity researchers discovered a vulnerability in McHire, McDonald's chatbot job application platform, that exposed the chats of more than 64 million job applicants across the United States.

The flaw was discovered by security researchers Ian Carroll and Sam Curry, who found that the ChatBot's admin panel utilized a test franchise that was protected by weak credentials of a login name "123456" and a password of "123456".

McHire, powered by Paradox.ai and used by about 90% of McDonald's franchisees, accepts job applications through a chatbot named Olivia. Applicants can submit names, email addresses, phone numbers, home addresses, and availability, and are required to complete a personality test as part of the job application process.

Once logged in, the researchers submitted a job application to the test franchise to see how the process worked.

During this test, they noticed that HTTP requests were sent to an API endpoint at /api/lead/cem-xhr, which used a parameter lead_id, which in their case was 64,185,742.

The researchers found that by incrementing and decrementing the lead_id parameter, they were able to expose the full chat transcripts, session tokens, and personal data of real job applicants that previously applied on McHire.

This type of flaw is called an IDOR (Insecure Direct Object Reference) vulnerability, which is when an application exposes internal object identifiers, such as record numbers, without verifying whether the user is actually authorized to access the data.

"During a cursory security review of a few hours, we identified two serious issues: the McHire administration interface for restaurant owners accepted the default credentials 123456:123456, and an insecure direct object reference (IDOR) on an internal API allowed us to access any contacts and chats we wanted," Carroll [explained in a writeup](https://ian.sh/mcdonalds) about the flaw.

"Together they allowed us and anyone else with a McHire account and access to any inbox to retrieve the personal data of more than 64 million applicants."

In this case, incrementing or decrementing a lead_id number in a request returned sensitive data belonging to other applicants, as the API failed to check if the user had access to the data.

![Exploiting the IDOR bug to see McDonald's job applications](https://www.bleepstatic.com/images/news/security/m/mchire/idor-vulnerability/mchire-idor.jpg)

**Exploiting the IDOR bug to see McDonald's job applications**

The issue was reported to Paradox.ai and McDonald's on June 30.

McDonald's acknowledged the report within an hour, and the default admin credentials were disabled soon after.

"We're disappointed by this unacceptable vulnerability from a third-party provider, Paradox.ai. As soon as we learned of the issue, we mandated Paradox.ai to remediate the issue immediately, and it was resolved on the same day it was reported to us," McDonald's told [Wired](https://www.wired.com/story/mcdonalds-ai-hiring-chat-bot-paradoxai/) in a statement about the research.

Paradox deployed a fix to address the IDOR flaw and confirmed that the vulnerability was mitigated. Paradox.ai has [since stated](https://www.paradox.ai/blog/responsible-security-update) that it is conducting a review of its systems to prevent similar big issues from recurring.

Paradox also told BleepingComputer that the information exposed would be any chatbot interaction, such as clicking on a button, even if no personal information was entered.

_Update 7/11/25: Added information from Paradox._