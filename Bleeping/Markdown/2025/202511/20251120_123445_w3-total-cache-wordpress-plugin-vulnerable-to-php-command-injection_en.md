# W3 Total Cache WordPress plugin vulnerable to PHP command injection

![W3 Total Cache WordPress plugin vulnerable to PHP command injection](https://www.bleepstatic.com/content/hl-images/2025/11/03/WordPress.jpg)

A critical flaw in the W3 Total Cache (W3TC) WordPress plugin can be exploited to run PHP commands on the server by posting a comment that contains a malicious payload.

The vulnerability, tracked as [CVE-2025-9501](https://nvd.nist.gov/vuln/detail/CVE-2025-9501), affects all versions of the W3TC plugin prior to 2.8.13 and is described as an unauthenticated command injection.

W3TC is installed on more than one million websites to increase performance and reduce load times.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

The developer released version 2.8.13, which addresses the security issue, on October 20\. However, based on data from WordPress.org, hundreds of thousands of websites may still be vulnerable, as there have been around 430,000 downloads since the patch became available.

WordPress security company WPScan says that an attacker can trigger CVE-2025-9501 and inject commands through the _\_parse\_dynamic\_mfunc()_ function responsible for processing dynamic function calls embedded in cached content.

“The \[W3TC\] plugin is vulnerable to command injection via the \_parse\_dynamic\_mfunc function, allowing unauthenticated users to execute PHP commands by submitting a comment with a malicious payload to a post,” [WPScan](https://wpscan.com/vulnerability/6697a2c9-63ae-42f0-8931-f2e5d67d45ae/)

An attacker successfully exploiting this PHP code execution may be able to take full control of the vulnerable WordPress website, as they can run any command on the server without the need to authenticate.

WPScan researchers have developed a proof-of-concept exploit (PoC) for CVE-2025-9501 and said they would publish it on November 24 to give users sufficient time to install the updates.

Typically, malicious exploitation of flaws begins almost immediately following the publication of a PoC exploit. Typically, after an exploit code is published, attackers look for potential targets and try to compromise them.

Website administrators who cannot upgrade by the deadline should consider deactivating the W3 Total Cache plugin or take the necessary action to make sure that comments cannot be used to deliver malicious payloads that could trigger the exploit.

The recommended action is to upgrade to W3 Total Cache version 2.8.13, released on October 20.