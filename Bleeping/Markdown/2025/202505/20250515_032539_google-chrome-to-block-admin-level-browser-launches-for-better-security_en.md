# Google Chrome to block admin-level browser launches for better security

![Chrome](https://www.bleepstatic.com/content/hl-images/2023/06/16/Google-Chrome-headpic.jpg)

Google is rolling out a change to Chromium that "de-elevates" Google Chrome so it does not run as an administrator to increase security in Windows.

Microsoft [previously introduced](https://www.bleepingcomputer.com/news/security/new-microsoft-edge-to-warn-users-when-in-administrator-mode/) a similar feature in 2019 to the Edge Browser. When users launched Edge with elevated permissions, a warning would appear, recommending that they relaunch the browser without administrative rights.

![Microsoft Edge alert](https://www.bleepstatic.com/images/news/web-browsers/edge/chromium-edge/administrative-mode-alert/browser-alert.jpg)

Later, Microsoft modified the feature to automatically prevent the Edge browser from launching with elevated permissions.

Microsoft is now bringing the same improvements to Chromium, with developers submitting a commit to the Chromium source code.

As [spotted](https://x.com/Leopeva64/status/1921807525009064363) by Leo on X, Microsoft has confirmed that Chrome will now automatically de-elevate when users try to launch it with elevated permissions.

"Automatically de-elevate users launching chrome elevated. This CL is based on changes we've had in Edge, circa 2019, which attempts to automatically de-elevate the browser when it's run with the elevated part of a split / linked token," Stefan Smolen, who works with the Microsoft Edge team, wrote in a [Chromium commit](https://chromium-review.googlesource.com/c/chromium/src/+/6515318).

"This automatically attempts a relaunch once, and then if it still fails it falls back to the current behaviour (which tries to launch admin)."

Microsoft has also added a command-line switch, "-do-not-de-elevate," to prevent the de-elevation after an auto-relaunch to prevent infinite loops.

" Do not de-elevate the browser on launch. Used after de-elevating to prevent infinite loops," reads a comment in the source code.

This feature does not work for Chrome processes launched with elevated rights when in automation mode, so as not to interfere with tools that may need to run automatically.

However, in general, Microsoft warns that launching the browser in admin mode is not a good idea.

When Chrome runs as an Administrator, it inherits elevated permissions, which means anything you download and open through the browser will also launch with Administrator rights, which can pose a serious security risk.

If you accidentally download and run a malicious file, it could execute with full system access, potentially compromising your entire operating system without any warning.