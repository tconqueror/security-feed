# Max severity Ni8mare flaw lets hackers hijack n8n servers

![Max severity Ni8mare flaw lets hackers hijack n8n servers](https://www.bleepstatic.com/content/hl-images/2024/03/05/hand.jpg)

A maximum severity vulnerability dubbed "Ni8mare" allows remote, unauthenticated attackers to take control over locally deployed instances of the N8N workflow automation platform.

The security issue is identified as CVE-2026-21858 and has a 10 out of 10 severity score. According to researchers at data security company Cyera, there are more than 100,000 vulnerable n8n servers.

n8n is an open-source workflow automation tool that allows users to connect applications, APIs, and services into complex workflows via a visual editor. It is primarily used to automate tasks and supports integrations with AI and large language model (LLM) services.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

It has over 50,000 weekly downloads [on npm](https://www.npmjs.com/package/n8n?activeTab=versions) and more than 100 million pulls on Docker Hub. It is a popular tool in the AI space, where it is used to orchestrate LLM calls, build AI agents and [RAG pipelines](https://blog.n8n.io/rag-pipeline/), and [automate data ingestion](https://n8n.io/integrations/solve-data/) and retrieval.

### Ni8mare details

The Ni8mare vulnerability gives an attacker access to files on the underlying server by executing certain form-based workflows.

"A vulnerable workflow could grant access to an unauthenticated remote attacker. This could result in exposure of sensitive information stored on the system and may enable further compromise depending on deployment configuration and workflow usage," n8n[ developers say](https://github.com/n8n-io/n8n/security/advisories/GHSA-v4pr-fm98-w9pg).

Cyera researchers discovered the Ni8mare vulnerability (CVE-2026-21858) and reported it to n8n on November 9, 2025\. They say that the security issue is a content-type confusion in the way n8n parses data.

n8n uses two functions to process incoming data based on the 'content-type' header configured in a webhook, the component that triggers events in a workflow by listening for specific messages.

When the webhook request is marked as multipart/form-data, n8n treats it as a file upload and uses a special upload parser that saves files in randomly generated temporary locations.

"This means users can’t control where files end up, which protects against path traversal attacks."

However, for all other content types, n8n uses its standard parser instead.

Cyera [found](http://www.cyera.com/research-labs/ni8mare-unauthenticated-remote-code-execution-in-n8n-cve-2026-21858) that by setting a different content type, such as application/json, an attacker can bypass the upload parser.

In this situation, n8n still processes file-related fields but does so without verifying that the request actually contains a valid file upload. This allows the attacker to fully control the file metadata, including the file path.

![The flawed parser logic](https://www.bleepstatic.com/images/news/u/1220909/2026/January/diagram(2).jpg)

**The flawed parser logic**  
_Source: Cyera_

"Since this function is called without verifying the content type is multipart/form-data, we control the entire req.body.files object. That means we control the filepath parameter – so instead of copying an uploaded file, we can copy any local file from the system," explains Cyera.

This allows reading arbitrary files from an n8n instance, which can expose secrets by adding internal files into the workflow's knowledge base.

Cyera says this can be abused to expose secrets stored on the instance, inject sensitive files into workflows, forge session cookies to bypass authentication, or even execute arbitrary commands.

**Triggering Ni8mare (CVE-2026-21858) to access the database**  
_Source: Cyera_

Cyera emphasizes that n8n often stores API keys, OAuth tokens, database credentials, cloud storage access, CI/CD secrets, and business data, making it a central automation hub.

n8n developers say that there is no official workaround available for Ni8mare, but one mitigation is to restrict or disable publicly accessible webhook and form endpoints.

The recommended action is to update to n8n version 1.121.0 or a more recent one.