# Unofficial Postmark MCP npm silently stole users' emails

![Unofficial Postmark MCP npm silently stole users' emails (edited) ](https://www.bleepstatic.com/content/hl-images/2024/01/03/email.jpg)

A npm package copying the official ‘postmark-mcp’ project on GitHub turned bad with the latest update that added a single line of code to exfiltrate all its users' email communication.

Published by a legitimate-looking developer, the malicious package was a perfect replica of the authentic one in terms of code and description, appearing as an official port on npm for 15 iterations.

Model Context Protocol (MCP) is an open standard that allows AI assistants to interface with external tools, APIs, and databases in a structured, predefined, and secure manner.

Postmark is an email delivery platform, and Postmark MCP is the MCP server that exposes Postmark’s functionality to AI assistants, letting them send emails on behalf of the user or app.

As [discovered by Koi Security](https://www.koi.security/blog/postmark-mcp-npm-malicious-backdoor-email-theft) researchers, the malicious package on npm was clean in all versions through1.0.15, but in the 1.0.16 release, it added a line that forwarded all user emails to an external address at giftshop\[.\]club linked to the same developer.

![Line added on the package's code to BCC the publisher](https://www.bleepstatic.com/images/news/u/1220909/2025/September/bccline.jpg)

**Dev added their email address to receive copies of users' communication**  
_Source: Koi Security_

This extremely risky functionality may have exposed personal sensitive communications, password reset requests, two-factor authentication codes, financial information, and even customer details.

The malicious version on npm was available for a week and recorded around 1,500 downloads. By Koi Security's estimations, the fake package might have exfiltrated thousands of emails from unsuspecting users.

For those who downloaded _postmark-mcp_ from npm, it is recommended to remove it immediately and rotate any potentially exposed credentials. Also, audit all MCP servers in use and monitor them for suspicious activity.

BleepingComputer has contacted the npm package publisher to ask about Koi Security’s findings, but we received no reply. The following day, the developer removed the malicious package from npm.

![The impersonator package on npm](https://www.bleepstatic.com/images/news/u/1220909/2025/September/npm.jpg)

**The impersonator package on npm**  
_Source: Koi Security_

Koi Security’s report highlights a broken security model where servers are implemented in critical environments without oversight or sandboxing, and AI assistants executing malicious commands without filtering for malicious behavior.

Because MCPs run with very high privileges, any [vulnerability](https://www.bleepingcomputer.com/news/security/ai-powered-cursor-ide-vulnerable-to-prompt-injection-attacks/) or [misconfiguration](https://www.bleepingcomputer.com/news/security/asana-warns-mcp-ai-feature-exposed-customer-data-to-other-orgs/) carries a significant risk.

Users should verify the source of the project and make sure it's an official repository, review the source code and changelogs, and look carefully for changes in every update.

Before using a new version in production, run MCP servers in isolated containers or sandboxes and monitor their behavior for suspicious actions like data exfiltration or unauthorized communication.