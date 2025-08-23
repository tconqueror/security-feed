# Apple Safari exposes users to fullscreen browser-in-the-middle attacks

![Apple Safari exposes users to fullscreen browser-in-the-middle attacks](https://www.bleepstatic.com/content/hl-images/2025/05/29/apple.jpg)

A weakness in Apple's Safari web browser allows threat actors to leverage the fullscreen browser-in-the-middle (BitM) technique to steal account credentials from unsuspecting users.

By abusing the Fullscreen API, which instructs any content on a webpage to enter the browser's fullscreen viewing mode, hackers can exploit the shortcoming to make guardrails less visible on Chromium-based browsers and trick victims into typing sensitive data in an attacker-controlled window.

SquareX researchers observed an increase use of this type of malicious activity and say that such attacks are particularly dangerous for Safari users, as Apple’s browser fails to properly alert users when a browser window enters fullscreen mode.

“SquareX’s research team has observed multiple instances of the browser’s FullScreen API being exploited to address this flaw by displaying a fullscreen BitM window that covers the parent window’s address bar, as well as a limitation specific to Safari browsers that makes fullscreen BitM attacks especially convincing,” [describes the report](https://labs.sqrx.com/fullscreen-bitm-f2634a91e6a5).

## How BitM works

A common [BitM attack](https://www.bleepingcomputer.com/news/security/devious-phishing-method-bypasses-mfa-using-remote-access-software/) involves tricking users into interacting with an attacker-controlled remote browser that shows a legitimate login page. This is achieved through tools like noVNC - an open-source VNC browser client, which opens a remote browser on top of the victim's session.

![Example of a BitM attack targeting Steam accounts](https://www.bleepstatic.com/images/news/u/1100723/BitM_example.webp)

**Attacker-controlled browser opens legitimate Steam login page in BitM attack**  
_Source: SquareX_

Since the log in process happens in the attacker's browser, the credentials are collected but the victim also successfully accesses their account unaware of the theft.

The attack still requires tricking the victim into clicking on a malicious link that redirects them to a fake site impersonating the target service. However, this can be easily achieved through sponsored ads in web browsers, social media posts, or comments.

![Sponsored ad leads to fake Figma site](https://www.bleepstatic.com/images/news/u/1100723/FakeAd_Figma.jpg)

**Promoting fake Figma site through sponsored ads**  
_Source: SquareX_

## Fullscreen deception

If users miss the suspicious URL in the browser bar and click on the log in button, the BitM window becomes active. Until triggered, the window stayed hidden from the victim in minimized mode.

If users miss the suspicious URL in the browser bar and click on the log in button, which activates the BitM window that was hidden from the victim in minimized mode.

Once activated, the attacker-controlled browser window enters fullscreen mode and covers the fake website, showing to the user the legitimate website they wanted to access.

Security solutions like EDRs or SASE/SSE won’t trigger any warnings when this happens, as the attack abuses standard browser APIs.

The researchers explain that Firefox and Chromium-based browsers (e.g. Chrome and Edge) show an alert whenever fullscreen is active. Although many users may miss the warning, it is still a guardrail that lowers the risk of a BitM attack.

**Warning message for fullscreen mode on Firefox (left) and Chrome (right)**  
_Source: SquareX_

However, on Safari there is no alert and the only sign of a browser entering fullscreen mode is a “swipe” animation that can be easily missed.

"While the attack works on all browsers, fullscreen BiTM attacks are particularly convincing on Safari browsers due to the lack of clear visual cues when going fullscreen," SquareX researchers say.

SquareX contacted Apple with its findings and received a “wontfix” reply, the explanation received being that the animation is present to indicate changes, and that should be enough.

BleepingComputer has also reached out to Apple for a comment, but we are still waiting for their response.