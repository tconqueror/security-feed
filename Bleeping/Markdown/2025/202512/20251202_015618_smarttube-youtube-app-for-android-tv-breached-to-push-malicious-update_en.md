# SmartTube YouTube app for Android TV breached to push malicious update

![SmartTube](https://www.bleepstatic.com/content/hl-images/2025/12/01/smartyoutubetv_screenshot_01.jpg)

The popular open-source SmartTube YouTube client for Android TV was compromised after an attacker gained access to the developer's signing keys, leading to a malicious update being pushed to users.

The compromise became known when multiple users reported that Play Protect, Android's built-in antivirus module, [blocked SmartTube on their devices](https://github.com/yuliskov/SmartTube/issues/5131#issue-3670629826) and warned them of a risk.

The developer of SmartTube, Yuriy Yuliskov, admitted that his digital keys [were compromised](https://github.com/yuliskov/SmartTube/releases/tag/notification) late last week, leading to the injection of malware into the app.

Yuliskov revoked the old signature and said he would soon publish a new version with a separate app ID, urging users to move to that one instead.

SmartTube is one of the most widely downloaded third-party YouTube clients for Android TVs, Fire TV sticks, Android TV boxes, and similar devices.

Its popularity stems from the fact that it is free, can block ads, and performs well on underpowered devices.

A user who [reverse-engineered](https://github.com/yuliskov/SmartTube/issues/5131#issuecomment-3592348406) the compromised SmartTube version number 30.51 found that it includes a hidden native library named libalphasdk.so \[[VirusTotal](https://www.virustotal.com/gui/file/63bb4b3ddfa723a2a8c82de026c71ee2d49e78f1634099b0f3c3b65ba8bf5cb7)\]. This library does not exist in the public source code, so it is being injected into release builds.

"Possibly a malware. This file is not part of my project or any SDK I use. Its presence in the APK is unexpected and suspicious. I recommend caution until its origin is verified," [cautioned Yuliskov on a GitHub thread](https://github.com/yuliskov/SmartTube/issues/5131#issuecomment-3591009196).

The library runs silently in the background without user interaction, fingerprints the host device, registers it with a remote backend, and periodically sends metrics and retrieves configuration via an encrypted communications channel.

All this happens without any visible indication to the user. While there's no evidence of malicious activity such as account theft or participation in DDoS botnets, the risk of enabling such activities at any time is high.

Although the [developer announced](https://t.me/SmartTubeEN/213780) on Telegram the release of safe beta and stable test builds, they have not reached the project's official GitHub repository yet.

Also, the developer has not provided full details of what exactly happened, which has created trust issues in the community.

Yuliskov [promised](https://github.com/yuliskov/SmartTube/issues/5142#issuecomment-3591868600) to address all concerns once the final release of the new app is pushed to the F-Droid store.

Until the developer transparently discloses all points publicly in a detailed post-mortem, users are recommended to stay on older, known-to-be-safe builds, avoid logging in with premium accounts, and turn off auto-updates.

Impacted users are also recommended to reset their Google Account passwords, check their account console for unauthorized access, and remove services they don't recognize.

At this time, it is unclear exactly when the compromise occurred or which versions of SmartTube are safe to use. One user [reported](https://github.com/yuliskov/SmartTube/issues/5142#issue-3676429378) that Play Protect doesn't flag version 30.19, so it appears safe.

BleepingComputer has contacted Yuliskov to determine which versions of the SmartTube app were compromised, but a comment hasn't been available yet.