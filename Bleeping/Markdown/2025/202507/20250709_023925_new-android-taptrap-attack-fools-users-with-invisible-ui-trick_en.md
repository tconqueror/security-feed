# New Android TapTrap attack fools users with invisible UI trick

![New Android TapTrap attack fools users with invisible UI trick](https://www.bleepstatic.com/content/hl-images/2024/05/03/Android-2.jpg)

A novel tapjacking technique can exploit user interface animations to bypass Android's permission system and allow access to sensitive data or trick users into performing destructive actions, such as wiping the device.

Unlike traditional, overlay-based tapjacking, TapTrap attacks work even with zero-permission apps to launch a harmless transparent activity on top of a malicious one, a behavior that remains unmitigated in Android 15 and 16.

TapTrap was developed by a team of security researchers at TU Wien and the University of Bayreuth (Philipp Beer, Marco Squarcina, Sebastian Roth, Martina Lindorfer), and will be presented next month at the [USENIX Security Symposium](https://www.usenix.org/conference/usenixsecurity25/presentation/beer).

However, the team has already published a [technical paper](https://taptrap.click/usenix25%5Ftaptrap%5Fpaper.pdf) that outlines the attack and a [website](https://taptrap.click/) that summarizes most of the details.

## How TapTrap works

TapTrap abuses the way Android handles activity transitions with custom animations to create a visual mismatch between what the user sees and what the device actually registers.

A malicious app installed on the target device launches a sensitive system screen (permission prompt, system setting, etc.) from another app using ‘startActivity()’ with a custom low-opacity animation.

“The key to TapTrap is using an animation that renders the target activity nearly invisible,” the researchers say on a [website that explains the attack](https://taptrap.click/).

“This can be achieved by defining a custom animation with both the starting and ending opacity (alpha) set to a low value, such as 0.01,” thus making the malicious or risky activity almost completely transparent.

“Optionally, a scale animation can be applied to zoom into a specific UI element (e.g., a permission button), making it occupy the full screen and increasing the chance the user will tap it.”

![TapTrap overview](https://www.bleepstatic.com/images/news/u/1220909/2025/July/overview.jpg)

**TapTrap overview**  
_Source: taptrap.click_

Although the launched prompt receives all touch events, all the user sees is the underlying app that displays its own UI elements, as on top of it is the transparent screen the user actually engages with.

Thinking they interact with the bening app, a user may tap on specific screen positions that correspond to risky actions, such as an “Allow” or "Authorize" buttons on nearly invisible prompts.

A video released by the researchers demonstrates how a game app could leverage TapTrap to enable camera access for a website via Chrome browser.

## Risk exposure

To check if TapTrap could work with applications in Play Store, the official Android repository, the researchers analyzed close to 100,000. They found that 76% of them are vulnerable to TapTrap as they include a screen ("activity") that meets the following conditions:

* can be launched by another app
* runs in the same task as the calling app
* does not override the transition animation
* does not wait for the animation to finish before reacting to user input

The researchers say that animations are enabled on the latest Android version unless the user disables them from the developer options or accessibility settings, exposing the devices to TapTrap attacks.

While developing the attack, the researchers used Android 15, the latest version at the time, but after Android 16 came out they also ran some tests on it.

Marco Squarcina told BleepingComputer that they tried TapTrap on a Google Pixel 8a running Android 16 and they can confirm that the issue remains unmitigated.

GrapheneOS, the mobile operating system focused on privacy and security, also confirmed to BleepingComputer that the latest Android 16 is vulnerable to the TapTrap technique, and announced that their next release will [include a fix](https://x.com/GrapheneOS/status/1942235186923499549).

BleepingComputer has contacted Google about TapTrap, and a spokesperson said that the TapTrap problem will be mitigated in a future update:

“Android is constantly improving its existing mitigations against tapjacking attacks. We are aware of this research and we will be addressing this issue in a future update. Google Play has policies in place to keep users safe that all developers must adhere to, and if we find that an app has violated our policies, we take appropriate action.” - a Google representative told BleepingComputer.