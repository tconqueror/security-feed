# Google to flag Android apps with excessive battery use on the Play Store

![Android](https://www.bleepstatic.com/content/hl-images/2024/02/08/Android.jpg)

Google will start taking action on Android apps in the official Google Play store that have high background activity and cause excessive battery draining.

Apps that exceed a "bad behavior threshold" may be flagged on Google Play for negatively impacting battery performance and may affect their visibility in the Android ecosystem.

Developers have until March 1, 2026, to update their apps to comply with a new core Android Vitals metric called "excessive partial wake locks."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

The algorithm has been in beta since April 14, and Google developed it in close collaboration with Samsung.

"This is the first in a series of new metrics designed to provide deeper insight into your app's resource utilization, enabling you to improve the experience for your users across the entire Android ecosystem," Google [announced](http://android-developers.googleblog.com/2025/11/raising-bar-on-battery-performance.html).

Apps that go beyond the bad behavior threshold for excessive wake locks may be flagged as battery drainers on Google Play and could be excluded "from prominent discovery surfaces such as recommendations."

![Warning displayed on Google Play](https://www.bleepstatic.com/images/news/u/1220909/2025/November/image3_new.jpg)

**Warning displayed on an offending app's Google Play listing**  
_Source: Google_

## What Google will measure

Google Play's Android vitals system will track partial wake locks, the cumulative time the app spends with background work while the screen is off, and prevent the device from entering sleep mode.

The measurement will be per user session and across all sessions over a 28-day window, counting only non-exempt wake locks, meaning locks that aren't system-held, related to audio playback, or user-initiated data transfer.

An application's behavior will be considered excessive when a single user session holds over two cumulative hours of non-exempt wake locks within 24 hours.

Google considers the bad-behavior threshold to be 5% of an app's user sessions over the past 28 days.

Developers with apps that exceed this level will receive an alert on their [Android vitals overview page](https://play.google.com/console/developers/app/vitals/metrics/overview).

**Warning to developers of apps with excessive CPU/battery use**  
_Source: Google_

Ultimately, this policy change will [pressure](https://developer.android.com/topic/performance/vitals/excessive-wakelock) developers to tighten their apps' behavior, reduce excessive or unnecessary wake locks, release them as soon as possible, and pay closer attention to wake locks initiated by external libraries and SDKs.

When asked whether this feature would be used to detect spyware, adware, and malware, which commonly refuse to sleep to keep network channels open and exfiltrate data, we were told that this is not the intended function of the feature.

"App security is a top priority on Google Play. However, the primary intent of this metric is to level up battery performance and technical quality to better our users' experience," explained Google.

"This metric is targeting 'bad behavior' in terms of excessive resource consumption, irrespective of whether an app is malicious. By enforcing these thresholds, we can identify and take action on apps that are abusing system resources without providing user value – but it is not primarily intended to target malware."