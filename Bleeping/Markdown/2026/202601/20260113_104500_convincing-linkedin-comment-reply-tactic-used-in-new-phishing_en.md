# Convincing LinkedIn comment-reply tactic used in new phishing

![LinkedIn](https://www.bleepstatic.com/content/hl-images/2022/10/26/linkedin-header.jpg)

Scammers are flooding LinkedIn posts this week with fake "reply" comments that appear to come from the platform itself, warning users of bogus policy violations and urging them to visit an external link.

The messages convincingly impersonate LinkedIn branding and in some cases even use the company’s official lnkd.in URL shortener, making the phishing links harder to distinguish from legitimate ones.

## 'Access to your account is temporarily restricted'

Over the past few days, LinkedIn users have been targeted with bot-like activity from several LinkedIn-themed profiles commenting on their posts.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

These posts falsely claim that the user has "engaged in activities that are not in compliance" with the platform and that their account has been "temporarily restricted" until they visit the specified link in the comment.

The fabricated reply bearing the LinkedIn logo, shown below and [archived here](http://archive.md/xFDiL), appears fairly convincing depending on how viewers are interacting with the comments area and on what device.

![Fake LinkedIn reply-comment urging users to visit a phishing page](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/linkedin-fake-comment-replies/LinkedIn-fake-suspension-comment.jpg)

**Fake LinkedIn reply-comment urging users to visit a phishing page**

"We take steps to protect your account when we detect signs of potential unauthorized access. This may include logins from unfamiliar locations or..." also states the link preview generated in the crafted reply.

The example shared above shows an alphanumeric ".app" domain that is not associated with LinkedIn and may raise suspicion among some users. However, other posts take this lure a step further by masking the destination links via LinkedIn's official URL shortener, _lnkd.in_, making phishing domains harder to spot without clicking on them. This can be especially concerning if the link preview does not fully appear on certain devices.

Examples of such replies and comments were shared by several LinkedIn members, including [Ratko Ivekovic](https://www.linkedin.com/posts/chefratko%5Ftoday-a-profile-called-linked-very-tried-activity-7415013519152222208-M2vk?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAArUYTQBMx2P2SMFdIx-wUs7H1hfLGpuhVM), [Jocelyn M.](https://www.linkedin.com/posts/jocelynmarquismsc%5Fbe-aware-and-be-warry-you-might-get-a-comment-activity-7415398707484987392-xF7t?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAArUYTQBMx2P2SMFdIx-wUs7H1hfLGpuhVM), [Candyce Edelen](https://www.linkedin.com/posts/candyceedelen%5Fscam-alert-this-scam-is-trying-to-steal-activity-7415436638413328385-T4nK?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAArUYTQBMx2P2SMFdIx-wUs7H1hfLGpuhVM), and [Adama Coulibaly](https://www.linkedin.com/posts/coulibalyadama%5Fover-the-past-few-days-ive-been-receiving-activity-7415274522901221380-Eep8/?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAArUYTQBMx2P2SMFdIx-wUs7H1hfLGpuhVM).

**Replies abusing the lnkd.in URL shortener** (Jocelyn M on LinkedIn)

The _very1929412.netlify\[.\]app_ phishing site in particular, seen by BleepingComputer, first elaborates on the false "temporary restriction" and advises the viewer that they need to "verify" their identity to lift the restriction:

**First LinkedIn phishing domain** (BleepingComputer)

When clicked, the "Verify your identity" button directs the user to yet another phishing domain, _https://very128918\[.\]site_ which is where credential harvesting actually occurs:

**Second LinkedIn-themed phishing domain harvesting credentials**  
(BleepingComputer)

## LinkedIn Company pages being abused

These comments are being posted from fake company pages using LinkedIn's official logo and a variation of the platform's name, e.g. Linked Very.

Edelen shared [several such "Linked Very" accounts](https://archive.md/wip/h7hVS) that popped up on the professional networking platform in the past week.

At the time of writing, the [page shown below](http://archive.md/igUgw) has been taken down by LinkedIn:

**A LinkedIn Company page impersonating LinkedIn** (BleepingComputer)

## LinkedIn aware and tackling the campaign

BleepingComputer reached out to LinkedIn to ask if the platform was aware of this ongoing campaign.

"I can confirm that we are aware of this activity and our teams are working to take action," a LinkedIn spokesperson stated to BleepingComputer.

"It's important to note that LinkedIn does not and will not communicate policy violations to our members through public comments, and we encourage our members to [make a report](http://www.linkedin.com/help/linkedin/answer/a1338436?hcppcid=search) if they encounter this suspicious behavior. This way we can review and take the appropriate action."

In 2023, BleepingComputer [first reported](https://www.bleepingcomputer.com/news/security/convincing-twitter-quote-tweet-phone-scam-targets-bank-customers/) a convincing X (then Twitter) scam in which accounts impersonating major banks replied to customers’ complaints directed at the real institutions, urging them to contact a scammer-controlled phone number.

Users should remain vigilant and avoid interacting with comments, replies, or private messages that appear to impersonate LinkedIn and urge recipients to click external links.