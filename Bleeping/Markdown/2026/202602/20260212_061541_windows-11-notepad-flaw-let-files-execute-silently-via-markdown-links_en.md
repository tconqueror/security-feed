# Windows 11 Notepad flaw let files execute silently via Markdown links

![Windows 11 Notepad](https://www.bleepstatic.com/content/hl-images/2026/02/11/modern-notepad-spotlight.jpg)

Microsoft has fixed a "remote code execution" vulnerability in Windows 11 Notepad that allowed attackers to execute local or remote programs by tricking users into clicking specially crafted Markdown links, without displaying any Windows security warnings.

With the release of Windows 1.0, Microsoft introduced Notepad, a simple, easy-to-use text editor that, over the years, became popular for quickly jotting notes, reading text files, creating to-do lists, or acting as a code editor.

For those who needed a rich text format (RTF) editor that supported different fonts, sizes, and formatting tools like bold, italics, and lists, you could use Windows Write and later WordPad.

[![Wiz](https://www.bleepstatic.com/c/w/Secured-Images-970x250.png)](https://www.wiz.io/lp/secure-images-101-a-visual-guide?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FHardened-Images-101-Digital-Poster&sfcid=701Py00000WFCeLIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=Secured-Images-101) 

However, with the release of Windows 11, Microsoft decided to discontinue WordPad and remove it from Windows.

Instead, Microsoft rewrote Notepad to modernize it so it could act as both a simple text editor and an RTF editor, adding Markdown support that lets you format text and insert clickable links.

Markdown support means Notepad can open, edit, and save Markdown files (.md), which are plain text files that use simple symbols to format text and represent lists or links.

For example, to bold text or create a clickable link, you would add the following markdown text:

```
**This is bold text**
[Link to BleepingComputer](https://www.bleepingcomputer.com/)
```

## Microsoft fixes Windows Notepad RCE flaw

As part of the [February 2026 Patch Tuesday updates](https://www.bleepingcomputer.com/news/microsoft/microsoft-february-2026-patch-tuesday-fixes-6-zero-days-58-flaws/), Microsoft disclosed that it fixed a high-severity Notepad remote code execution flaw tracked as CVE-2026-20841.

"Improper neutralization of special elements used in a command ('command injection') in Windows Notepad App allows an unauthorized attacker to execute code over a network," explains [Microsoft's security bulletin](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20841).

Microsoft has attributed the discovery of the flaw to [Cristian Papa](https://www.linkedin.com/in/cristian-papa-aa4a38212/), [Alasdair Gorniak](https://www.linkedin.com/in/alasdair-gorniak/), and [Chen](https://x.com/chen9918b/status/2021414637884014761), and says it can be exploited by tricking a user into clicking a malicious Markdown link.

"An attacker could trick a user into clicking a malicious link inside a Markdown file opened in Notepad, causing the application to launch unverified protocols that load and execute remote files," explains Microsoft.

"The malicious code would execute in the security context of the user who opened the Markdown file, giving the attacker the same permissions as that user," continued the Advisory.

The novelty of the flaw quickly drew attention on social media, with cybersecurity researchers [quickly figuring out how it worked](https://github.com/BTtea/CVE-2026-20841-PoC) and how easy it was to exploit.

All someone had to do was create a Markdown file, like test.md, and create file:// links that pointed to executable files or used special URIs like ms-appinstaller://.

![Markdown for creating links to executable or to install an app](https://www.bleepstatic.com/images/news/security/vulnerabilities/n/notepad/CVE-2026-20841/poc_1.png)

**Markdown for creating links to executables or to install an app**  
_Source: [BTtea](https://github.com/BTtea/CVE-2026-20841-PoC)_

If a user opened this Markdown file in Windows 11 Notepad versions 11.2510 and earlier and viewed it in Markdown mode, the above text would appear as a clickable link. If the link is clicked with Ctrl+click, it would automatically execute the file without Windows displaying a warning to the user.

The execution of the program without a warning is what Microsoft considers to be the remote code execution flaw.

**Windows 11 command prompt launched without a warning**  
_Source: BTtea_

This could potentially allow attackers to create links to files in remote SMB shares that would then be executed without warning.

In BleepingComputer's tests, Microsoft has now fixed the Windows 11 Notepad flaw by displaying warnings when clicking a link if it does not use the http:// or https:// protocol.

**Windows 11 Notepad displays a warning when opening non-standard URLs**  
_Source: BleepingComputer_

Now, when clicking on all other types of URI links, including file:, ms-settings:, ms-appinstaller, mailto:, and ms-search:, Notepad will display the above dialog.

However, it's unclear why Microsoft didn't just prevent non-standard links in the first place, as it is still possible to social engineer users into clicking the 'Yes' button on the prompts.

The good news is that Windows 11 will automatically update Notepad via the Microsoft Store, so the flaw will likely have no impact beyond its novelty.