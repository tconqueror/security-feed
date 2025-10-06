# Steam and Microsoft warn of Unity flaw exposing gamers to attacks

![Steam and Microsoft warn of Unity flaw exposing gamers to attacks](https://www.bleepstatic.com/content/hl-images/2025/10/06/Unity.jpg)

A code execution vulnerability in the Unity game engine could be exploited to achieve code execution on Android and privilege escalation on Windows.

Unity is a cross-platform game engine and development platform that provides rendering, physics, animation, and scripting tools for developers to create titles for Windows, macOS, Android, iOS, consoles, and the web.

A large number of mobile games are built with Unity, as well as indie and mid-tier PC/console titles. The platform is also used in non-gaming industries for real-time 3D applications.

### Valve and Microsoft warn users

In response to the risk, Steam has taken action by releasing a [new Client update](https://steamcommunity.com/groups/steamworks/announcements/detail/524229329545071275) that blocks the launching of custom URI schemes to prevent exploitation through its distribution platform.

At the same time, Valve recommends that publishers rebuild their games using a safe Unity version, or plug a patched version of the ‘UnityPlayer.dll’ file right into their existing builds.

Microsoft has also [published a bulletin](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59489) to warn about the issue, recommending users to uninstall vulnerable games are uninstalled until new versions that address CVE-2025-59489 become available.

The company said that popular game titles are vulnerable, including Hearthstone, The Elder Scrolls: Blades, Fallout Shelter, DOOM (2019), Wasteland 3, and Forza Customs.

Unity recommends developers to update the editor to the latest version branch and then recompile and redeploy their games or applications.

### Patch extended to some unsupported versions

The vulnerability is tracked as [CVE-2025-59489](https://nvd.nist.gov/vuln/detail/CVE-2025-59489) and affects the Runtime component. It allows unsafe file loading and local file inclusion, and could lead to code execution and information disclosure.

GMO Flatt Security’s researcher ‘RyotaK’ discovered the vulnerability in May, at the Meta Bug Bounty Researcher Conference and says that it affects all games built on versions of the engine starting 2017.1.

“\[The vulnerability\] could allow local code execution and access to confidential information on end user devices running unity-built applications,” Unity warns in its [security bulletin](https://unity.com/security/sept-2025-01).

“Code execution would be confined to the privilege level of the vulnerable application, and information disclosure would be confined to the information available to the vulnerable application.”

In a [technical writeup](http://flatt.tech/research/posts/arbitrary-code-execution-in-unity-runtime/), RyotaK showed that Unity’s handling of Android Intents allows any malicious app installed on the same device as the vulnerable game to load and execute an attacker-supplied native library.

This enables the attacker to achieve arbitrary code execution with the target game’s privileges.

While Ryotak discovered the issue on Android, the root cause - Unity’s handling of the _\-xrsdk-pre-init-library_ command line argument without proper validation or sanitization, is also present on Windows, macOS, and Linux operating platforms.

There are different input paths on these systems that can feed untrusted arguments or modify library search paths on the targeted application, so when conditions are met, exploitation is possible.

Unity states that it has observed no active exploitation as of the publication of its bulletin on October 2nd.

Fixes are available and the remediation steps include updating "the Unity Editor to the newest version then rebuild and redeploy the application" and replacing the Unity runtime binary with a patched version.

Unity has released fixes to out-of-support versions starting 2019.1 and later. Older versions that are no longer supported will not receive the patch.