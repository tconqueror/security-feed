# Researcher reveals evidence of Instagram private profiles leaking photos

![Instagram](https://www.bleepstatic.com/content/hl-images/2023/12/20/instagram.jpg)

A security researcher has published detailed evidence showing that some Instagram private profiles returned links to user photos to unauthenticated visitors.

Instagram's private account feature is designed to restrict photos, videos, stories, and reels to approved followers. However, the researcher's findings show that, in certain cases, private profile content was embedded in publicly accessible server responses.

According to the researcher, Meta fixed the issue after his report was submitted but later closed it as "not applicable," stating the vulnerability could not be reproduced.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

## Instagram private profiles leaking photos

Security researcher Jatin Banga has recently demonstrated how certain Instagram private profiles were leaking links to private photos from these accounts—in the HTML response body itself.

When accessed by an unauthenticated user from certain mobile devices, private Instagram profiles (such as the researcher-created [_https://instagram.com/jatin.py_](https://www.instagram.com/jatin.py)) display the standard message: "This account is private. Follow to see their photos and videos."

![A sample private Instagram profile when accessed by an unauthenticated user](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/Instagram-private-profiles-bug/jatin-py-profile.jpeg)

**A sample private Instagram profile when accessed by an unauthenticated user**

However, in the HTML source code for affected profiles, links to some private photos were embedded in the page response.

In Banga's [example](https://github.com/jatin-dot-py/instagram-private-bypass/blob/main/sample%5Fresponse.html), the _polaris\_timeline\_connection_ JSON object returned in the HTML contained encoded CDN links to photos that should not have been accessible.

**HTML source code returning links to private photos**

The video proof-of-concept (PoC) shared by Banga and embedded below demonstrates the data leak vulnerability in action.

By limiting the formal testing to private test profiles Banga had created or had explicit permission to use, he found that at least 28% of the profiles were returning links to private photos:

## Meta quietly fixed the issue after report, researcher says

The researcher states that he shared his findings with Instagram's parent company, Meta, as early as October 12, 2025.

Meta initially classified the issue as a CDN caching problem, a characterization the researcher disputed.

"This wasn't a CDN caching issue — Instagram's backend was failing to check authorization before populating the response," [Banga wrote](http://medium.com/@jatin.b.rx3/i-found-a-bug-that-exposed-private-instagram-posts-to-anyone-eebb7923f7e3), describing it as a server-side authorization failure.

Banga created a second bug report clarifying the issue, but did not reach a satisfactory resolution with Meta despite a lengthy discussion spanning days.

According to the researcher, after repeated exchanges, the case was closed as "not applicable" but the exploit stopped working around October 16.

"The standard coordinated disclosure window is 90 days. I gave Meta 102 days and multiple escalation attempts. The exploit stopped working on all accounts I tested — though without root cause analysis from Meta, there's no confirmation the underlying issue is truly resolved," he continues.

In addition to his disclosure and the [GitHub repository](https://github.com/jatin-dot-py/instagram-private-bypass/) documenting extensive evidence of the flaw and communications with Meta, Banga shared additional materials with BleepingComputer to demonstrate the existence of the flaw.

We asked Banga why he did not archive the test private profile using a public service like the Internet Archive's Wayback Machine, which could have preserved the HTML source code with the links to private photos present, thereby indisputably confirming the presence of a bug.

"The Wayback Machine doesn't send the specific Mobile User-Agent and Headers required to trigger this server-side leak, so their crawlers couldn't capture it," the researcher clarified to BleepingComputer.

In the [published correspondence](http://github.com/jatin-dot-py/instagram-private-bypass/tree/main/official%5Fcommunication/pdfs), a Meta vulnerability triage analyst wrote:

**Meta's response to Instagram private profile leak bug** ([Jatin B.](https://github.com/jatin-dot-py/instagram-private-bypass/blob/main/official%5Fcommunication/pdfs/Case%5F1838100803582037.pdf))

Ultimately, during the course of the conversation, the analyst is seen stating:

"The fact that an unreproducible issue was fixed doesn't change the fact that it was not reproducible at the time. Even if the issue were reproducible, it's possible that a change was made to fix a different issue and this issue was fixed as an unintended side effect."

"I want to emphasize that I am not chasing a bounty here. By going public with this disclosure, I have forfeited any chance of a reward," Banga told BleepingComputer via email.

"The goal is transparency. Meta patched a critical privacy leak 48-96 hours after my report but refused to acknowledge it, dismissing it as an 'unintended side effect.' Their negligence and reluctance to investigate the actual root cause—despite having the logs—is the real issue."

"Nobody knows how long this has been actually exploited for, since it was not so hard to find."

BleepingComputer contacted Meta for comment on three separate occasions well in advance of publication but did not receive a response.