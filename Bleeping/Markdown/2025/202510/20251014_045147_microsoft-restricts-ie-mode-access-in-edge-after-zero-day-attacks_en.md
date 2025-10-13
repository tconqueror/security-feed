# Microsoft restricts IE mode access in Edge after zero-day attacks

![Microsoft restricts IE mode access in Edge after zero-day attacks](https://www.bleepstatic.com/content/hl-images/2021/06/01/Microsoft-Edge.jpg)

Microsoft is restricting access to Internet Explorer mode in Edge browser after learning that hackers are leveraging zero-day exploits in the Chakra JavaScript engine for access to target devices.

The tech giant did not share too many technical details but said that the threat actor combined social engineering with an exploit in Chakra to gain remote code execution.

“The \[Edge security\] team recently received intelligence indicating that threat actors were abusing Internet Explorer (IE) mode within Edge to gain access to unsuspecting users’ devices,” [says](https://microsoftedge.github.io/edgevr/posts/Changes-to-Internet-Explorer-Mode-in-Microsoft-Edge/) Gareth Evans, Microsoft Edge Security Team Lead.

Although support for Internet Explorer ended on June 15, 2022, Microsoft Edge has an IE mode for legacy compatibility with older technologies (ActiveX and Flash) still in use with a small set of business applications and government portals.

In August, the Edge security team learned that threat actors were directing targets to "an official-looking spoofed website" that prompted users, through an interface element, to load the page in IE mode.

After exploiting the zero-day in Chakra, the attacker leveraged a second vulnerability to increase privileges and escape the browser, and take full control of the device.

Evans did not provide identifiers for the exploited vulnerabilities and said the flaw in Chakra is unpatched.

To mitigate the risk, Microsoft removed the methods that allowed activating IE mode in Edge through easy methods, like the dedicated toolbar button, context menu, and items in the hamburger menu.

Users who want IE mode active now have to navigate to Settings > Default Browser > Allow and define the pages that should be loaded using Internet Explorer.

![Edge setting for IE mode](https://www.bleepstatic.com/images/news/u/1220909/2025/October/edge.jpg)

**Edge setting for IE mode**  
_Source: BleepingComputer_

The new restrictions aim at making the activation of IE mode an intentional user action. Furthermore, the list of websites approved to load in IE mode should make it very difficult for attackers to succeed in their compromise attempts.

These changes do not apply to commercial users, who will continue to use IE mode as configured through enterprise policies.

However, Microsoft reminded users that they should migrate from the legacy web technology in Internet Explorer to modern products that deliver better security, are more reliable, and come with improved performance.