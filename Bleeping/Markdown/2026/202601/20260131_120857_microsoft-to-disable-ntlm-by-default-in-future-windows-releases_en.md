# Microsoft to disable NTLM by default in future Windows releases

![Windows](https://www.bleepstatic.com/content/hl-images/2024/06/12/windows-blue-background.jpg)

Microsoft announced that it will disable the 30-year-old NTLM authentication protocol by default in upcoming Windows releases due to security vulnerabilities that expose organizations to cyberattacks.

NTLM (short for New Technology LAN Manager) is a challenge-response authentication protocol introduced in 1993 with Windows NT 3.1 and is the successor to the LAN Manager (LM) protocol.

Kerberos has [superseded NTLM](https://answers.microsoft.com/en-us/msoffice/forum/all/ntlm-vs-kerberos/d8b139bf-6b5a-4a53-9a00-bb75d4e219eb) and is now the current default protocol for domain-connected devices running Windows 2000 or later. While it was the default protocol in older Windows versions, NTLM is still used today as a fallback authentication method when Kerberos is unavailable, even though it uses weak cryptography and is vulnerable to attacks.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Since its release, NTLM has been widely exploited in [NTLM relay attacks](https://www.bleepingcomputer.com/tag/ntlm-relay-attack/) (where threat actors force compromised network devices to authenticate against attacker-controlled servers) to escalate privileges and take complete control over the Windows domain. Despite this, NTLM is still used on Windows servers, allowing attackers to exploit vulnerabilities such as [PetitPotam](https://www.bleepingcomputer.com/news/security/microsoft-fixes-new-petitpotam-windows-ntlm-relay-attack-vector/), [ShadowCoerce](https://www.bleepingcomputer.com/news/microsoft/microsoft-quietly-fixes-shadowcoerce-windows-ntlm-relay-bug/), [DFSCoerce](https://www.bleepingcomputer.com/news/microsoft/new-dfscoerce-ntlm-relay-attack-allows-windows-domain-takeover/), and [RemotePotato0](https://www.bleepingcomputer.com/news/security/windows-remotepotato0-zero-day-gets-an-unofficial-patch/) to bypass NTLM relay attack mitigations.

NTLM has also been targeted by [pass-the-hash attacks](https://www.bleepingcomputer.com/tag/pass-the-hash/), in which cybercriminals exploit system vulnerabilities or deploy malicious software to steal NTLM hashes (hashed passwords) from targeted systems. These hashed passwords are used to authenticate as the compromised user, allowing the attackers to steal sensitive data and spread laterally across the network.

## "Blocked and no longer used automatically"

On Thursday, as part of a broader push toward passwordless, phishing-resistant authentication methods, Microsoft announced that NTLM will finally be disabled by default in the next major Windows Server release and associated Windows client versions, marking a significant shift away from the legacy protocol to more secure Kerberos-based authentication.

Microsoft also outlined a three-phase transition plan designed to mitigate NTLM-related risks while minimizing disruption. In phase one, admins will be able to use enhanced auditing tools available in Windows 11 24H2 and Windows Server 2025 to identify where NTLM is still in use.

Phase two, scheduled for the second half of 2026, will introduce new features, such as IAKerb and a Local Key Distribution Center, to address common scenarios that trigger NTLM fallback.

Phase three will disable network NTLM by default in future releases, even though the protocol will remain present in the operating system and can be explicitly re-enabled through policy controls if needed.

![NTLM timeline](https://www.bleepstatic.com/images/news/u/1109292/2026/ntlm-timeline.png)

_NTLM timeline (Microsoft)_

​"Disabling NTLM by default does not mean completely removing NTLM from Windows yet. Instead, it means that Windows will be delivered in a secure-by-default state where network NTLM authentication is blocked and no longer used automatically," [Microsoft said](https://techcommunity.microsoft.com/blog/windows-itpro-blog/advancing-windows-security-disabling-ntlm-by-default/4489526).

"The OS will prefer modern, more secure Kerberos-based alternatives. At the same time, common legacy scenarios will be addressed through new upcoming capabilities such as Local KDC and IAKerb (pre-release)."

Microsoft first announced [plans to retire the NTLM authentication protocol](https://www.bleepingcomputer.com/news/security/microsoft-plans-to-kill-off-ntlm-authentication-in-windows-11/) in October 2023, noting that it also wanted to expand management controls to give administrators greater flexibility in monitoring and restricting NTLM usage within their environments.

It also [officially deprecated NTLM authentication](https://www.bleepingcomputer.com/news/microsoft/microsoft-deprecates-windows-ntlm-authentication-protocol/) on Windows and Windows servers in July 2024, advising developers to transition to Kerberos or Negotiation authentication to prevent future issues.

Microsoft has been warning developers to stop using NTLM in their apps [since 2010](https://learn.microsoft.com/en-us/openspecs/windows%5Fprotocols/ms-nlmp/1e846608-4c5f-41f4-8454-1b91af8a755b) and advising Windows admins to either disable NTLM or configure their servers to block NTLM relay attacks using Active Directory Certificate Services (AD CS).