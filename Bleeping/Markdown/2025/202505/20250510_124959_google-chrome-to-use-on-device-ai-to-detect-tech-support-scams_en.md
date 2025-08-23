# Google Chrome to use on-device AI to detect tech support scams

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Google is implementing a new Chrome security feature that uses the built-in 'Gemini Nano' large-language model (LLM) to detect and block tech support scams while browsing the web.

Tech support scams are malicious websites that trick users into thinking their computer has a virus infection or other problem. These alerts are shown as full-screen browser windows or will display additional pop-ups, making them difficult to close.

The goal is to convince the victim to call a listed number for help to either sell unnecessary remote support subscriptions or gain remote access to devices, which can lead to [financial losses](https://www.bleepingcomputer.com/news/security/ftc-will-send-255-million-to-victims-of-tech-support-scams/) or data theft.

![Example tech support scam](https://www.bleepstatic.com/images/news/security/t/tech-support-scams/recipe/tech-support-scam.jpg)

**Example tech support scam**  
_Source: BleepingComputer_

Google Chrome 126 to power AI features directly within the browser for faster, privacy-focused assistance.

Chrome's new anti-scam system, which is integrated into the browser's 'Enhanced Protection,' analyzes web pages in real time to detect scam signals like fake virus alerts or full-screen lockouts, which are hallmarks of tech support scams.

This analysis takes place offline, locally on the user's device using Gemini Nano. When there's a positive match, the data (LLM output + site metadata) is sent to 'Google Safe Browsing' for a more thorough evaluation.

If malicious intent is confirmed, Chrome will display a warning message informing the user of the risk.

![Overview of how the new system works](https://www.bleepstatic.com/images/news/u/1220909/2025/May/diagram.jpg)

**Overview of how the new system works**  
_Source: Google_

Google says the feature respects users' privacy and has only a minimal performance impact, though not many details were given in the announcement.

"This is all done in a way that preserves performance and privacy," [announced Google](https://security.googleblog.com/2025/05/using-ai-to-stop-tech-support-scams-in.html).

"In addition to ensuring that the LLM is only triggered sparingly and run locally on the device, we carefully manage resource consumption by considering the number of tokens used, running the process asynchronously to avoid interrupting browser activity, and implementing throttling and quota enforcement mechanisms to limit GPU usage."

The AI-powered protection feature will be implemented on Chrome 137, scheduled for release next week, and it will be enabled by default on all users who upgrade to the latest version and opt into 'Enhanced Protection' within the browser's Safe Browsing settings.

Open **Chrome Settings > Privacy and Security > Security > Enhanced Protection** to enable it.

_Source: BleepingComputer_

Google stated it plans to expand the system in future releases and make it capable of detecting other scam types, such as fake package delivery or toll notices. Also, Chrome for Android will get this feature sometime in 2025.

Google's new anti-scam feature is similar to what Microsoft [introduced for Edge](https://www.bleepingcomputer.com/news/microsoft/microsoft-tests-edge-scareware-blocker-to-block-tech-support-scams/) earlier this year, which uses a specially trained machine learning model to detect and block scams targeting the user.