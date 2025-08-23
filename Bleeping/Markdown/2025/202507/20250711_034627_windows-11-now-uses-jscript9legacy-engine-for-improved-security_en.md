# Windows 11 now uses JScript9Legacy engine for improved security

![Windows 11 now uses JScript9Legacy engine for improved security](https://www.bleepstatic.com/content/hl-images/2025/02/07/Windows-11.jpg)

Microsoft announced that it has replaced the default scripting engine JScript with the newer and more secure JScript9Legacy on Windows 11 version 24H2 and later.

The decision is driven by security concerns, as JScript9Legacy is expected to offer better protection against web threats, such as cross-site scripting (XSS), and also improved performance.

"To provide a more secure experience, beginning with Windows 11, version 24H2, JScript9Legacy is enabled by default to handle all scripting processes and operations that previously used JScript," [announced Microsoft's Naveen Shankar](https://techcommunity.microsoft.com/blog/windows-itpro-blog/jscript9legacy-scripting-engine-now-enabled-by-default/4431326).

JScript (jscript.dll), introduced in 1996, is Microsoft's implementation of ECMAScript, similar to JavaScript, and was primarily used in Internet Explorer and as a scripting language for Windows to automate tasks, validate forms, or create admin scripts.

The engine is considered severely outdated today, non-compliant with modern JavaScript security standards, and a frequent target of memory corruption, arbitrary code execution, and XSS vulnerabilities triggered through malicious documents, emails, and websites.

Despite its status, it remained the default engine on Windows until now to ensure backward compatibility and avoid breaking workflows in critical systems.

But with Internet Explorer now deprecated and increased adoption of Edge browser, Microsoft is drawing the line and finally replaces JScript with JScript9Legacy (jscript9legacy.dll) starting Windows 11 24H2.

The new engine is a modernized version of JScript9, which can be used outside the browser, and is designed to support legacy scripting needs with better security and compatibility.

No user action is required for the switch to take effect on the latest Windows version, and existing scripts should continue to work as expected.

If compatibility issues arise, Microsoft says a rollback to the old engine is possible by contacting the support team.