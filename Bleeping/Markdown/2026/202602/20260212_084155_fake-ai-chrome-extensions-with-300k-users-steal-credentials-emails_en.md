# Fake AI Chrome extensions with 300K users steal credentials, emails

![Fake AI Chrome extensions with 300K users steal credentials, emails](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

A set of 30 malicious Chrome extensions that have been installed by more than 300,000 users are masquerading as AI assistants to steal credentials, email content, and browsing information.

Some of the extensions are still present in the Chrome Web Store and have been installed by tens of thousands of users, while others show a small install count.

Researchers at browser security platform LayerX discovered the malicious extension campaign and named it AiFrame. They found that all analyzed extensions are part of the same malicious effort as they communicate with infrastructure under a single domain, _tapnetic\[.\]pro_.

[![Wiz](https://www.bleepstatic.com/c/w/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=AI-Agents-101) 

According to them, the most popular extension in the AiFrame campaign had 80,000 users and was called Gemini AI Sidebar (fppbiomdkfbhgjjdmojlogeceejinadg), but it is no longer on the Chrome Web Store.

However, BleepingComputer found that other extensions with thousands of users are still present on Google's repository for Chrome extensions. It should be noted that the names may be different in some cases, but the identification is the same.

1. **AI Sidebar** (gghdfkafnhfpaooiolhncejnlgglhkhe) – 70,000 users
2. **AI Assistant** (nlhpidbjmmffhoogcennoiopekbiglbp) – 60,000 users
3. **ChatGPT Translate** (acaeafediijmccnjlokgcdiojiljfpbe) – 30,000 users
4. **AI GPT** (kblengdlefjpjkekanpoidgoghdngdgl) – 20,000 users
5. **ChatGPT** (llojfncgbabajmdglnkbhmiebiinohek) – 20,000 users
6. **AI Sidebar** (djhjckkfgancelbmgcamjimgphaphjdl) – 10,000 users
7. **Google Gemini** (fdlagfnfaheppaigholhoojabfaapnhb) – 10,000 users

LayerX found that all 30 extensions share the same internal structure, JavaScript logic, permissions, and backend infrastructure.

The malicious browser add-ons do not implement AI functionality locally; instead, they deliver the promised feature by rendering a full-screen iframe to load content from a remote domain.

This, by itself, is risky, as publishers can change the extensions’ logic at any time without pushing an update - just like in the case of [Microsoft Office Add-ins](https://www.bleepingcomputer.com/news/security/microsoft-store-outlook-add-in-hijacked-to-steal-4-000-microsoft-accounts/) \- thus avoiding a new review.

In the background, the extensions extract page content from websites the user visits, including sensitive authentication pages, using Mozilla’s Readability library.

LayerX says that a subset of 15 extensions specifically targets Gmail data, using a dedicated content script that runs at ‘document\_start’ on ‘mail.google.com’ and injects UI elements.

The script reads visible email content directly from the DOM and repeatedly extracts email thread text via ‘.textContent.’ The researchers note that even email drafts can be captured.

“When Gmail-related features such as AI-assisted replies or summaries are invoked, the extracted email content is passed into the extension’s logic and transmitted to third-party backend infrastructure controlled by the extension operator,” [LayerX explains](https://layerxsecurity.com/blog/aiframe-fake-ai-assistant-extensions-targeting-260000-chrome-users-via-injected-iframes/?utm%5Fsource=BC) in a report today.

“As a result, email message text and related contextual data may be sent off-device, outside of Gmail’s security boundary, to remote servers.”

The extensions also feature a remotely triggered voice recognition and transcript generation mechanism using the ‘Web Speech API,’ returning the results to the operators. Depending on the granted permissions, the extensions may even siphon conversations from the victim’s environment.

BleepingComputer has contacted Google for a comment on LayerX findings, but we have not received a response by publication time.

It is recommended to check LayerX's list of indicators of compromise for the complete set of malicious extensions. If compromise is confirmed, users should reset passwords for all accounts.