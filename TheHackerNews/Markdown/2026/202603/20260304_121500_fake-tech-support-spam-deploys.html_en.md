# Fake Tech Support Spam Deploys Customized Havoc C2 Across Organizations

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgMxXTslXwVQy4UDmwQOi39oPLz0gBjk3E%5FmUL0hONp%5FuAbe2mkCooBcTU3zE6nArVycOldRPm5jMHfzTAI%5FplrX1jvn5o8zmSGKTH794N2tpztPyTLW-TBZqfHaa4nbHLMY2LHhW0l1J4wzmg8lCRXOFWdAQSSn1Qb4iR8PIeRUE9K1NvpCtluT69-y7By/s1700-e365/outlook.jpg)

Threat hunters have called attention to a new campaign as part of which bad actors masqueraded as fake IT support to deliver the [Havoc](https://github.com/HavocFramework/Havoc) command-and-control (C2) framework as a precursor to data exfiltration or ransomware attack.

The intrusions, [identified](https://www.huntress.com/blog/fake-tech-support-havoc-command-control) by Huntress last month across five partner organizations, involved the threat actors using email spam as lures, followed by a phone call from an IT desk that activates a layered malware delivery pipeline.

"In one organization, the adversary moved from initial access to nine additional endpoints over the course of eleven hours, deploying a mix of custom [Havoc Demon](https://attack.mitre.org/software/S1229/) payloads and legitimate RMM tools for persistence, with the speed of lateral movement strongly suggesting the end goal was data exfiltration, ransomware, or both," researchers Michael Tigges, Anna Pham, and Bryan Masters said.

It's worth noting that the modus operandi is consistent with email bombing and Microsoft Teams phishing attacks [orchestrated](https://thehackernews.com/2025/01/qakbot-linked-bc-malware-adds-enhanced.html) by [threat actors](https://thehackernews.com/2025/06/former-black-basta-members-use.html) associated with the Black Basta ransomware operation in the past. While the cybercrime group appears to have gone silent following a public leak of its internal chat logs last year, the continued presence of the group's playbook suggests two possible scenarios.

[](https://thehackernews.uk/not-fast-enough-d)

One possibility is that former Black Basta affiliates have moved on to other ransomware operations and are using them to mount fresh attacks, or two, rival threat actors have adopted the same strategy to conduct social engineering and obtain initial access. 

The attack chain begins with a spam campaign aiming to overwhelm a target's inboxes with junk emails. In the next step, the threat actors, masquerading as IT support, contact the recipients and trick them into granting remote access to their machines either via a Quick Assist session or by installing tools like AnyDesk to help remediate the problem.

With the access in place, the adversary wastes no time launching the web browser and navigating to a fake landing page hosted on Amazon Web Services (AWS) that impersonates Microsoft and instructs the victim to enter their email address to access Outlook's anti-spam rules update system and update the spam rules.

Clicking a button to "Update rules configuration" on the counterfeit page triggers the execution of a script that displays an overlay asking the user to enter their password.

"This mechanism serves two purposes: it allows the threat actor (TA) to harvest credentials, which, when combined with the required email address, provides access to the control panel; concurrently, it adds a layer of authenticity to the interaction, convincing the user the process is genuine," Huntress said.

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEii4Lib-wKbh4pAovQsn5oiBbzv2fPcZbMECZ03FDMU0cFMzd5BNvg-qFAmq8OrTFYJ8f3%5FkhRg9aqLAcM5zOqiA8xzrmUTzvFrjnfcJQ%5F-NfgYvZCJl146UiHI4FONhE2zrMfOtmEm-8P3P1VRbh-pcegdvLp3LtXjhODwoNBeOq4A%5F4WS%5FRhQ0Cv2APDN/s1700-e365/anti.jpg)

The attack also hinges on downloading the supposed anti-spam patch, which, in turn, leads to the execution of a legitimate binary named "ADNotificationManager.exe" (or "DLPUserAgent.exe" and "Werfault.exe") to sideload a malicious DLL. The DLL payload implements defense evasion and executes the Havoc shellcode payload by spawning a thread containing the Demon agent.

At least one of the identified DLLs ("vcruntime140\_1.dll") incorporates additional tricks to sidestep detection by security software using control flow obfuscation, timing-based delay loops, and techniques like [Hell's Gate](https://thehackernews.com/2025/04/lazarus-hits-6-south-korean-firms-via.html) and [Halo's Gate](https://blog.sektor7.net/#!res/2021/halosgate.md) to [hook](https://malwaretech.com/2023/12/an-introduction-to-bypassing-user-mode-edr-hooks.html) [ntdll.dll functions](https://0xmaz.me/posts/HookChain-A-Deep-Dive-into-Advanced-EDR-Bypass-Techniques/) and bypass endpoint detection and response (EDR) solutions.

"Following the successful deployment of the Havoc Demon on the beachhead host, the threat actors began lateral movement across the victim environment," the researchers said. "While the initial social engineering and malware delivery demonstrated some interesting techniques, the hands-on-keyboard activity that followed was comparatively straightforward."

This includes creating scheduled tasks to launch the Havoc Demon payload every time the infected endpoints are rebooted, providing the threat actors with persistent remote access. That said, the threat actor has been found to deploy legitimate remote monitoring and management (RMM) tools like Level RMM and XEOX on some compromised hosts instead of Havoc, thus diversifying their persistence mechanisms.

[](https://thehackernews.uk/fs-report-d)

Some important takeaways from these attacks are that threat actors are more than happy to impersonate IT staff and call personal phone numbers if it improves the success rate, techniques like defense evasion that were once limited to attacks on large firms or state-sponsored campaigns are becoming increasingly common, and commodity malware is customized to bypass pattern-based signatures.

Also of note is the speed at which attacks progress swiftly and aggressively from initial compromise to lateral movement, as well as the numerous methods used to maintain persistence.

"What begins as a phone call from 'IT support' ends with a fully instrumented network compromise – modified Havoc Demons deployed across endpoints, legitimate RMM tools repurposed as backup persistence," Huntress concluded. "This campaign is a case study in how modern adversaries layer sophistication at every stage: social engineering to get in the door, DLL sideloading to stay invisible, and diversified persistence to survive remediation."