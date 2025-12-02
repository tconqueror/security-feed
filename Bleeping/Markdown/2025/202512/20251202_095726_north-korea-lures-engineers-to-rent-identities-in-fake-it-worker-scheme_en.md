# North Korea lures engineers to rent identities in fake IT worker scheme

![Famous Chollima tricks devs to rent identities in fake IT worker scheme](https://www.bleepstatic.com/content/hl-images/2023/08/31/Lazarus-1.jpg)

In an unprecedented intelligence operation, security researchers exposed how North Korean IT recruiters target and lure developers into renting their identities for illicit fundraising.

Famous Chollima (also known as WageMole), part of North Korea’s state-sponsored Lazarus group, is known for social-engineering campaigns to infiltrate Western companies for espionage and revenue generation for the regime.

They managed to trick recruiters and secure jobs at Fortune 500 companies by leveraging stolen identities and a lot of AI, including deep fake videos, and avoiding appearing on camera during interviews.

Another method is to recruit legitimate engineers and convince them to act as a figurehead in DPRK agents’ operation to get a remote job at a targeted company.

The frontman would have to be the face of the agents in the interaction with the company during interviews and would receive a percentage of the salary, between 20% and 35% for the duration of the contract.

To get a larger sum, the compromised engineer would have to let DPRK agents use their computer.

This is to hide the North Korean’s location and their traces, since they would use the computer and the engineer as a proxy for malicious activities.

[Mauro Eldritch](https://www.linkedin.com/in/mauroeldritch/), a hacker and threat intelligence specialist at BCA LTD, says that the compromised engineer takes all the risk as they rented their identity and will be the only one responsible for any damage done.

### Spamming GitHub repositories

Eldritch is familiar with Famous Chollima’s recruiting tactics while leading the Quetzal Team, the Web3 Threats Research Team at digital financial services company Bitso.

He documented several encounters with DPRK agents looking for gullible engineers or developers ready to make some quick money \[[1](https://quetzal.bitso.com/p/interview-with-the-chollima), [2](https://quetzal.bitso.com/p/interview-with-the-chollima-ii), [3,](https://quetzal.bitso.com/p/interview-with-the-chollima-iii) [4](https://quetzal.bitso.com/p/interview-with-the-chollima-iv), [5](https://quetzal.bitso.com/p/interview-with-the-chollima-v)\].

Recently, he found multiple accounts on GitHub that were spamming repositories with a recruitment announcement for individuals who would attend technical interviews (.NET, Java, C#, Python, JavaScript, Ruby, Golang, Blockchain) under a provided fake identity.

![Repositories with recruitment messages](https://www.bleepstatic.com/images/news/u/1100723/C%20-%20pull%20requests_DPRK-offer.png)

**Repositories with Famous Chollima recruitment messages**  
_source: Mauro Eldritch and Heiner García_

The candidate would not have to be proficient in the technical areas, as the recruiter would assist “to respond to interviewers effectively.”

To make the offer more attractive, the DPRK agent set the financial expectation to “around $3000 per month.”

![Famous Chollima recruitment message](https://www.bleepstatic.com/images/news/u/1100723/B%20-%20DPRK-offer.png)

**Famous Chollima recruitment message**  
_source: Mauro Eldritch and Heiner García_

Eldritch accepted the challenge and developed a plan with Heiner García from the NorthScan threat intelligence initiative for uncovering North Korean IT worker infiltration.

The two researchers used the ANY.RUN sandbox and malware analysis platform to set up a simulated [laptop farm](https://www.bleepingcomputer.com/news/security/us-woman-sentenced-to-8-years-in-prison-for-running-laptop-farm-helping-north-koreans-infiltrate-300-firms/) honeypot that could record the activity in real time for later analysis of the tactics and tools used in the operation.

García assumed the role of the rookie engineer responding to the recruitment offer. He posed as a previously contacted individual, a developer named Andy Jones, based in the United States.

The researchers created a new GitHub profile that mimicked Jones’ down to the public repositories and associated details.

Following multiple interactions with the DPRK agent to obtain information about the operation, the North Korean recruiter asked for 24/7 remote access to Eldritch’s laptop over AnyDesk for “remote work.”

Slowly, the agent disclosed that he needed the ID, full name, visa status, and address to apply to interviews as Andy Jones.

For acting as a frontman in the interviews, Eldritch’s persona would receive 20% of the salary, or “10% for only using my information and laptop whilst he conducts the interviews himself.”

The DPRK agent also asked for the social security number, for background checks, and explained that all accounts need to be verified on KYC-compliant platforms.

### Remoting in via Astrill VPN

After setting up the sandboxed ANY.RUN environment, based in Germany, and tunneled the connection through a residential proxy to appear US-based, the researchers were ready to let the “recruiter” connect remotely to their “laptop.”

The researchers had full control over the environment and could prevent the threat actor from browsing while keeping the remote connection active, and crash the machine at will, to deny malicious activity against any third party.

After connecting to the researchers’ machine remotely, the threat actor started to check the hardware on the system, set Google Chrome as the default browser, and verified the location of the station.

The researchers noticed that the remote connection came through Astrill VPN, a popular service among North Korean fake IT workers.

[](http://x.com/craiu/status/1899045753286209988) 

**North Koreans IT worker prefer Astrill VPN**  
_source: Costin Raiu_

### Tools and tricks of the trade

The two researchers tried to stall the North Korean’s activity as much as possible, pushing his patience to the limit by crashing the machine and removing all the progress, or by delaying their reply to messages.

They even blamed all the technical “mishaps” on a network misconfiguration or the agent’s use of a VPN connection.

In one instance, the researchers trapped the DPRK agent in a login and CAPTCHA loop where he spent almost an hour trying to escape.

However, all these actions led to obtaining more information about the operation, the individuals involved, potential partners from different countries, and the tools and tricks used.

The researchers observed multiple AI-powered extensions like AIApply, Simplify Copilot, Final Round AI, and Saved Prompts that helped the threat actor autofill job applications and create resumes, save ChatGPT LLM prompts, and for getting real-time replies during interviews.

Apart from this, the threat actor also revealed OTP authentication extensions, the use Google Remote Desktop, and routine system reconnaissance tactics.

At one point, the fake recruiter logged into his Google account and activated the synchronization option, which loaded in the browser all the preferences associated with the profile, and gave access to his email inbox.

**GMail inbox used by the North Korean fake IT recruiter**  
_source: Mauro Eldritch and Heiner García_

García and Eldritch could see multiple subscriptions to job-seeking platforms, installed the browser extensions, and Slack workspaces and partial chats.

“He spoke regularly with an individual named Zeeshan Jamshed who in an initial conversation stated that he would be out for Eid, the Muslim festivity,” the researchers say in a report shared with BleepingComputer.

According to the report, the Famous Chollima team involved in this operation consisted of six members, who used the names Mateo, Julián, Aaron,  
Jesús, Sebastián, and Alfredo.

However, it should be mentioned that there are multiple North Korean teams engaged in Famous Chollima operations, some of them having ten members, and they compete with each other, poaching potential victims, as Eldritch and García also point out in the report.

The information collected from the interaction with the North Korean threat actor could serve defenders across both small and large enterprises as an early warning of a potential infiltration attempt.

The data could help them anticipate the group’s behaviors, disrupt workflows, and improve detection beyond standard malware IoC matching.