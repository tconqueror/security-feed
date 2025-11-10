# Quantum Route Redirect PhaaS targets Microsoft 365 users worldwide

![Quantum Route Redirect PhaaS targets Microsoft 365 users worldwide](https://www.bleepstatic.com/content/hl-images/2025/07/25/Microsoft-365.jpg)

A new phishing automation platform named Quantum Route Redirect is using around 1,000 domains to steal Microsoft 365 users' credentials.

The kit comes pre-configured with phishing domains to allow less skilled threat actors to achieve maximum results with the least effort.

Since August, analysts at security awareness company KnowBe4 have noticed Quantum Route Redirect (QRR) attacks in the wild across a wide geography, although nearly three-quarters are located in the U.S.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

They say that the kit "is an advanced automation platform" that can cover all the stages of a phishing attack, from rerouting traffic to malicious domains to tracking victims.

Attacks start with a malicious email made to appear as a DocuSign request, a payment notification, a missed voicemail, or a QR code.

![Sample phishing message](https://www.bleepstatic.com/images/news/u/1220909/2025/November/phish.jpg)

**Sample phishing message**  
_Source: KnowBe4_

The emails direct targets to a credential harvesting page hosted on a URL that follows a specific pattern.

“Our researchers also observed that the domain URLs consistently follow the pattern “/(\[\\w\\d-\]+\\.){2}\[\\w\]{,3}\\/quantum.php/” and are typically hosted on parked or compromised domains,” [explains KnowBe4](https://blog.knowbe4.com/quantum-route-redirect-anonymous-tool-streamlining-global-phishing-attack).

“The choice to host on legitimate domains can help to socially engineer the human targets of these attacks.”

KnowBe4 says it has identified about 1,000 domains hosting QRR phishing pages.

A built-in filtering mechanism can distinguish between bots and human visitors, the researchers say, adding that QRR can redirect potential victims to a phishing page, while automated systems, such as email security tools, are sent to benign sites.

**Profiling and redirection flow**  
_Source: KnowBe4_

As the central traffic routing system on QRR performs its redirecting tasks automatically, operators can view the related statistics on the dashboard, where the number of real versus non-human visitors is logged in real-time.

**Main panel**  
_Source: KnowBe4_

KnowBe4 has observed the QRR phishing kit targeting Microsoft 365 accounts across 90 countries, but 76% of the attacks were directed at users in the U.S.

**QRR victims heatmap**  
_Source: KnowBe4_

The researchers expect the use of Quantum Route Redirect to increase due to the methods used to evade URL scanning technologies.

Similar services that gained prominence earlier this year include [VoidProxy](https://www.bleepingcomputer.com/news/security/new-voidproxy-phishing-service-targets-microsoft-365-google-accounts/), [Darcula](https://www.bleepingcomputer.com/news/security/darcula-phaas-steals-884-000-credit-cards-via-phishing-texts/), [Morphing Meerkat](https://www.bleepingcomputer.com/news/security/phishing-as-a-service-operation-uses-dns-over-https-for-evasion/), and [Tycoon2FA](https://www.bleepingcomputer.com/news/security/tycoon2fa-phishing-kit-targets-microsoft-365-with-new-tricks/).

However, there are defense methods that can protect against this threat.

KnowBe4 analysts recommend implementing robust URL filtering that can detect phishing attempts, along with tools that can monitor accounts for signs of compromise if a user's credentials are stolen.